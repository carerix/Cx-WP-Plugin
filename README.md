Carerix WordPress Plugin
----------------

Demo website at [plugin.carerix.com](https://plugin.carerix.com/) \
After installation [Authorisation of the Plugin](#authorisation-of-the-plugin-for-the-specified-carerix-application)

## 1. Introduction

The Carerix WordPress Plugin converts vacancies and candidates from Carerix to WordPress Posts (posts), making use of the power of WordPress.
Applications for each Vacancy are automatically processed in Carerix.
This means more flexibility and a big performance boost. The plugin therefore works ideally for responsive websites, and also ensures search engine optimized vacancies on your website.


### Features

* Show Carerix Vacancies (Publications) as WordPress Posts
* Create your own (custom) layout for Vacancy posts (with shortcodes and HTML)
* Create your own (custom) Application Form (select and reorder form fields)
* Show multiple overviews of Vacancy posts from different sources
* Job Alert
* Support for Multilingual websites
* SEO Optimized
* Google for Jobs
* Diagnostic tools

### Roles & rights
The Carerix WordPress plugin is the connection between the Carerix application and the WordPress website. Therefor there are certain roles/rights for different tasks:
* **Carerix administrator**: Has the administrator user role and is able to manage the Carerix data-tables (e.g. Country table), mediums and email templates.
* **Wordpress administrator**: Webbuilder with rights to manage the settings of Wordpress, can install/configure plugins and knows how to create/edit pages (with sidebars). HTML skills are useful


Table of Contents
=================

* [1. Introduction](#1-introduction)
  * [Features](#features)
  * [Getting Started](#getting-started-a-basic-guide-to-using-the-plugins-core-functionalities)
  * [Roles & rights](#roles--rights)
* [Installation & Configuration](#installation--configuration)
  * [System Requirements](#system-requirements)
  * [Installation Steps](#installation-steps)
  * [Usage in Email Templates](#usage-in-email-templates)
* [3. Settings & Usage](#3-settings--usage)
  * [Application Forms](#application-forms)
  * [Sources](#sources)
  * [Shortcodes Reference](#shortcodes-reference)
  * [Medium](#medium)
  * [Taxonomies](#taxonomies)
  * [Job Alert Subscription](#job-alert-subscription)
* [4. Advanced Features](#4-advanced-features)
  * [Diagnostics](#diagnostics)
  * [Multilingual Websites](#multilingual-websites)
  * [Without multilingual plugin](#without-multilingual-plugin)
  * [Special multilingual jobs](#special-multilingual-jobs)
  * [Extra/Additional Carerix fields support](#extraadditional-carerix-fields-support)
  * [Google for Jobs](#google-for-jobs)
  * [Job Conversion Tracking](#job-conversion-tracking-for-web-analytics)
* [5. FAQ (Frequently Asked Questions)](#5-faq-frequently-asked-questions)
* [6. Support](#6-support)
  * [Required and recommended specifications](#2-required-and-recommended-specifications)
  * [Updating the Plugin](#updating-the-plugin)
  * [Uninstall the Plugin](#uninstall-the-plugin)
  * [Create RSS feeds per category](#create-rss-feeds-per-category)
  * [Applicant Source Tracking](#applicant-source-tracking)

## Latest release

> [!Tip]
> Download the [Latest Release of the Carerix WordPress plugin](https://github.com/carerix/Cx-WP-Plugin/releases)

# Installation & Configuration

1. Download and install the [latest plugin version](https://github.com/carerix/Cx-WP-Plugin/releases)
2. Configure permalinks in WordPress: **Settings → Permalinks** (choose any structure except plain)
3. Set up required email templates in Carerix:
   | Template | Purpose |
   |----------|---------|
   | CxpeForgotPwd | Password recovery |
   | CxpResetPwd | Password reset |
   | JobAlert | Job alert emails |
   | web-subscribe | Job alert signup confirmation |

4. Authorize the plugin with your Application Token

> [!IMPORTANT]
> ## Authorisation of the Plugin for the specified Carerix application
> 
> The plugin needs to be authenticated with the Carerix application. Therefor you need the Application name (which can be derived from **applicationname**.carerix.net) and the Application Token. 
> 
> The Admin of a Carerix application can generate an Application Token. If you don't have access to the Carerix application you can ask an admin. He can provide you the Application token using the email template 'Application Token'.
> Or request a token via our Helpdesk ([support@carerix.com](mailto:support@carerix.com)) \
> Carerix will not be able to provide you the Application token directly, as this is part of the authorization procedure.

5. Configure ApplyURL in Carerix:
> [!IMPORTANT]  
> ## Configure ApplyURL
> The ApplyURL setting ensures candidates can apply to vacancies directly from emails, job alerts and newsletters. Without proper configuration, application links won't work correctly.
> 
> In Carerix, configure the ApplyURL setting:
> 1. Go to **Settings** → **Attributes and fields** → **Apply_url**
> 2. Set the URL format:
>    ```
>    https://yoursite.com/?pub_id=<cx:write value="$publication.publicationID"/>
>    ```

### Usage in Email Templates
To create links to vacancies in your Carerix email templates, use:
```
<cx:write value="$publication.publicationID"/>
```
This generates URLs like: `https://yoursite.com/pubid/123`

Common use cases:
- Job alert emails
- Application confirmation emails
- Recruiter newsletters
- Social media sharing


# 3. Settings & Usage
## Application Forms

By default a form named Form 1 is ready for use. This default form can not be changed. Create your a new form if you want to customize your application form:
1. Each apply form can also be used for different kind of publications (see settings under [Sources](#sources --> Apply Form) )
2. The **Synchronize with Carerix button** checks if fields that use values from the Carerix System are available. For example, if it can not find any values for the Nationality field, that field will be disabled.
3. Set each fields to Visible of Required
4. You can reorder fields with drag and drop and you can drag & drop whole sections (on the right side)
5. Copy paste the shortcode of the form to the page where you want to use it as an 'Open Application form', for example:
```
[cx_open_application openFormID="2"]
```

See [Application Shortcodes](#application-shortcodes) for details


### Settings of a (custom) Application Form
You can create a new form and link it to the desired Job feed source. For each form you can synchronize the fields from Carerix.
Note that you must first save the title of the form before you can synchronize. You can compose each form yourself by or (un)checking the appropriate (and/or required) fields.

* 🔴 CHECKEN: KLOPT DIT NOG (Dit is nu toch een shortcode?): Show login link: set to Yes by default. If enabled, it generates the login link in the job details page.
* Extra apply options: Set to no by default. If enabled it generates the Apply with Linkedin link
* Address format: International / Dutch. For Dutch each field is split on it's own form field while for International the entire addres can be inserted in one textarea.
* Agreement link (No agreement link by default):
    * Insert desired text in the “Agreement Label” and in “Agreement text” fields to display the link.
    * Insert an URL to be associated with the agreement text url. If Agreement URL field is filled it takes precedent over the Agreement text.
* Captcha: Choose to display the Captcha code
* Advanced: Clear Datanodes Cache. If you made a change in the Carerix System to one of the DataNodes used here, you should clean the cache.


## Sources

Configure how vacancies appear on your site:
1. Template layout
2. Apply form selection
3. Medium settings
4. Location display options

> [!TIP]
> Use different mediums (web, web2, etc.) to separate vacancy flows

### Configuring a Job source

### Adding New Source
1. Click `Add New` button
2. Configure settings
3. Click `Synchronize` to update

> [!note] 
> - Deleting sources keeps existing job posts
> - Changes require synchronization to become effective

### Source Settings
| Setting | Description |
|-------|-------------|
| Source name | Identifier for the source configuration |
| Publications Details Options | Settings for vacancy post display and interaction |
| Apply Form | Select the application form for this source |
| Title - Location | Toggle work location display in title |
| Alternative Feed Parameters | Set custom medium code for different vacancy sets |
| Header and Footer | Add content using shortcodes |
| Excerpt | Custom summary for listings and previews |
| Details Body | Content structure using|

Use the [Shortcodes for Sources](#shortcodes-used-in-sources) in combination with Html to create your own template.

## Medium
Medium 'web' is default, but you can show a different 'job flow' on the website. For example, a list of ZZP projects or jobs per establishment, all published to medium 'web2'.
You can do this by publishing to a different medium. You use this medium as follows:

### In Carerix
1. Create a new medium (e.g. `web2`)
2. Publish test job using new medium

### In WordPress
1. Go to: `Carerix Plugin → Settings → Sources`
2. Add new source
3. Set as medium parameter: (e.g. `medium=web2`)
4. Save changes

### What Happens
- Plugin creates new job category matching medium name
- Jobs appear under a new category
- Use WordPress tags/categories to display jobs

> [!NOTE]
> Leave main medium (`web`) blank in plugin settings


## Shortcodes Reference

### Application Shortcodes
These shortcodes handle the application process.

| Shortcode & Examples | Description |
|---------------------|-------------|
| `[cx_open_application]` | Basic usage: Insert in any page content |
| `[cx_open_application openFormID="XX"]` | Use specific form - Replace XX with Form ID from Carerix → Application Forms |
| `[cx_open_application openpubid="XX"]` | Link to specific vacancy - Replace XX with Publication ID |
| `[cx_open_application openFormID="3" openpubid="312"]` | Combine parameters for specific form and vacancy |
| `[cx_job_alert_subscription]` | Job alert signup form with parameters: `frequency="daily\|weekly\|monthly" confirmation_message="..." confirmation_url="..."` |
| `[cx_google_for_jobs]` | Structured data for Google Jobs |

### Shortcodes used in Sources
Under 'Sources' you can use many shortcodes to built your Vacancy template.
That means you can use them in the Excerpt, Header, Body or Footer of the Publication post.
Also see the [#Common parameters] to use with these shortcodes.

#### Basic shortcodes for Vacancy template
These shortcodes are typically used in the main content sections of a vacancy.

| Shortcode | Description | Parameters |
|-----------|-------------|------------|
| [cx_intro_information] | Introduction text | Common parameters |
| [cx_vacancy_information] | Position description | Common parameters  |
| [cx_requirements_information] | Requirements description | Common parameters  |
| [cx_offer_information] | What the employer offers | Common parameters  |
| [cx_company_information] | Organization description | Common parameters  |
| [cx_function_contact_information] | Contact info for questions | Common parameters  |
| [cx_application_contact_information] | Application contact person | Common parameters  |
| [cx_apply_button] | Apply button linking to form | - |
| [cx_apply_form] | Embedded application form | - |

Furthermore these shortcodes can be used in vacancy templates to display job details. Some have specific parameters besides the common parameters.

| Shortcode | Description | Special Parameters |
|-----------|-------------|-------------------|
| [cx_job_title] | Job title | Common parameters |
| [cx_organization] | Company/organization name | Common parameters |
| [cx_country] | Country/countries | `separator=", "` |
| [cx_region] | Region(s) | `separator=", "` |
| [cx_work_location] | Work location | Common parameters |
| [cx_work_postal_code] | Postal code | Common parameters |
| [cx_workplace_type] | Workplace type (Remote/On site/Hybrid) | Common parameters |
| [cx_employment] | Contract type | Common parameters |
| [cx_hours_per_week] | Working hours | Common parameters |
| [cx_education] | Educational requirements | `separator=", "` |
| [cx_professional_level] | Required professional level | Common parameters |
| [cx_function_group] | Function group | Common parameters |
| [cx_function_position] | Position within function group | Common parameters |
| [cx_field] | Area of expertise | Common parameters |
| [cx_sector] | Business sector | Common parameters |
| [cx_industry] | Industry | Common parameters |
| [cx_salary] | Salary range | `show="csu"` |
| [cx_publication_id] | Carerix publication ID | - |
| [cx_vacancy_code] | Vacancy reference code | - |
| [cx_medium] | Publication medium code | `type="code"` |
| [cx_end_date] | Publication end date | Common parameters |
| [cx_apply_until] | Final application date | Common parameters |
| [cx_job_group] | Vacancy group(s) | `separator=", "` |
| [cx_extra*] | Display custom Carerix fields | `field="fieldcode" separator=", " type="string\|date"` |

### Common Parameters
Many shortcodes accept these standard parameters:
| Parameters | Description |
|-----------|-------------|
| `container="div\|span"` | Wrapper element type |
| `label="yes\|no"` | Show/hide label | 
| `heading="h1..h6\|div\|span\|no"` | Heading element type |
| `content="yes\|no"` | Show/hide content |
| `class="..."` | Custom CSS classes |
| `raw="yes\|no"` | Output raw data |
| `quotes="double\|single"` | Quote style for attributes |


For example you can use a shortcode like this:

```
[cx_application_contact_information container="div" label="yes" 
heading="h3" content="yes" class="contact-info" raw="no" quotes="double"]
```

### Deprecated Shortcodes
The following shortcodes are no longer supported:
- [cx_rss_for_all]
- [cx_print_link]
- [cx_login_form]
- [cx_newsletter_subscription]
- [cx_social_icons]
- [cx_vacancy_number]


## Taxonomies
The plugin automatically creates these job taxonomies in WordPress:

| System Name     | Display Name         |
|----------------|---------------------|
| cx_country     | Country            |
| cx_region      | Region             |
| cx_education   | Education Level    |
| cx_funcgroup   | Function Group     |
| cx_function    | Function           |
| cx_location    | Work Location      |

**🔴 Deze worden toch automatisch gegenereerd. Kun je hier nog iets mee instellen? Vanuit Carerix de naam bepalen bijv?**

In order to use the taxonomies as filters for the 2 types of posts, the names of the taxonomies must be distinct. Otherwise, if common, the values of the taxonomies will be displayed for both type of posts and the user will experience that after sellecting a taxonomy no result will be returned.

Default resources are used to generate the names of the taxonomies. The language applied will follow the language of the plugin.

Define your own values for the taxonomies creating for each languge a different / new value to overwrite the default ones filled from resources.



## Job Alert Subscription
In WordPress you can show a form for job alerts (vacancy subscription). When candidates signup they will receive emails in the future containing vacancies that fit their selected criteria, on a daily basis.

1. Setup in Carerix: [See guide](https://help.carerix.com/en/articles/1954170)
2. Required email templates: `web-subscribe`, `jobalert`
3. Create a standalone Job Alert Subscription page, use this shortcode on a regular WordPress page:

```
[cx_job_alert_subscription frequency="daily|bidaily|tridaily|twiceweekly|weekly|biweekly|monthly"
confirmation_message="Thank you for subscribing. Shortly you will receive an email with an activation link.
After activation you will start receiving new job opportunities in your mailbox on a daily basis!"
confirmation_url="/jobalert_thank_you/"]
```

For the following instructions you need to have Admin rights in Carerix and be familiar with [Carerix Table](https://help.carerix.com/en/articles/1810726) editing.


### Prerequisites
1. Configure Job Alerts in Carerix ([Setup guide](https://help.carerix.com/en/articles/1954170))
2. Required email templates:
   - `web-subscribe`: Subscription confirmation
   - `jobalert`: Daily/weekly job alert emails

### Form Fields
- Email address
- First/Last name (with prefix)
- Gender
- Country preferences (if multiple available)
- Three region preferences (provinces/counties/departments)
- Two function group preferences with optional business-line selector
- GDPR agreement checkbox
- Captcha anti-abuse system

### Subscription Process
1. Candidate submits form with job preferences
2. Receives opt-in activation email
3. Clicks activation link to confirm subscription
4. Starts receiving job alerts matching their criteria
5. Can unsubscribe via link in alert emails

### Customizing Job Alert Selection Options
Access Carerix Tables to customize dropdown options for the Job Alert:

1. **Countries** (table: 'Land')
   - Uncheck "not for web" to hide unwanted countries
   - Single enabled country removes dropdown entirely

2. **Business Lines** (table: 'Vakgebied/Business line') 
   - Enable "not for web" for unused business lines
   - Keep "Standard" business line with "not for web" disabled
   
3. **Function Groups** (table: 'functie 0 / function 0')
   - Enable desired groups and connect to business lines
   - Disable "not for web" for groups to display

After modifying tables, clear cache: **Dashboard → Carerix → Application Forms → Settings → Clear DataNodes cache**


# 🔴 4. Advanced Features

* 🔴 For developers or experienced users, this section can cover:
    * Hooks and filters used by the plugin.
    * Custom functions available.
    * Integration with other plugins or WordPress APIs.

## Diagnostics

The jobs synchronizing process will be fully handled by the REST API. The diagnostics tool (**Wordpress Dashboard** → **Carerix** → **Settings** → **Tab Diagnostics**) will help you find possible inconsistencies between published vacancies in your Carerix system and the vacancies that are retrieved by your Wordpress site.

You can review the 'active job publications' but also the available 'medium codes'.
* General plugin (version) information (Active mediums, Open application found, etc)
* Active job publications (synced from Carerix, with Pub ID, Title, start date, Visibility sensitive data)
* Available mediums (in Carerix)

## Multilingual Websites

The Carerix WordPress plugin supports multilingualism. To do this, you use a multilingual plugin. Carerix supports [Multilingual Plugin WPML](http://wpml.org/), the most popular plugin on multilingualism. We assume that you all vacancies in both Dutch as a 2nd language publishing (English in this example). Proceed as follows

1. Make Carerix in another medium (in tables). You've already medium 'web', add a new medium to eg code web-en 'for English.
2. Create an additional publications of a job
3. One publication (1st language) already has the medium `web`. Make an extra publication of the same job and web (2nd language) with it. Please note that this publication contains the texts in the 2nd language.
4. Go to the WordPress Website
5. Install WPML and adjust it as desired
6. Go to the Carerix settings and synchronize all items Carerix
7. In the list of all messages (posts) you can see which posts have been published in any language

Use the medium code 'web-XX', where 'XX' is the ICU Locale language.

The Carerix plugin works perfectly with WPML, one of the best WordPress plugins multilingual. The price WPML is worth it, see [WPML](https://wpml.org/)


## Without multilingual plugin
IMPORTANT! You can do steps below only in case when WPML plugin is NOT installed. If you have WPML plugin please skip this section!

You can also show jobs from different languages ​​(different mediums) without multilingual plugin:

1. Create a medium (per language) a separate job to feed source,
2. On Set Feed Source Parameters Add `medium=web` and as parameter behind `/cxtools/wp_feed.php?`
3. You now have several job feeds, jobs are created as separate jobs in the'd really rather know categories. The page is created only displays the jobs with the medium 'and web.


## Special multilingual jobs
🔴 CHECKEN
Need to display job postings in multiple languages on your website? This guide explains how to configure multilingual job publications while keeping your main website in a single language.

### Configuration 
1. Carerix:
   - Create/verify language-specific mediums (e.g., 'web-en' for English)
   - Create job publications using these mediums

2. WordPress Plugin:
   - Add new source in plugin settings
   - Set feed parameter: `medium=web|web-en` (replace web-en with your language code)

### Examples
- Dutch + English: `medium=web|web-en`
- Dutch + German: `medium=web|web-de`
- All: `medium=web|web-en|web-de`

### ⚠️ Notes
- Headers auto-generate in medium's language
- Use dashes (-) only for language codes
- Correct: `webagency2`
- Incorrect: `web-agency2`

Medium codes with dashes will be interpreted as language indicators, resulting in language-specific formatting.


## Featured vacancies
You can find the feature in **Carerix Dashboard→Carerix→Settings→ Technology previews**

In the Carerix system extra/additional fields can be added to Job orders and Publications. The information from these custom fields can be displayed in your vacancies. You can also use it as options in a “vacancy-listing search & filter” widget.

**Use case**
A nice use case is a “featured/highlighted” vacancy widget to highlight some vacancies. Therefore in Carerix you need to create an additional field called “featured on website” (type single checkbox) and attach it to the “Publications entity”.
In Carerix, recruiters can tag preferred publications as “Featured on website”.

The Wordpress developer can create a "Featured vacancies section" based on a “vacancy post loop” restricted to the custom-field “featured on website”.


## Google for Jobs
Google for Jobs is an enhanced search functionality from Google. It aggregates listings from job boards and vacancy sites and displays them prominently in Google search.

You need to add “structured job posting data” to have your jobs included to these listings. This information is invisible, so your job pages are still looking the same. When Google is indexing your site, the structured data is recognized and added to Google for Jobs.

### Overview
Adds structured job data to your pages for Google Jobs search integration.

### Setup
1. Enable Integration
   - Navigate: `Carerix → Settings → Google for jobs`
   - Check "Google for Jobs support"
   - Save changes

2. Test Implementation
   - Open any vacancy page
   - Use [Google Structured Data Testing Tool](https://search.google.com/test/rich-results)
   - Verify "JobPosting" entity appears

### Hiring Organization Config
- For anonymous jobs: Set your company as hiring org
- Navigate: `Carerix → Settings → Google for jobs`
- Configure:
  - Company name
  - Logo (optional)


## Web analytics
The plugin supports custom code snippets for extended web analytics usage (e.g. Facebook pixel, Google Analytics, etc.). Apply custom (javascript) code to the following webpage sections:

* General (basically to all pages)
* Job description page
* Job application page
* Job application confirmation page

Additionally custom information (apply source and apply tags) can be set which will be stored in the “Candidate Match file”.

### Prerequisites
- WordPress admin access
- JavaScript knowledge

### Configuration
1. Go to: `WordPress Dashboard → Carerix → Settings → Conversion tracking`
2. Add tracking code in script boxes

### Available Features
- Global `cx` object with vacancy data
- Methods: `cx.setApplySource()`, `cx.setApplyTags()`

> [!TIP]
> You can also dump this information in your browser debug console by entering console.log(cx); at a vacancy description page.

## Applicant Source Tracking
The apply page supports the following GET parameters `cx_applysource` and `cx_applytags`

## Usage example
```
https://yoursite.com/vacancy/1234/apply?cx_applysource=Google&cx_applytags=jobboard.nl,paid,regionA
```
> [!NOTE]
> - Tracking data saves in 30-day cookie
> - Data auto-adds to all applications from same candidate
> - Appears in Carerix under Match details
> - Add apply=true parameter if using custom URLs:

```url
https://yoursite.com/vacancy/ID/apply

```

## Create RSS feeds per category
Build an RSS feed for all your jobs as posts in WordPress or build a Feed for each Category or any tag. Use the built-in feature of WordPress for generating feeds.

Example: Build the feed for **category = marketing** on website:

```
https://yoursite.com/category/marketing/feed
```

This will result in a standard RSS page containing all posts from category ''marketing'' as generated by the Carerix plugin.


## 🔴 CHECKEN: How to use the 'cxwordpress_post_updated' hook?
```
With this hook you can apply changes to a vacancy-post upon (creation/update) to have it better fit into your site/theme. It's useful to apply changes in text formatting or post-statuses.
Example, edit the file 'functions.php' in your activated child theme. Add the following:
function my_cx_post_preparation(array $postids, array $data, array $cxfields ) { $post_id = (int) $postids[0]; // First item is the WP post ID $post_data_v1 = $data[0]; // The original data that the CX WP plugin has saved/updated $_post = get_post( $post_id ); // Another way to access the post data $post_cxfields = $cxfields[0]; // First item holds an associative array of retrieved (raw) CX fields $pub_id = get_post_meta($post_id, 'guid', true); // CX publication ID // Example to retrieve some specific CX fields $cx_requirements = get_post_meta($post_id, 'requirementsInformation', true); $cx_function_group = get_the_terms($post_id, "functiongroups")[0]->name ?? ""; $cx_function_name = get_the_terms($post_id, "functions")[0]->name ?? ""; $cx_min_salary = $post_cxfields['minSalary'] + 0; $cx_max_salary = $post_cxfields['maxSalary'] + 0; $cx_period_salary = $post_cxfields['salaryPeriodClassification']; // MonthTag = per hour, HourTag = per month, etc. // Example to update the post content $_post ->post_content = "< h1 >Hook `cxwordpress_post_updated` altered this post contents!</ h1 >" . $_post ->post_content; wp_update_post( $_post ); // Update post // Example to set post meta info. This is specifically for posts in the Divi theme. Note "_et" is an abbreviation for Elegant Themes. update_post_meta( $post_id, '_et_pb_page_layout', 'et_full_width_page'); // force Divi post as a full width page update_post_meta( $post_id, '_et_pb_show_title', 'off'); // turn Divi post titles off // Clean cache wp_cache_delete( $post_id, 'posts' ); } // Add the hook with prio 3 (default) and accepting 3 arguments
add_action( 'cxwordpress_post_updated', 'my_cx_post_preparation', 10, 3);
```


## 🔴 CHECKEN: New method for language edits
You need (s)FTP credentials for the WordPress website to do this. The idea is to override portions of the plugin's language file within your own child theme. That way you are sure the language modifications aren't reverted when a new plugin version is released.
In this example we will change the heading text “Introductie” (introduction) which appears in the vacancy texts. We assume you've set the Wordpress site language to Dutch and have the site running in a child theme.

**1. Create a blank PHP-file called**

`nl-NL.resources.php`

in {WORDPRESS-ROOT}/wp-content/themes/your-child-theme/CxWordpress/assets/resources/ Change your-child-theme to your child theme directory name and create the subdirectories (CxWordpress/assets/resources) if needed.

**2. Edit the new file**

'nl-NL.resources.php as follows'
```
;<?php die()?> [CxPortal.message.field] introduction = "Intro (formerly Introductie)" requirements = "Wat neem jij mee? (formerly Functie-eisen)" offer = "Wat bieden wij? (formerly Aanbod)" organization = "Over deze werkgever (formerly Organisatie)" function = "Wat ga je doen? (formerly Functie)" information = "Meer informatie (formerly Inlichtingen)" application = "Solliciteren bij (formerly Sollicitatie)" closingDate = "Sluitingsdatum (formerly Sluitdatum)" [general.button] apply = "Versturen (formerly Solliciteren)"
```
**3. Do a full sync from Carerix to regenerate the job posts**

**Wordpress Dashboard** → **Carerix** → **Settings** → **Button** “Enforce full sync of all items from Carerix” or “Synchronize new/changed items from Carerix”

**Notes**:
* Our new file nl-NL.resources.php is based on {WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/assets/resources/nl-NL.resources.php. You can copy all desired elements from there to your own resource file.
* Each section of language elements starts with a section heading [xxxxxxx] (recognized by the brackets).

### How do I show the vacancies in other languages ​​on a multilingual website?
See [Multilingual Websites](#multilingual-websites)

# 5. FAQ (Frequently Asked Questions)

### How do I get the Application Name and Token?
* Application name is the first part of the customers application: `applicationname.carerix.net`
* For the Application Token see: [Application Token](#authorisation-of-the-plugin-for-the-specified-carerix-application)

### Why don't I see any vacancies?
Jobs are displayed under the following conditions (You need Carerix administrator):
* In Carerix, the medium-code of publications have to be set to web
(or intentionally match a custom medium-code which is used in the plugin)
* Last publication date is on or after today. Please note, check if necessary in the Carerix application:
    * Publication Basic tab: Last publication date
    * Publication Admin tab: Closing date
    * Job: Start Date

You can always verify if publications have been synced during the last sync via the diagnostics tool (**Wordpress Dashboard** → **Carerix** → **Settings** → **Tab Diagnostics**)


### Can I edit the job posts?
Yes and No: You can manually add a Featured Image (open the job post and add Featured image). But be aware that manual changes in the job posts texts are overridden by the next vacancy sync, but as the featured image is not part of vacancy syncs it won't be removed)
You can check by forcing a manual sync: Located in **Wordpress → Dashboard → Carerix → Settings → Tab Settings → Button** '**Synchronize new/changed items from Carerix**'.

### Can I show a featured image in a vacancy post?
Yes, you can manually add a Featured Image. Simply open the job post and add Featured image. You need editing rights in WordPress. 
Be aware that manual changes in the job posts texts are overridden by the next vacancy sync, but as the featured image is not part of vacancy syncs it won't be removed.

### Can I show the application form below the vacancy texts?
Yes, go to **Wordpress Dashboard** → **Carerix** → **Sources**
In the 'Publication Details Header/Body/Footer' (or in the Header or Boday) of a source, you can use HTML and Shortcodes to build your own template. 
For example use the shortcode `[cx_apply_form]` (instead of `[cx_apply_form]` which generates a button) in the Publication Details Footer.

### Can I add an image within the paragraphs of the vacancy texts?
Yes, you can add HTML or a shortcode in the publication text in the Carerix application. 
Be aware that the Carerix user would need a little bit of HTML experience to add this to the publication text.
1. In the Carerix application open the publication text where you want to add the image
2. Switch the editor to HTML mode
3. Insert the HTML-image-tag in the HTML source code. For example:
``<img src="https://carerix.com/.../carerix-logo.png" alt="ALT Text" />``
4. Save the changes
5. Sync the WordPress plugin on the website

### Can I add a youtube video in the vacancy text?
Yes, you can add HTML or a shortcode in the publication text in the Carerix application:
use for example: 
* ``https://www.youtube.com/watch?v=4bUS0k5L6v8`` 
* or ashortcode like `[embed width="600px"]https://www.youtube.com/watch?v=4bUS0k5L6v8[/embed]`

### It seems as if one or more jobs do not sync?
Perhaps you have moved jobs to the trash. Remove them permanently from the trash. After synchronization, they are recreated again and will be visible.

Make sure to do a full jobs sync by clicking on the “**Enforce full sync of all items from Carerix**” button.

### Can I create a custom text confirmation or confirmation page?
Yes, follow these steps:
1. Go to **Wordpress Dashboard** → **Carerix** → **Applicaton Forms** and open the desired form
2. At the of the form select 'Confirmation message' if you want a standard confirmation text. 
3. If you want to refer to a specific WordPress page. You can choose to enter a URL.

### Can I monitor conversions with Google Analytics?
Yes, absolutely:
* Make sure the Google Analytics (page) tracker code is already present for all site pages
* Create a specific Wordpress page as confirmation page
* In Google Analytics you can track the statistics of this page
* You could also add this confirmation page as one of your Goals

🔴 CHECKEN: Also see [Applicant Source Tracking](#applicant-source-tracking) for tracking candidates in Carerix throughout their application process.

### How to search / filter by taxonomy?
Jobs include taxonomy by Country and Region, Function and Training. Use those taxonomies in your  Search & Filter widgets of plugins.

### 🔴 CHECKEN: Can I use a search radius from a postal code area?
With the 'Carerix Search widget' it is possible to search by radius. These can be found under Wordpress → Dashboard → View → Widgets. You need WordPress editing rights. However, if you use a third party search-plugin (like Search & Filter or Jet SmartFilters) you cannot use this radius function because of technical limitations.
See the example in https://demo.carerix.com/plugin/zoeken-filteren/


### Can I change the Layout or styling of the vacancies?
Yes, the plugin has minimal styling so it basically follows the theme used. Additionally, you can build your own template layout of the vacancies with HTML and Shortcodes in 'Publication Details Header/Body/Footer within the source.

### Can I change the text of the headings, labels, buttons for vacancy texts and application forms?
Yes you can! You can build a template with the use of shortcodes in combination with HTML.
(see [Sources](#sources))

### Can I offer an RSS feed of all job vacancies or by function?
Yes, you can use standard WordPress RSS feeds. The URLs for this example:
* /category-name/publications/feed /
* /tag/utrecht/feed/

For example https://plugin.carerix.com/category/vacatures/techniek-engineering/feed/

### Can I submit a sitemap to Google Search Console?
Yes, use the following URL:
https://yoursite.com/?carerix_sitemap

### When I enable 'Google For Jobs' why do I get warnings from a (structured data) testing tool?
These are warnings and not blocking errors.

Google recommends you to provide detailed information about the vacancies. At the moment it's not possible to fully map the Carerix vacancy information to the Google For Jobs structure. But the most important data is covered.

Also, Google For Jobs wants to know the address location of the jobs. Not all customers want to reveal this because it's sensitive business information. Therefor this high level of detail is left out.

### Can I customize the labels in the URL (such as ../category/, ../publications/ etc)?
No, this is not possible

### Why should I enable this: 'Reporting its location'?
We can continue to make the plugin better and better with the necessary feedback that we receive from the plugin. No vacancy or candidate data is send, so there is no privacy issue, and it gives no performance issues.

### How to enable logging and where is the logfile?
You can enable the logging in Wordpress → Dashboard → Carerix → Settings → Tab Settings. The logfile is created in
{WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/tmp/logs/
> [!WARNING] 
> The logfile directory can grow fast in size which may lead to your site running out of disk space. So make sure you **only** enable it if you experience problems.

### Where are the uploaded documents?
Candidate documents (e.g. a CV because of a job application) are submitted to the Carerix system, but temporarily uploaded to the following folder to process it:
{WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/tmp/uploads/
After a few hours the files are automatically removed by the plugin and will only reside in the Carerix system.
> [!WARNING]
> Make sure you have disabled “developers logging” (see above), because candidate details (needed for debugging) are stored in the logfile too.


### Why does the plugin not use Custom Post Types instead of regular posts for Vacancies?
**Pro's**
* Templates: Web builder can use a custom template specifically for job post types.
* Filters: 3rd Party filters specifically for Custom post types are set
* Consistency: Difference between news and jobs is clearly in the admin area.

**Cons**
* Blog post listings: It is not possible to show vacancies in major blog listing.
* Compatibility: Switch between regular and post types Custom post types can cause synchronization problems.


Currently we have chosen not offering Jobs as Custom Post Types because many of our customers use the standard features like blog listing.


🔴 [TO DO LATER: FAQs]


# 6. Support

* 🔴 [Github issues](https://github.com/carerix/Cx-WP-Plugin/issues)? Provide information on where users can get help, such as a support forum, email address or via ticketing system.
* Give a clear description of the issue 
* Use screenshots and visuals to enhance clarity.
* Include clear code snippets if necessary.
* Make sure not to send confidential information

## Disclaimer
**Altering the plugin**
If someone alters (the code of) the plugin this will invalidate any form of support. Carerix can not support customizations. Also customizations will be lost at each update of the plugin!

_____________

## 2. Required and recommended specifications

## System Requirements

**Mandatory**:
* Linux OS with Apache 2.x (NGINX not supported)
* PHP 7.4 - 8.2 with cURL, OpenSSL, JSON
* MySQL 5+ / MariaDB
* PHP Memory: 256MB recommended (128MB min, 512MB+ for complex sites)

### **Updating the Plugin**

1. Make sure to make a backup of your website before updating the plugin which is good practice for updating WordPress plugins. Also check your Website after updating.
2. In Wordpress dashboard → Plugins, locate the Carerix Wordpress Plugin
3. If there's an update available you can click on the 'Update now' link

### **Install the Plugin**
* Make sure the hosting environment meets the technical requirements
* Go to **Plugins** → **Add New** → **Upload**
    * Upload the archive you have just saved
    * Click **Install**
* When the upload is completed, click on the **Activate Plugin** link
* Go to the **Settings** → **Permalinks** panel and choose any of the options listed.
* Do NOT put your site url in the permalinks field. You must use one of the structure tags, or a combination of tags only.
    * Make sure you don't cache the Vacancy Posts with caching plugins like W3 total cache, Comet cache, Rocket cache.
* Check your Administration Panels or WordPress blog to see if the Plugin is working.
* Follow the instructions in the Settings section to setup the plugin.

### **Uninstall the Plugin**
* Deactivate
    * Go to Plugins section
    * Find the plugin,
    * Click on **Deactivate**
* Remove the plugin
    * Go to Plugins section
    * Find the plugin,
    * Click on **Deactivate** (if the plugin is active)
    * Click on **Delete**


_____________

> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

_____________
`````
