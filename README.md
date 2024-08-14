Carerix WordPress Plugin
----------------

See Demo & Tips at <a href="https://plugin.carerix.com" target="_blank" >plugin.carerix.com</a>


## 1. Introduction


* Carerix Wordpress Plugin v3.1.2.2
* The Carerix WordPress Plugin converts vacancies and candidates from Carerix to WordPress Posts (posts), making use of the power of WordPress. 

    This means more flexibility and a big performance boost. The plugin therefore works ideally for responsive websites, and also ensures search engine optimized vacancies on your website.


### Features

* Show Carerix Vacancies as WordPress Posts
* Job Alert
* Create your own (custom) layout for Vacancy posts
* Create your own (custom) Application Form
* Show multiple overviews of Vacancy posts from different sources

* SEO Optimized
* Google for Jobs
* Support for Multilingual websites
* Diagnostic tools


## 2. Installation

**Mandatory**:

* Linux OS
* Apache 2.x (NGINX is not supported)
* PHP 7.4 - 8.2
    * cURL
    * OpenSSL
    * JSON
* MySQL 5 or higher / MariaDB

**Recommended PHP memory limit:**



* 128 MB (for sites with lightweight themes / few plugins)
* 256 MB (for regular sites)
* 512 MB or higher (for sites with heavy weight themes/ many plugins)

## Latest release

**May 2023**
The (latest) Carerix Wordpress Plugin has been tested for Wordpress versions up to 6.2



## **Updating the Plugin**

1. Make sure to make a backup of your website before updating the plugin which is good practice for updating WordPress plugins. Also check your Website after updating.
2. In Wordpress dashboard → Plugins, locate the Carerix Wordpress Plugin
3. If there's an update available you can click on the 'Update now' link


## **Uninstall the Plugin**

* Deactivate
    * Go to Plugins section
    * Find the plugin,
    * Click on **Deactivate**
* Remove the plugin
    * Go to Plugins section
    * Find the plugin,
    * Click on **Deactivate** (if the plugin is active)
    * Click on **Delete**

**Installation Steps**

* Make sure the hosting environment meets the technical requirements
* Go to Plugins → Add New → **Upload**
    * Locate the archive you have just saved
    * Click **Install**
* When the upload is completed, click on the **Activate Plugin** link
* Go to the **Settings** → **Permalinks** panel and choose any of the options listed.
* Do NOT put your site url in the permalinks field. You must use one of the structure tags, or a combination of tags only.
    * Make sure you don't cache the Vacancy Posts with caching plugins like W3 total cache, Comet cache, Rocket cache.
* Check your Administration Panels or WordPress blog to see if the Plugin is working.
* Follow the instructions in the Settings section to setup the plugin.


### Settings Carerix

* Change ApplyURL
* Don't forget to change the ApplyURL, so that links in emailtemplates are directed to the website (Settings → Attributes and fields → Apply_url)

    ```
    https://www.domainname.com/?pub_id=<cx:write value="$publication.publicationID"/>
    ```

    This will link to the according Vacancy publication on the website



### Modified URLs
* Use above cx-script code ```<cx:write value="$publication.publicationID"/>```in your Carerix email templates to Create links to jobs in your emails, alerts and newsletters?
* To generate a link with the correct vacancy page URL: [https://website.com/pubid/xxx](https://website.com/pubid/xxx), where xxx is the pubID \
For example [https://www.website.com/pubid/123](https://www.website.com/pubid/123)


## 3. Usage

* Getting Started: A basic guide to using the plugin's core functionalities.
* Configuration Options: Explain any settings or configuration options available for the plugin.
* Shortcodes or Widgets (if applicable): Provide usage instructions and examples for any shortcodes or widgets included in the plugin.

## 4. Advanced Features (Optional)

* For developers or experienced users, this section can cover:
    * Hooks and filters used by the plugin.
    * Custom functions available.
    * Integration with other plugins or WordPress APIs.

## Create RSS feeds per category

Build an RSS feed for all your jobs as posts in WordPress or build a Feed for each Category or any tag. Use the built-in feature of WordPress for generating feeds.

Ex: Build the feed for **category = publications** on website

like this:


```
https://example.com/category/publications/feed
```


This will result in a standard RSS page containing all posts from category publications as generated by the Carerix plugin.


## Applicant Source Tracking

The apply page supports 2 new GET parameters cx_applysource and cx_applytags as of version 2.14.36


## Usage example


```
https://example.com/vacancy/1234/apply?cx_applysource=Google&cx_applytags=jobboard.nl,paid,regionA
```


NOTE: The apply parameters are being stored in a cookie for 30 days. If the same candidate applies for another vacancy through another URL e.g. When a candidate submits the apply form the tracking values will be automatically saved in Match details and become visible in Carerix application as Apply Source and Apply Tags fields in Matches details.

If your wordpress is configured differently and you are not using default urls, be sure that the redirect from the job board will land on the apply page. Usually it is enough to provide apply=true parameter in the url


```
https://example.com/vacancy/9876/apply
```


The resulting match will be created with previous tracking values.


## 5. FAQ (Frequently Asked Questions)



* Address common questions users might have about the plugin's functionality or troubleshooting.

[TO DO LATER: FAQs]


## 6. Support



* Provide information on where users can get help, such as a support forum, email address, or ticketing system.
 \
Additional Tips:



* Use screenshots and visuals to enhance clarity.
* Include clear code snippets for developers (in a separate section if needed).
* Maintain a consistent tone and style throughout the documentation.



# Technical Information WordPress plugin

See Demo & Tips at[ https://plugin.carerix.com/](https://plugin.carerix.com/)

**Application Token**
The plugin needs an Application Token to authorize the plugin with the Carerix Application (yourapplicationname.carerix.net). The Admin of the Carerix application can use a mailtemplate "Application Token' or request a token via our Helpdesk ([support@carerix.com](mailto:support@carerix.com)) \
Carerix will not be able to provide you the Application token directly, as this is the authorization procedure.


## Carerix WordPress plugin - Technical information


# Installation

To create a new website based on WordPress and connect it to the Carerix System, follow this steps:



1. Download the latest Carerix WordPress plugin
2. Install and configure your WordPress
3. Download the stable version of the CxWordPress plugin


## Installing Email templates

You need to have these email templates installed to make full use of the plugin: Email codes (System, CxWordPress)

Make sure that this e-mail templates are installed in the library of the Carerix application:



* CxpeForgotPwd - e-mail sent to the candidate to resend the login details
* CxpResetPwd - email used to reset the password for a candidate That can no longer access the original email account
* JobAlert - Mandatory for sending job alert subscription emails.


## Change ApplyURL to website

Don't forget to change the ApplyURL, so that links in email templates are directed to the correct Vacancies on the website (Settings →  Attributes and fields →  Apply_url)


```
https://www.domainname.com/?pub_id=<cx:write value="$publication.publicationID"/>
```


This will link to the according Vacancy publication on the website


## Authorisation of the Plugin

The plugin needs to be authenticated with the Carerix application with the Application name and Application Token. 

The Admin of a Carerix application can generate an Application Token. If you don't have access to the application you can ask an admin. He can provide you the Application token using the email template 'Application Token'.


## Location Reporting

If you check the Allow the plugin to report its location, the plugin will periodically send data about the location of where the plugin was installed back to Carerix.


## Synchronizing Vacancies (Publications) from Carerix to your site



1. Automatically every 10 minutes
2. Manually hit the Button: **Synchronize new/changed items from Carerix**
3. Manually hit the Button: **Enforce full sync of all items from Carerix**
4. Go to the external link [https://website.com/?carerix_sync](https://website.com/?carerix_sync) that is available without logging in. After syncing you will see a log file of that last sync.

 \
The data that exists in WordPress is periodically updated (every 10 minutes) to reflect the actual data in the system. You can use the Synchronize Now button to manually initiate the synchronize mechanism, if you want to see the changes immediately.


## Forms



* In the Forms section you can create your own custom apply form.
* Each apply form can also be used for different kind of publications.
* The **Synchronize with Carerix button** checks if fields that use values from the Carerix System are available. For example, if it can not find any values for the Nationality field, that field will be disabled.
* By default a form named Form 1 is ready for use. This default form can not be changed. Create your own form if you want to customize your application form:


## Creating a New Form



1. To create a New Form go to Forms and click on the Add new
2. Give the form a proper name to be able to identify it later
3. Set each fields to Visible of Required
4. You can reorder fields with drag and drop and you can drag & drop whole sections (on the right side)
5. Copy paste the shortcode of the form to the page where you want to use it as an 'Open Application form', for example: \
 \
`[cx_open_application openFormID="2"]`
\
\
also see [Open Application](#heading=h.tglj98aziw6l) for more parameters


## Specify the form for your source

Connect a form to the 'Source' of regular Vacancy posts as follows:



1. Open the Source
2. Under Publication Details Options select the form that you want to use


## Form settings

Show login link: set to Yes by default. If enabled, it generates the login link in the job details page.

Extra apply options: Set to no by default. If enabled it generates the Apply with Linkedin link

Address format: International / Dutch. For Dutch each field is split on it's own form field while for International the entire addres can be inserted in one textarea.

Agreement link:



* Default: no agreement link
* Insert desired text in the “Agreement Label” and in “Agreement text” fields to generate and display the link.
* Insert an URL to be associated with the agreement text url. If Agreement URL field is filled it takes precedent over the Agreement text.
* Captcha: choose in which page to display the Captcha code
* Advanced: Clear Datanodes Cache. If you made a change in the Carerix System to one of the DataNodes used here, you should clean the cache.


## Sources

Under the Sources section you can create one or more Jobs sources. You can use the Default jobs source or you can create new ones. Create a different source if you want to:



* Use a different other settings or a different template lay out for your vacancy posts
* Use a different Carerix  'medium'-code (like 'web' or 'web2' or 'web-en')


## Configuring a Job source

1. Add a new Jobs source click via Add New button.
2. When you Add or edit a Source you need to synchronize to see changes
3. Deleting a source will not delete the generated posts from wordpress.
4. The following fields can be set:

**Source name** \
Helps you to identify the configured source.

**Publications Details Options** \
Here you can set options for how the applicant will see and interact with the vacancy posts generated from this source.

**Apply Form** \
Select the Application Form to be used for this specific Source

**Title - Location** \
Select if you want to show the work location after the Title or not.

**Set Alternative Feed Source Parameters** \
You can specify a different 'medium'-code here. It's useful if you have multiple sites or brands with different sets of vacancies. Therefore these 'medium'-codes are active and in use in the Carerix application.

**Publication Details Header and Publication Details Footer** \
If you want to display details in the footer or the header, use the following shortcodes:


<table>
  <tr>
   <td>
[cx_rss_for_category]
   </td>
   <td>display the rss for the publication category
   </td>
  </tr>
  <tr>
   <td>[cx_rss_for_all]
   </td>
   <td>display the rss for all the publications
   </td>
  </tr>
  <tr>
   <td>[cx_print_link]
   </td>
   <td>display the print link
   </td>
  </tr>
  <tr>
   <td>[cx_function_group]
   </td>
   <td>display the function group
   </td>
  </tr>
  <tr>
   <td>[cx_vacancy_number]
   </td>
   <td>display the vacancy number, as auto-generated in Carerix. However, consider using [cx_vacancy_code] instead
   </td>
  </tr>
  <tr>
   <td>[cx_vacancy_code]
   </td>
   <td>display the vacancy reference code. By default the reference code is equal to the auto-generated vacancy number in Carerix. But if you have changed the reference code in Carerix→Files→Job orders→General, this new entry is displayed
   </td>
  </tr>
  <tr>
   <td>[cx_apply_button]
   </td>
   <td>display the apply button
   </td>
  </tr>
  <tr>
   <td>[cx_apply_form]
   </td>
   <td>display the apply form
   </td>
  </tr>
  <tr>
   <td>[cx_job_alert_subscription_link] (discontinuing in upcoming releases)
   </td>
   <td>display the job alert subscription link
   </td>
  </tr>
</table>

**Publication Excerpt**

Here you can use an alternative/better teaser (summary text) which will be used as a summary, specifically in vacancy overview/listing pages. This excerpt will also be used as intro/description text as preview text on Social Media etc.


**Publication Details Body**

You can use shortcodes like [cx_intro_information], [cx_offer_information] and many more to setup your own vacancy layout template. See the shortcodes in the plugin for exact usage. Please read the accompanying usage explanation in the plugin as you are configuring the job source.



## Special jobs
One language website, multiple languages used for publication texts

You have a website entirely in Dutch but you want to display one or more jobs in a different language? By default, your publications will receive all header sections in Dutch. take the following steps in order to have the labels in the correct language.

**In Carerix:**
1. If an extra medium for language is not already active: Create a medium with the desired code (i.e. 'web-en') for use of publications in the different language of the website.
2. Create publications in this medium in the extra language that you need to publish

**In the WordPress plugin** (under Sources)



1. Create new source to generate your jobs page. **Eg. Page name: Mixed jobs**
2. In the Set Feed Source Parameters section, after the default feed, in the input text insert **Eg. for English:** medium=web|web-en
3. If you want to mix the Vacancy posts from the different languages you can use medium=web|web-en. 
4. Finish the rest of settings and save.

**Result:** Page named **Mixed Jobs** is created. The page will display jobs from the 2 defined mediums.

For the posts for which value of parameter medium is found to be language codes, the resources will be generated in the language code corresponding to language code. 

**NOTE**: If you do not want to use multilanguage-features, never use a mediumcode containing a dash. The Wordpress plugin will interpret it as a language resulting in English subtitles within your vacancies. So if you want to use a medium to separate vacancies for your second agency, use a mediumcode like “webagency2” instead of “web-agency2”


---


## Diagnostics (since v3.0.0)

The jobs synchronizing process will be fully handled by the REST API. The diagnostics tool (Wordpress Dashboard → Carerix → Settings → Tab Diagnostics) will help you find possible inconsistencies between published vacancies in your Carerix system and the vacancies that are retrieved by your Wordpress site.

You can review the 'active job publications' but also the available 'medium codes'.


## Extra/Additional Carerix fields support (since v3.0.0)

You can find the feature in Carerix Dashboard→Carerix→Settings→ tab Technology previews

In the Carerix system extra/additional fields can be added to Job orders and Publications. The information from these custom fields can be displayed in your vacancies. You can also use it as options in a “vacancy-listing search&filter” widget.

**Use case**

A nice use case is a “featured/highlighted” vacancy widget to highlight some vacancies. Therefore in Carerix you need to create an additional field called “featured on website” (type single checkbox) and attach it to the “Publications entity”.  \
In Carerix, recruiters can tag preferred publications as “Featured on website”.  \
 \
After that, the Wordpress developer can create a “Featured vacancies widget” based on a “vacancy post loop” restricted to the custom-field “featured on website”.


## Google for Jobs

Google for Jobs is an enhanced search widget that aggregates listings from job boards and vacancy sites and displays them prominently in Google search.

To have your jobs included you need to add “structured job posting data” to your job pages. This information is invisible, so your job pages are still looking the same. When Google is indexing your site, the structured data is recognized and added to Google for Jobs.

**Enabling and testing Google for Jobs**
* Carerix → Settings → Tab 'Google for jobs'
* Enable 'Google for Jobs support' and click on save changes
* Navigate to a vacancy information page of your choice at the front-end of your site
* Copy/paste the URL of the former step in the Google Structured Data testing tool:
* You will see the JobPosting entity is detected. The tool might give some warnings about recommended fields. Currently this information is not available in the CX WP plugin.

**Configuring yourself as hiring organization**

The hiring organization is also included in Google for Jobs. If you don't mark your jobs as “anonymous”, your client (hiring organization) will be displayed. For jobs marked as anonymous you can put your own organization name as the hiring one. To do this fill in your own company name in the field “Hiring organization”. Optionally you can also add your company logo.


## Job Conversion Tracking for web analytics


## The Cx WP plugin supports custom code snippets for extended web analytics usage (e.g. Facebook pixel, Google Analytics, etc.)

Custom (javascript) code can be applied to the following webpage sections:


* General (basically  to all pages)
* Job description page
* Job application page
* Job application confirmation page

Additionally custom information (apply source and apply tags) can be set which will be stored in the “Candidate Match file”.

Configuring custom conversion/tracking code


* Note: understanding of/some skills in JavaScript is required
* As an administrator from your Wordpress Dashboard, navigate to Carerix → Settings → Tab 'Conversion tracking'
* Enter valid javascript code including &lt;script>-tags in the corresponding text-boxes
* You can access special global variables holding information like publication-ID, vacancy-ID and job title. The available variables names are displayed in the blue information box. Tip: you can also dump this information in your browser debug console by entering console.log(cx); at a vacancy description page.
* Finally you can use the methods cx.setApplySource() and cx.setApplyTags() to add extra information to the application (retrievable in the Carerix system under 'Matches')


## Taxonomies

The plugin is generating Taxonomies for Jobs posts. The current taxonomies and the corresponding Carerix tables are

**Jobs**

* Countries - Country
* Regions - Region
* Educations - Education 0
* Functiongroup - Function 0
* Functions - Function 1
* Work locations - Publication work location

In order to use the taxonomies as filters for the 2 types of posts, the names of the taxonomies must be distinct. Otherwise, if common, the values of the taxonomies will be displayed for both type of posts and the user will experience that after sellecting a taxonomy no result will be returned.

Default resources are used to generate the names of the taxonomies. The language applied will follow the language of the plugin.

Define your own values for the taxonomies creating for each languge a different / new value to overwrite the default ones filled from resources.


## Shortcodes

## Job Alert Subscription
You can create a standalone Job Alert Subscription page, using the the [cx_job_alert_subscription] shortcode.

In WordPress you can use this shortcode to show a form for job alerts (vacancy subscription). When candidates signup they will receive emails in the future containing vacancies that fit their selected criteria, on a daily basis.

`See the example in`

The following fields will be displayed in the form:

* Email address
* First name
* Last name (and prefix)
* Gender
* Country selection preference (only if multiple countries are published in Carerix)
* Three “sub region” selector preferences like provinces, counties and departments (only if these are published in Carerix)
* Two function group preferences with an optional parent business-line selector (the business-line selector will only appear if multiple business-lines are published in Carerix)
* Agreement to terms checkbox (also enforces the storage term of the personal information to comply to GDPR)
* Anti bot abuse system (by captcha)

The process for the candidate is as follows:

1. Candidate selects the criteria to receive job opportunities for and submits the form
2. Candidate receives an opt-in activation mail and clicks on the activation link
3. Candidate starts receiving mail with (new) vacancies on a daily basis that match the selected criteria
4. To cancel, the candidate can use the unsubscribe link in the job alert mails

#### Parameters

<table>
  <tr>
   <td><strong>Parameter</strong>
   </td>
   <td><strong>Is Mandatory</strong>
   </td>
   <td><strong>Possible values</strong>
   </td>
   <td><strong>Details</strong>
   </td>
  </tr>
  <tr>
   <td>frequency (supported since v3.0.0)
   </td>
   <td>NO
   </td>
   <td>daily, bidaily, tridaily, twiceweekly, weekly, biweekly or monthly (defaults to daily)
   </td>
   <td>sets the default mailing frequency for the subscription
   </td>
  </tr>
  <tr>
   <td>confirmation_message
   </td>
   <td>NO
   </td>
   <td>text/html string
   </td>
   <td>the actual message that appears after a successful user submission
   </td>
  </tr>
  <tr>
   <td>confirmation_url
   </td>
   <td>NO
   </td>
   <td>relative or full URL
   </td>
   <td>redirects the users' browser to the provided URL after a successful submission
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>Usage example</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Example
   </td>
   <td colspan="3" >Result
   </td>
  </tr>
  <tr>
   <td>[cx_job_alert_subscription confirmation_url=“/jobalert_thank_you/”]
   </td>
   <td colspan="3" >It will display a form for the user to choose on what kind of publications to subscribe. After a successful submission the browser redirects to the URL /jobalert_thank_you/
   </td>
  </tr>
</table>



