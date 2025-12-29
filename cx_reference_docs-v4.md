# cx Module – Developer Documentation

## Purpose

The JavaSCript `cx` module is a frontend API that provides a clean interface for reading/setting basic vacancy information to enrich 3rd-party tracking or attribution scripts like Google Tag Manager (GTM), Google Analytics 4 (GA4) and Meta Pixel.

Secondly Carerix Applicant Tracking parameters (`applySource` and `applyTags`) can be read, set or modified which are stored as metadata in the Matching File when an applicant has applied..
This gives recruiters insight into application origins (for example: campaign, platform, or referrer).

---

## How the `cx` Object Appears in the Browser Console

Before inspecting the `cx` object, make sure you are viewing a **vacancy-detail page**, because only those pages load and populate the `cx` API.

Then open your browser’s Developer Tools console and type:

```js
cx.
```

*(Include the dot — this shows autocompletion and the available properties and functions.)*

You will then see a list of accessible fields and functions, for example:

- `applySource`
- `applyTags`
- `gaClientID`
- `getApplySource()`
- etc.

This gives a quick overview of what data is currently available and can be read or modified.

---

## Public API Summary

| Property/Method                | Type     | Persistence     | Description                  |
| ------------------------------ | -------- | --------------- | ---------------------------- |
| `getPublicationID()`           | function | page-level data | Get publication ID           |
| `publicationID`                | value    | page-level data | Alias of getPublicationID()  |
| `getVacancyID()`               | function | page-level data | Get vacancy ID               |
| `vacancyID`                    | value    | page-level data | Alias of getVacancyID()      |
| `getTitle()`                   | function | page-level data | Get vacancy title            |
| `title`                        | value    | page-level data | Alias of getTitle()          |
| `getGaClientID()`              | function | page-level data | Get GA client ID             |
| `gaClientID`                   | value    | page-level data | Alias of getGaClientID()     |
| `getGaClientIDWithTimestamp()` | function | page-level data | Get GA Client ID + timestamp |
| `gaClientIDWithTimestamp`      | value    | page-level data | Alias of getGaClientIDWithTimestamp() |
| `setApplySource()`             | function | cookie (30d)    | Set application source. Will appear in the Carerix Match File  |
| `getApplySource()`             | function | cookie fallback | Get application source (from URL param cx_applysource or cookie)  |
| `applySource`                  | value    | cookie fallback | Same as getApplySource()     |
| `setApplyTags()`               | function | cookie (30d)    | Set tags (comma-separated). Will appear in the Carerix Match File  |
| `getApplyTags()`               | function | cookie fallback | Get tags (from URL param cx_applytags or cookie)  |
| `applyTags`                    | value    | cookie fallback | Same as getApplyTags()        |

> Some setter functions that aren’t relevant have been left out.

---

## Carerix Application Tracking (to the Match File)
1. The applicant arrives on a vacancy detail page extended with **additional** URL parameters such as:
```
?cx_applysource=email&cx_applytags=campaign-abcd
```
2. The **CX WP Plugin copies these URL parameters into cookies** (`cx_applysource` and `cx_applytags`)
3. These cookie values are then automatically read by the JavaScript `cx` object at page load. This means the JS version of `applySource` and `applyTags` always starts with the values provided by the URL (if present), ensuring full alignment between URL → cookie → JavaScript → Carerix Application Tracking.
4. This JavaScript module lets 3rd-party scripts read/modify/override them
5. When the applicant submits their application form, the CX WP Plugin sends the final `applySource` and `applyTags` values to Carerix.
6. In the Carerix App, these values appear in the **match file**, giving the recruiter insight into application origin and campaign attribution.


### `applySource`

Used to store the originating source of an application, e.g.:
- `linkedin`
- `indeed`
- `facebook`
- `referral`
- `jobboard-xyz`
- `googleads`
- `email`

Stored in a cookie: `cx_applysource` (30 days).

### `applyTags` (comma-separated)

A tag to specify/clarify the `applySource`, e.g.:
- `"summer-campaign"`
- `"jobalert"`
- `"agency-abcd"`

You can use multiple tags by separating them by a comma, e.g.:
- `"region-north,region-south"`

Stored in cookie `cx_applytags` (30 days)

> Third-party developers should not rely on cookies directly — always use the `cx` getters/setters.

---

## Examples

### General JavaScript demonstration

```js
alert('Hello, you are viewing vacancy ID ' + cx.getVacancyID() + ' titled: ' + cx.getTitle() );
```

### Using for Google Tag Manager and Analytics
Because all vacancy-related values (vacancy ID, publication ID, title, applySource, applyTags, etc.) are available via the `cx` object, they can be pushed into the Google DataLayer:

```js
dataLayer.push({
  event: "vacancy_view",
  vacancyID: cx.getVacancyID(),
  publicationID: cx.getPublicationID(),
  title: cx.getTitle(),
  applySource: cx.getApplySource(), // get from URL param `cx_applysource` or an earlier set cookie
  applyTags: cx.getApplyTags(), // // get from URL param `cx_applytags` or an earlier set cookie
});
```

This enables integration with:
- Google Tag Manager
- Google Analytics 4
- Attribution pipelines
- External marketing or tracking scripts

### Setting Carerix Match File tracking values

This will override any apply source apply tags from the URL params or stored earlier in a cookie.

```js
cx.setApplySource('linkedin');
cx.setApplyTags('linkedin,campaign-abcd');
```
---

## Notes for Integrators

- Cookies are automatically read when the module initializes.
- All other fields are page-specific and sourced from the WordPress vacancy post (reloaded fresh per vacancy view).

---
