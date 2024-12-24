# BACK UP WordPress Plugin
----------------
Dit document bevat een backup van 2 Wiki pagina’s : 
1. De Technical info
2. Getting started guide 

voorheen te vinden op: https://development.wiki.carerix.com/doku.php?id=cxwordpress2

Go to cxwordpress2#release_notes|Release Notes]] and download the latest version.
Also see Demo & Tips at [plugin.demo.carerix.com]([url](https://demo.carerix.com/plugin/))

<!--
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
-->

> [!IMPORTANT]
> ### Application Token ###
> You'll be asked for the Application Token to authorize the Carerix plugin with your Carerix Application (applicationname.carerix.net).
>
> You'll have to ask your customer to contact Carerix support to ask for a Token.
>
>Carerix will not be able to provide you the Application token, as this is the authorization procedure.

See also:
  * [[cxwordpress2-getting-started|Getting started Guide]]
  * [[cxwordpress2-getting-started#faqs|Frequently Asked Questions]]

##### Carerix WordPress plugin - Technical information #####

##### Requirements #####

  *  Mandatory:
    * Linux OS
    * Apache 2.x (NGINX is not supported)
    *  PHP 7.4 - 8.2 
        * cURL
        * OpenSSL
        * JSON
    *  MySQL 5 or higher / MariaDB
  * Recommended PHP memory limit:
    * 128 MB (for sites with lightweight themes / few plugins)
    * 256 MB (for regular sites)
    * 512 MB or higher (for sites with heavyweight themes/ many plugins)

> [!NOTE]
> **May 2023** The (latest) Carerix Wordpress Plugin has been tested for Wordpress versions up to 6.2



### Installation ###

## Initial Steps ##
To create a new website based on WordPress and connect it to the Carerix System, follow this steps:

  -  Download the latest WordPress http://wordpress.org/download/
  -  Install and configure your WordPress  http://codex.wordpress.org/Installing_WordPress
  -  Download the latest CxWordPress plugin as a zip package from Release Notes.

## Installing the Carerix Plugin ##
  * Make sure the hosting environment meets the technical requirements (described earlier)
  * Define the hosting' PHP memory limit in the Wordpress configuration file [wp-config](https://wordpress.org/support/article/editing-wp-config-php/#increasing-memory-allocated-to-php) » define('WP_MEMORY_LIMIT', 'xxxM');]] where xxx is the PHP memory limit expressed in megabytes
  *  Go to **Plugins** » **Add New** » **Upload**
    *  Locate the archive you have just saved
    *  Click Install
  *  When the upload is completed, click on the "**Activate Plugi**n" link
  *  Go to the **Settings » Permalinks** panel and choose any of the options listed.
  *  Do NOT put your site url in the permalinks slot. You must use one of the structure tags, or a combination of tags only.
    * Make sure you don't cache the Vacancy Posts with caching plugins like W3 total cache, Comet cache, Rocket cache. 
  *  Check your Administration Panels or WordPress blog to see if the Plugin is working.
  *  Follow the instructions in the [[#Settings| Settings]] section to setup de plugin.

## Installing Email templates ##
You need to have these email templates installed to make full use of the plugin: 
- cxportal_cxwordpress

> [!IMPORTANT]
> ## Change the ApplyURL to website ##
> Don't forget to change the ApplyURL, so that links in emailtemplates are directed to the website instead of cxportal.  (**Settings » Attributes and fields » Apply_url**)
> ```
> http://www.domainname.com/?pub_id=<cx:write value="$publication.publicationID"/>
> ```
> This will generate http://www.domainname.com/?pub_id=123 and show the according Vacancy publication on the website


### Updating the Plugin ###
  - Make sure to make a backup of your website before updating the plugin which is good practice for updating WordPress plugins. Also check your Website after updating.
  - In Wordpress dashboard -> Plugins, locate the Carerix Wordpress Plugin
  - If there's an update available you can click on the 'Update now' link

### Uninstall the Plugin ###

  *  Deactivate
    *  Go to Plugins section
    *  Find the plugin, 
    *  Click on //Deactivate//

  *  Remove the plugin
    *  Go to Plugins section
    *  Find the plugin, 
    *  Click on //Deactivate//, if the plugin is active
    *  Click on //Delete//

### Features ###

  * List Job orders
  * <del>List Candidates</del>
  * (Custom) Apply Forms
  * Shortcodes
  * WPML Integration





----

### Usage ###

First of all. If you experience PHP warnings/notices, please suppress these messages by using the setting <code>define( 'WP_DEBUG', false );</code> More info: https://wordpress.org/support/article/debugging-in-wordpress/
## Settings ##

### Credentials ###

The credentials can be set in the Settings section of the Carerix plugin.
They consist of the **Carerix Application Name** and **Application Token**.
If you do not have an **Application Token**, you can follow this [[http://en.wiki.carerix.com/index.php/Activate_API_for_WordPress_plugin|Activate API for WordPress]] to generate one.

Click on **Save changes** button to save the credentials.

### Location Reporting ###

If you check the **Allow the plugin to report its location**, the plugin will periodically send data about the location of where the plugin was installed back to Carerix.

### Manual Synchronization ###

The data that exists in WordPress is periodically updated (every 10 minutes) to reflect the actual data in the system.
You can use the **Synchronize Now** button to manually initiate the synchronize mechanism, if you want to see the changes immediately.

## Forms ##

In the Forms section you can define different apply forms to be used for different kind of publications.

When you first install the plugin, a default form named Form 1 will be added automatically. This default form can be changed and saved.


### Form 1 (default form) ###

Default form has the following fields set: 
<!--
|<WRAP>**Field Name**
</WRAP>||<WRAP> Visible 
</WRAP>||<WRAP> Required 
</WRAP>|-
|<WRAP>Last name 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> YES 
</WRAP>|-
|<WRAP>First name 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> YES 
</WRAP>|-
|<WRAP>Last name at birth 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Title 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Suffix 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Password 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Gender 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Marital status 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Date of birth 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> YES
</WRAP>|-
|<WRAP>Place of birth 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Country of birth 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Nationality 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Function level 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Experience 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>CV 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> YES 
</WRAP>|-
|<WRAP>Photo 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Extra document 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Email 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> YES
</WRAP>|-
|<WRAP>Home Phone 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Work Phone 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Contact Instructions 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 

</WRAP>|-
|<WRAP>Home address 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Alternative address 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Ambition & Availability  
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Experience 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Transportation 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Education 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Languages 
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Motivation & Source  
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> NO 
</WRAP>|-
|<WRAP>Remember Me  
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> NO 
</WRAP>|}
-->

### Creating a New Form  ###
  * To create a **New Form **go to //Carerix >> Forms// and click on the **Add new** 
  * This action will open an editing screen for a new form. 

## Title ##
The first input field is the name of the form to help the web builder identify it when using it.

## Options  ##
  * In the **Form Options** panel, you'll be able to set each field available for a form as **Visible** or **Required**. If you set a field as **Required, **it** **will also be **Visible.** The **Last Name** and **Email** fields can not be changed, and both are set to be **Required.** 
  * After you set the status of each field as you want, click on the **Save** button. 
  * The edit screen will re-display, with your choices remembered and a new section above the options displaying the shortcode to use if you want to display this form for an open application.

## Synchronize with Carerix ##
The **Synchronize with Carerix** button checks if fields that use values from the Carerix System are available. For example, if it can not find any values for the Nationality field, that field will be disabled.

### Change the form of a specific Source ###
Connect a form to the 'Source'  of regular Vacancy posts as follows:
  * Go to **Sources**
  * Open the specific Source that you want the new form to use with
  * Scroll down to **Publication Details Options**
  * Select the new form and Save the Source

### Editing and Deleting a Form  ###
  * Every form that you created, except the default Form 1, can be edited or deleted.
  * The edit and delete link appears when you move the mouse pointer over the title of a form.
  * To Edit a Form, click on it's name or on the edit link under its name.
  * To Delete a Form, click on the delete link under its name.

###Settings###
**Show login link:** set to Yes by default. If enabled, it generates the login link in the job details page. 

**Extra apply options:** Set to no by default. <del>If enabled it generates the Apply with Linkedin link</del> 

**Address format:** International / Dutch. For Dutch each field is split on it's own form field while for International the entire addres can be inserted in one textarea. 

**Agreement link:**
  * Default: no agreement link
  * Insert desired text in the **"Agreement Label"** and in ** "Agreement text"** fields to generate and display the link. 
  * Insert an URL   to be associated with the agreement text url. If Agreement URL field is fille,d it takes precedent over the Agreement text. 
  * Captcha: choose in which page to display the Captcha code
  * Advanced: Clear Datanodes Cache. If you made a change in the Carerix System to one of the DataNodes used here, you should clean the cache. 
## Sources ##

The sources section allows the web builder to set the locations from where the plugin should fetch the data when generating posts and pages.

### Configuring a job source ###

## Add New ##

To add new Jobs source click on the **Add New** button. 

The following fields can be set:

  *  **Source name**
    *  Helps you to identify the configured source.
  *  **Publications Details Options**
    *  Here you can set options for how the applicant will see and interact with the vacancy posts generated from this source.
      *  Apply Form
        *  Here you can select what form to be used when an user applies to a publication corresponding to a post generated from this source.
      *  Title - Location:
        *  You can select if you want to add the work location after the Title or not.
{{:title_-_location.png?nolink|}}
      *  Set Alternative Feed Source Parameters
        *  You can specify a different 'medium'-code here. It's useful if you have multiple sites or brands with different sets of vacancies
      * **Publication Details Header** and **Publication Details Footer**
        * If you want to display details in the footer or the header, use the following shortcodes:
          * [cx_rss_for_category]
            * display the rss for the publication category
          * [cx_rss_for_all]
            * display the rss for all the publications
          * <del>[cx_tell_a_friend_link]</del> (discontinuing in upcoming releases)
            * display the tell a friend link
          * [cx_print_link]
            * display the print link
          * [cx_function_group]
            * display the function group
          * [cx_vacancy_number]
            * display the vacancy number, as auto-generated in Carerix. However, consider using [cx_vacancy_code] instead
          * [cx_vacancy_code]
            * display the vacancy reference code. By default the reference code is equal to the auto-generated vacancy number in Carerix. But if you have changed the //reference code// in Carerix->Files->Job orders->General, this new entry is displayed
          * <del>[cx_social_icons]</del> (discontinuing in upcoming releases)
            * display social share icons
          * [cx_apply_button]
            * display the apply button
          * [cx_apply_form]
            * display the apply form
          * <del>[cx_job_alert_subscription_link]</del> (discontinuing in upcoming releases)
            * display the job alert subscription link
      * **Publication Excerpt** (new since v3.0.0)
        * Here you can use an alternative/better teaser (summary text) which will be used as a summary, specifically in vacancy overview/listing pages. Please read the accompanying usage explaination in the plugin as you are configuring the job source.
      * **Publication Details Body** (new since v3.0.0)
        * One of the biggest new features of v.3.0.0 is the Publication Details Body editor. You can use shortcodes like [cx_intro_information], [cx_offer_information] and many more to setup your own vacancy layout template. Please read the accompanying usage explaination in the plugin as you are configuring the job source.
## Edit and Delete a Source ##

  *  Editing
    *  To Edit a Source click on its name or on the edit link under its name. 
    *  Changes to the Title, Feed Source or Page intro will become visible only after the next synchronize.
    *  Changes to the Publication Details options will become visible immediately.

  *  Deleting
    *  To Delete a Source click on the delete link under its name.
    *  //Important//: Deleting a source will not delete the generated posts from wordpress.

**Note:** If you want to change the form that is set to a certain Source: Please see [[#change_the_form_of_a_specific_source|Change the form of a specific Source]]
## Special jobs: one language website, multiple languages used for publication texts ##

You have a website entirely in Dutch but you want to display one or more jobs in a different language?
By default, you publications will receive all header sections in Dutch. take the following steps in order to have the labels in the correct language. 

##In Carerix:##
  * Create medium with the desired code (Eg: MED) to contain the publications in the default language of the website.
  * Create the publications in this medium with text in the default language of the website.
  * Create medium with code defined at 1. and add to it -lg code (Eg: MED-en, MED-es, MED-de, MED-fr).
  * Create publications in this medium in the extra language that you need to publish

 
##In wp-admin / Carerix / Sources##
  * Create new source to generate your jobs page. //Eg.  Page name: Mixed jobs//
  * In the Set Feed Source Parameters section, after the default feed, in the input text  insert //Eg. for English:// medium=MED|Med-en
  * Make the rest of settings and click save.


##Result:##
Page named ##Mixed Jobs## is created. The page will display jobs from the 2 defined mediums.
For the posts for which value of parameter medium is found to be code-lg, the resources will be generated in the language code corresponding to lg value.
If the lg value is not one of the know values used by CxWp, the default language to be used is the language in which the website is defined.


<WRAP tip 60%>
NOTE: If you do not want to use multilanguage-features, never use a mediumcode containing a dash. The Wordpress plugin will interprete it as a language resulting in English subtitles within your vacancies. So if you want to use a medium to seperate vacancies for your second agency, use a mediumcode like "webagency2" instead of "web-agency2"
</WRAP>

----






	
## Diagnostics (since v3.0.0) ##
From v3.0.0, the jobs synchronizing process will be fully handled by the REST API. Therefore the CxTools jobs feed has become obsolete.
For example, the diagnostics tool (Wordpress Dashboard -> Carerix -> Settings -> Tab Diagnostics) will help you to find possible inconsistencies between published vacancies in your Carerix system and the vacancies that are retrieved by your Wordpress site.

You can review the 'active job publications' but also the available 'medium codes'.


## Extra/Additional Carerix fields support (since v3.0.0) ##
You can find the feature in Carerix Dashboard->Carerix->Settings-> tab Technology previews

In the Carerix system extra/additional fields can be added to Job orders and Publications.
The information from these custom fields can be displayed in your vacancies. You can also use it as options in a "vacancy-listing search&filter" widget.

Use case

A nice use case is a "featured/highlighted" vacancy widget to highlight some vacancies. Therefore in Carerix you need to create an additional field called "featured on website" (type single checkbox) and attach it to the "Publications entity". In Carerix, recruiters can tag preferred publications as "featured on website".
After that, your Wordpress developer can create a "featured vacancies widget" based on a "vacancy post loop" restricted to the custom-field "featured on website". 


## Google for Jobs (since v2.15.0) ##
Google for Jobs is an enhanced search widget that aggregates listings from job boards and vacancy sites and displays them prominently in Google search.

To have your jobs included you need to add "structured job posting data" to your job pages.
This information is invisible, so your job pages are still looking the same.
When Google is indexing your site, the structured data is recognized and added to Google for Jobs.

**Enabling and testing Google for Jobs**
  * As an administrator from your Wordpress Dashboard, navigate to Carerix -> Settings -> Tab 'Google for jobs'
  * Enable 'Google for Jobs support' and click on save changes
  * Navigate to a vacancy information page of your choice at the front-end of your site
  * Copy/paste the URL of the former step in the Google Structured Data testing tool: https://search.google.com/structured-data/testing-tool
  * If everything went well you will see the JobPosting entity is detected. Probably the tool will give some warnings about recommended fields. Currently this information is not available in the CX WP plugin.

**Configuring yourself as hiring organization**

The hiring organization is also included in Google for Jobs. If you don't mark your jobs as "anonymous",
your client (hiring organization) will be displayed.
For jobs marked as anonymous you can put your own organization name as the hiring one.
To do this fill in your own company name in the field "Hiring organization". Optionally you can also add your company logo.


## Job Conversion Tracking (since v2.15.0) ##
The CX WP plugin supports custom code snippets for extended web analytics usage (e.g. Facebook pixel, Google Analytics, etc.)

Custom (javascript) code can be applied to the following webpage sections:
  * General (basicly to all pages)
  * Job description page
  * Job application page
  * Job application confirmation page

Additionally custom information (apply source and apply tags) can be set which will be stored in the "Candidate Match file".

**Configuring custom conversion/tracking code**
  * Note: understanding of/some skills in JavaScript is required
  * As an administrator from your Wordpress Dashboard, navigate to Carerix -> Settings -> Tab 'Conversion tracking'
  * Enter valid javascript code including <script>-tags in the corresponding text-boxes
  * You can access special global variables holding information like publication-ID, vacancy-ID and job title. The available variables names are displayed in the blue information box. Tip: you can also dump this information in your browser debug console by entering **console.log(cx);** at a vacancy description page.
  * Finally you can use the methods **cx.setApplySource()** and **cx.setApplyTags()** to add extra information to the application (retrievable in the Carerix system under 'Matches')

## Taxonomies##
The plugin is generating Taxonomies for Jobs posts. The current taxonomies and the corresponding Carerix tables are

**Jobs:**

  * Countries - Country
  * Regions - Region
  * Educations - Education 0
  * Functiongroup - Function 0
  * Functions - Function 1
  * Work locations - Publication work location


In order to use the taxonomies as filters for the 2 types of posts, the names of the taxonomies must be distinct.
Otherwise, if common,  the values of the taxonomies will be displayed for both type of posts and the user will experience that after sellecting a taxonomy no result will be returned.

Default resources are used to generate the names of the taxonomies. The language applied will follow the language of the plugin.

Define your own values for the taxonomies creating for each languge a different / new value to overwrite the default ones filled from resources. 



## Shortcodes ##

### Tell a Friend ###
Optional, you can create a stand alone //Tell a friend//  page for a specific publication. Use **[cx_tell_a_friend]** shortcode in order to enable this feature. 

## Parameters ##


|<WRAP>**Parameter**
</WRAP>||<WRAP> Is Mandatory 
</WRAP>||<WRAP> Possible values 
</WRAP>||<WRAP>Details 

</WRAP>|-
|<WRAP>publicationid 
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> pubID 
</WRAP>||<WRAP> the id of the publication for which this form will send the tell a friend email template.

</WRAP>|}

 
## Usage Example  ##



|<WRAP>**Example**
</WRAP>||<WRAP> Result 

</WRAP>|-
|<WRAP>[cx_tell_a_friend publicationid="4"]  
</WRAP>||<WRAP> Generates a "The tell a friend" form that will display for the publication with id 4

</WRAP>|}


### Job Alert Subscription ###

You can create a standalone Job Alert Subscription page, using the the **[cx_job_alert_subscription]** shortcode.

## Parameters ##


|<WRAP>**Parameter**
</WRAP>||<WRAP> Is Mandatory 
</WRAP>||<WRAP> Possible values 
</WRAP>||<WRAP> Details 

</WRAP>|-
|<WRAP>frequency (supported since v3.0.0)
</WRAP>||<WRAP> NO
</WRAP>||<WRAP> daily, bidaily, tridaily, twiceweekly, weekly, biweekly or monthly
(defaults to daily)
</WRAP>||<WRAP> sets the default mailing frequency for the subscription

</WRAP>|-
|<WRAP>confirmation_message
</WRAP>||<WRAP> NO
</WRAP>||<WRAP> text/html string
</WRAP>||<WRAP> the actual message that appears after a successful user submission

</WRAP>|-
|<WRAP>confirmation_url
</WRAP>||<WRAP> NO
</WRAP>||<WRAP> relative or full URL
</WRAP>||<WRAP> redirects the users' browser to the provided URL after a successful submission
</WRAP>|}

 


## Usage example ##



|<WRAP>**Example**
</WRAP>||<WRAP> Result 

</WRAP>|-
|<WRAP>[cx_job_alert_subscription confirmation_url="/jobalert_thank_you/"]  
</WRAP>||<WRAP> It will display a form for the user to choose on what kind of publications to subscribe. After a successful submission the browser redirects to the URL /jobalert_thank_you/

</WRAP>|}

Note: please study the [[cxwordpress2-getting-started#job_alerts|job alert step-by-step guide]] explaining how to setup the required configuration in Carerix

### Campaign ###

To create a subscription form for the campaigns existent in the system, you can use the **[cx_campaign]** shortcode in a page. See the examples below.

## Parameters  ##

|<WRAP>**Parameter** 
</WRAP>||<WRAP> Is Mandatory 
</WRAP>||<WRAP> Possible values 
</WRAP>||<WRAP> Details
</WRAP>|-
|<WRAP>sendto
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> email list 
</WRAP>||<WRAP> a list of emails where the data should be send separated by a pipe character '&#124;'

</WRAP>|-
|<WRAP>codeinname
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> codes
</WRAP>||<WRAP> a list of text fragments, separated by a pipe character '&#124;', that the title of the campaign should contain if it is to be displayed

</WRAP>|-
|<WRAP>campaignid
</WRAP>||<WRAP>  NO 
</WRAP>||<WRAP> campaign ids
</WRAP>||<WRAP> a list of ids, separated by a pipe character '&#124;', for the campaigns to be displayed

</WRAP>|}

## Usage  ##



|<WRAP>**Example**
</WRAP>||<WRAP> Result 

</WRAP>|-
|<WRAP>[cx_campaign sendto="email2@test.com"] 
</WRAP>||<WRAP> it will display all the active campaigns

</WRAP>|-
|<WRAP>[cx_campaign sendto="email2@test.com" codeinname="test1&#124;test2"] 
</WRAP>||<WRAP> it will display only campaigns that have 'test1' or 'test2' in their names.

</WRAP>|-
|<WRAP> [cx_campaign sendto="email2@test.com" campaignid="1&#124;2&#124;3"] 
</WRAP>||<WRAP> it will display only the campaigns with ids 1, 2 and 3

</WRAP>|-
|<WRAP> [cx_campaign sendto="email2@test.com" codeinname="test1&#124;test2" campaignid="1&#124;2&#124;3"] 
</WRAP>||<WRAP> //codeinname// parameter, if existent, has priority over the //campaignid// parameter

</WRAP>|}



### Open Application ###

To create an open application form, create a page and insert the **cx_open_application** shortcode, following one of the examples below.

## Parameters ##


|<WRAP>**Parameter**
</WRAP>||<WRAP>Is Mandatory 
</WRAP>||<WRAP>Possible values 
</WRAP>||<WRAP>Details

</WRAP>|-
|<WRAP>openformid
</WRAP>||<WRAP> YES 
</WRAP>||<WRAP> form id 
</WRAP>||<WRAP> the number should reference the id of one of the apply forms that the web builder created.

</WRAP>|-
|<WRAP>openpubid
</WRAP>||<WRAP> NO 
</WRAP>||<WRAP> pubID
</WRAP>||<WRAP> must be the id of a valid open publication in the system

</WRAP>|}


## Usage ##



|<WRAP>**Example**
</WRAP>||<WRAP> Result 

</WRAP>|-
|<WRAP> <code>[cx_open_application openformid="3"]</code> 
</WRAP>||<WRAP> will display the form with id 3 for the first open publication found in the system.

</WRAP>|-
|<WRAP> <code>[cx_open_application openformid="3" openpubid="30"]</code>  
</WRAP>||<WRAP>will display the form with id 3 for the open publication with id 30, if it is a valid open publication.

</WRAP>|}

### Login ###
|<WRAP>**Example**
</WRAP>||<WRAP> Result 

</WRAP>|-
|<WRAP> [cx_login_form] 
</WRAP>||<WRAP> Will display a login form (username & password)
</WRAP>|}



----


#### Release Notes ####

## Stable version ##

> [!NOTE]
> ### Version 3.0.2 ###
> 30 MARCH 2023 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_3.0.2.zip|CxWordPress 2 (v3.0.2)]]
> 
  > * WP-147 **Added** Filter hook `carerix_search_action`
  > * WP-149 **Fix** Applytags fix (cx_applysource cx_applytags)
  > * WP-151 **Fix** Submit label missing on open application form for Dutch language
> 

### Version 3.0.1 ###
20 MARCH 2023 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_3.0.1.zip|CxWordPress 2 (v3.0.1)]]

  * **Improved** Cleanup NL language resource file. Other languages to do
  * **Fix** Category recreation in non-WPML environment
  * **Fix** Php warning removed in apply form
  * **Fix** Php warning removed google cookie
  * **Fix** In some cases some parts of vacancy texts aren't retrieved from the Carerix system
  * **Fix** In some cases the vacancy synchronisation is halted during the processing of `additional fields`
  * **Fix** Vacancy list page stepper didn't reset to the first page if a visitor used the "Carerix Search Widget"

### Version 3.0.0 ###
27 FEBRUARY 2023 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_3.0.0.zip|CxWordPress 2 (v3.0.0)]]

  * **Fix**   Choices from the gender field of the Open Applicaton form were incorrectly stored in Carerix
  * **Added**   Vacancy templates structured by new shortcodes for fine-grained control of the vacancy layout
  * **Added**   Vacancy posts can make use of additional/custom fields defined in job orders/publications (technology preview)
  * **Added**   Diagnostics page
  * **Added**   Support for PHP 8.1 and 8.2
  * **Added**   Search widget will query all registered medium sources instead of the default 'web'
  * **Added**   Minimal Polish language support (Note: still in progress. Some strings are still in English)
  * **Improved** New Feed source parameters Support (WP admin->Carerix Sources): pipe-delimited mediumcodes (e.g. medium=web|brand2|office2) and 'forced' localized headers/labels (e.g. language=French)
  * **Improved** Shortcode [cx_job_alert_subscription] supports sending frequencies by the parameter "frequency". [cx_job_alert_subscription frequency="daily,bidaily,tridaily,twiceweekly,weekly,biweekly,monthly"]
  * **Improved** Better multilanguage support (requires WPML plugin)
  * **Improved** Max document upload size calculation (for application forms)
  * **Improved** Default Application form can be edited (used to be 'read-only')
  * **Dropped ** Requires PHP 7.4 or higher. Dropped support for PHP 7.3 and lower
  * **Dropped ** Synchronizing vacancies by CXtools feed (in favour of REST-API sync)

### Version 2.22.0 ###
18 OCTOBER 2021 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.22.0.zip|CxWordPress 2 (v2.22.0)]]

  * WPP-61  Added    Support for PHP 7.4 and PHP 8.0
  * WPP-113 Added    WP admin alertbox/announcement Cxtools feeds stops
  * WPP-115 Added    Pre-installation/upgrade compatibility check
  * WPP-121 Added    Google for jobs - Direct Apply support
  * WPP-130 Added    New shortcode [cx_apply_form]
  * WPP-131 Improved Extended incoming data of action hook "cxwordpress_post_updated". New arguments: `post data` and `raw cx fields`
  * WPP-132 Dropped  Disabled applicant login links on apply forms
  * WPP-133 Improved Improved job sources screen (admin UI)
  * WPP-135 Improved Removed auto generated pages (jobs default page + open application page)

### Version 2.21.3 ###
16 AUGUST 2021 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.21.3.zip|CxWordPress 2 (v2.21.3)]] 

  * Misc    Fix      German language file was missing Business Line (Fachgebiet)
  * WPP-114 Fix      Emailaddress on application forms were not validated (client-side) anymore
  * Misc    Improved Improved support for rendering [cx_open_application] shortcode for widgets (like Elementor)

### Version 2.21.2 ###
02 JUNE 2021 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.21.2.zip|CxWordPress 2 (v2.21.2)]] 

* Misc    Fix  PHP 7.0-7.2 yield compatibility notifications

### Version 2.21.1 ###
02 JUNE 2021 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.21.1.zip|CxWordPress 2 (v2.21.1)]] 

  * Misc    Fix  REST-API jobs sync

### Version 2.21.0 ###
01 JUNE 2021 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.21.0.zip|CxWordPress 2 (v2.21.0)]] 

  * WPP-40  Improved Job alert form and shortcode. Optional attributes are thank you message and custom confirmation url: [cx_job_alert_subscription confirmation_message="Thank you for subscribing to the job alert" confirmation_url="/thank_you/"]
  * WPP-85  Fix      Wordpress Site Health Operation timed out
  * WPP-90  Added    CX fields: implement "vacancy code" + shortcode [cx_vacancy_code]
  * WPP-91  Added    CX fields: implement "vacancy group"
  * WPP-94  Improved Disable mentioning postal code to Google For Jobs if the vacancy is set to anonymous
  * WPP-97  Added    Warning alert boxes if hosting requirements fail
  * WPP-98  Added    REST API full sync button (WP admin->Carerix->Settings)
  * WPP-102 Improved Replaced PHP-session by cookie management for required functionality
  * WPP-104 Improved Replaced captcha library by a newer one
  * WPP-105 Fix      Fields ordering by mousedrag (WP admin->Carerix->Application form configurator)
  * WPP-106 Fix      Rendering of the apply form between the <head>-tags in very specific 3rd party plugins/theme installations
  * WPP-107 Fix      Rest API-job-sync sometimes "misses" some vacancies resulting in a out-of-sync
  * WPP-108 Added    Possibility to override fixed resource labels like "introduction", "requirements" etc. from your own (child)theme. Access and knowledge to add/modify php files required
  * Misc    Improved Vacancy syncing process flushes a possible (Redis) cache first to avoid blocking PHP errors
  * Misc    Improved Compatibility with Wordpress 5.6 and 5.7 (jQuery 1.x is dropped)
  * Misc    Dropped  Outdated promotional jobs. Replaced by WPP-91

### Version 2.20.5 ###
16 SEPT 2020 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.20.5.zip|CxWordPress 2 (v2.20.5)]] 
  * Improved Only show 'managed by Carerix' column in the general posts manager
  * WPP-88 Added    Support for the field "Business Line / Field" (vakgebied)
  * WPP-49 Added    New Application Form settings: 'remember me'-on/off toggle, emailaddress private/business-on/off toggle, add/remove emailaddress on/off toggle
  * WPP-86 Improved Google For Jobs structured data now supports salary fields. Settings are retrieved from the CX job order: "Purchase rate/Salary low and high" and "Publish Salary" checkbox
  * Fix      The Wordpress global timezone setting could postpone the API job synchronization process

### Version 2.20.4 ###
18 JUNE 2020 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.20.4.zip|CxWordPress 2 (v2.20.4)]] 
  
  * WPP-83 Improved Compatibility with Wordpress themes (jQuery conflicts)
  * WPP-83 Improved Compatibility with optimizer plugins like Autoptimize, W3 Total Cache and Breeze Cache
  * WPP-83 Improved Updated Polyfiller/Webshim to the latest release
  * WPP-83 Fix      Removed deprecated filter 'contextual_help'

### Version 2.20.3 ###
25 MAY 2020 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.20.3.zip|CxWordPress 2 (v2.20.3)]] 
  
  * WPP-80 Fix Plugin breaks with Yoast SEO plugin using opengraph (staring from v14.x)
  * WPP-77 Fix Conflicting with other Jquery versions
  * Improved Job landing pages like https://yoursite.com/?pub_id=519 or https://yoursite.com/pubid/519 will now redirect including optionally parsed URL variables 

### Version 2.20.2 ###
07 MAY 2020 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.20.2.zip|CxWordPress 2 (v2.20.2)]] 
  
  * WPP-68 Added    Configuration option for setting or leaving out the <meta description>-tag directive for Yoast SEO
  * Fix      Javascript error (frontend.js) application form in Edge browsers
  * Fix      Date/time format in Google Sitemap (https://yoursite.com/?carerix_sitemap) 

### Version 2.20.1 ###
30 APR 2020 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.20.1.zip|CxWordPress 2 (v2.20.1)]] 
  
  * WPP-41 Added    Vacancy synchronisation by REST-API (enable via CX->settings->Sync by REST-API)
  *        Added    Developers logging enable/disable via Dashboard->Carerix->Settings
  *        Added    Shortcode [cx_apply_button] is not mandatory anymore in Sources->Source edit->Publication Details Footer
  * WPP-58 Added    New CSS classes (prefixed with cx2_) to vacancy details posts (section titles + content) for better styling. E.g: <nowiki><h4 class="cx_h4 cx2_introduction">Introduction</h4> <div class="cx2_introduction">...</div></nowiki>
  * WPP-67 Added    For application forms a required field indicator (e.g. asterisk) can be appended to the field label: #apply_form label.cx2_required:after { content:" *" !important; }
  * WPP-37 Added    Google sitemap for faster Google For Jobs indexation. Register the URL https://yoursite.com/?carerix_sitemap as a sitemap in Google Search Console
  * WPP-1  Added    Redirect from "foreign pubid" (alias pubids). Other publications of the vacancy will be mapped to the published publication on the site. Usage: https://mysite.com/?pub_id=xxxx, where xxxx is replaced by the "foreign" pub-id
  * WPP-70 Fixed    Apply form. Sometimes the error arises: "Uncaught Error: Call to a member function getId() on null in /wp-content/plugins/CxWordpress/Entity/Form/EmployeeApply.php:1715"
  * WPP-24 Fixed    PHP warning on vacancy detail page (in case google for jobs structured data was unable to parse)
  * WPP-55 Fixed    Setting 'Clean categories at sync'
  * WPP-57 Fixed    WP->CX->(application) forms->edit form: custom ordering of the fields in section 'address details' are respected
  * WPP-50 Fixed    WP->CX->(application) forms->edit form: enabling field education messes up the form
  * WPP-66 Fixed    Notice: A parser-blocking, cross site (i.e. different eTLD+1) script, http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js, is invoked via document.write.
  * WPP-12 Fixed    Application form sometimes doesn't validate the emailaddress format
  * WPP-59 Added    'wpnonce'-security for CX->sources->delete source + underlying associated posts/pages
  * WPP-59 Added    'wpnonce'-security for CX->forms->delete form + CX->forms->edit form
  * WPP-12 Improved Upload fields on the apply forms show better "max upload" indication texts
  * WPP-48 Improved Allow HTML in CX->sources->edit source: publication header and footer
  *        Improved Compatibility with plugin `Autoptimize`
  *        Improved fallback jQuery library version increased from v1.10.2 to v1.12.4
  *        Improved serveral UI labels/texts in the plugin settings
  *        Removed  Unused (cxtools) sources: runForCompanies, runForCandidates, runForPeople, runForNewsletters
  *        Removed  WP->CX->Settings->Tab "Import/Export"
### Version 2.15.1 ###
11 JUL 2019 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.15.1.zip|CxWordPress 2 (v.2.15.1)]]
  * Fixed jobalert form (after submit)
  * Improved translation issue for Dutch language (jobalert thank you form)
  * Improved translation issue for Dutch language (Functie eisen -> Functie-eisen)
  * Fixed PHP warning on vacancy detail page

### Version 2.15.0 ###
21 JUN 2019 | [[https://tools.carerix.com/wpupdate/packages/CxWordpress_2.15.0.zip|CxWordPress 2 (v.2.15.0)]]
  * Added new CSS classes (prefixed with cx2_) to the Apply Form to support better styling
  * Added new Carerix fields for vacancies: sector (branche0), industry (branche1), employment contract (contractType), hours per week (hoursPerWeek), minimum salary (minSalary), maximum salary (maxSalary)
  * Added support for 3rd party conversion tracking like Google Analytics, Google Adwords, Indeed, Facebook. (See: Dashboard -> Carerix -> Settings, tab "Conversion tracking")
  * Added appreciate URL parameters 'cx_applysource' and 'cx_applytags' for vacancy detail pages. (They were only processed on the apply-page previously)
  * Added support for Google for Jobs (minimal required fields). See: Dashboard -> Carerix -> Settings, tab "Google for jobs"
  * Improved switched from http to https for sharethis.com social-sharing icons
  * Removed split() function from EmployeeApply.php. Deprecated since PHP7
### Version 2.14.45 ###
09 JUL 2018 | [[https://tools.carerix.com/wpupdate/?CxWordpress.4b3403665fea6|CxWordPress 2 (v2.14.45)]] 
  * Added Improved Candidate "cleanup" procedure

### Version 2.14.44 ###
10 Jun 2018 | [[https://tools.carerix.com/wpupdate/?v=2.14.44&key=4b3403665fea6|CxWordPress2 (v2.14.44)]] 
  * Improved GDPR related functionality
  * Created extra checkbox in Carerix (not in Plugin) for table Consent Period called "Default for web" : if checked there that period is set by plugin applications


### Version 2.14.43 ###
02 Jan 2018 | [[https://tools.carerix.com/wpupdate/?v=2.14.43&key=4b3403665fea6|CxWordPress2 (v2.14.43)]] 
  * Added "approval date and stage" to apply functionality

### Version 2.14.42 ###
24 Jul 2017 | [[https://tools.carerix.com/wpupdate/?v=2.14.42&key=4b3403665fea6|CxWordPress2 (v2.14.42)]] 
  * Fixed translation issues

### Version 2.14.41 ###
08 May 2017 | [[https://tools.carerix.com/wpupdate/?v=2.14.41&key=4b3403665fea6|CxWordPress2 (v2.14.41)]] 
  * Added transliteration for permalinks
  * Fixed translation issues for Deutsch language
  * Removed "Applied with Linkedin" option

### Version 2.14.40 ###
10 Feb 2017 | [[https://tools.carerix.com/wpupdate/?v=2.14.40&key=4b3403665fea6|CxWordPress2 (v2.14.40)]] 
  * Disabled logging by default
  * Added extra validation logic for uploaded files
  * Increased "cleanup" cron interval
  * Fixed minor issues


### Version 2.14.39 ###
31 Jan 2017 | [[https://tools.carerix.com/wpupdate/?v=2.14.39&key=4b3403665fea6|CxWordPress2 (v2.14.39)]] 
  * Fixed issue with "ghost" translations of WPML plugin which stops synchronization in some cases

### Version 2.14.38 ###
31 Jan 2017 | [[https://tools.carerix.com/wpupdate/?v=2.14.38&key=4b3403665fea6|CxWordPress2 (v2.14.38)]] 
  * Fixed issue with "open application" apply

### Version 2.14.37 ###
05 Dec 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.37&key=4b3403665fea6|CxWordPress2 (v2.14.37)]] 
  * Added WPCron to remove tmp files created by plugin


### Version 2.14.35 ###
21 Sep 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.35&key=4b3403665fea6|CxWordPress2 (v2.14.35)]] 
  * Fixed issue with "motivation" field not been sent on application apply
  * Fixed issue with 404 error in some systems

### Version 2.14.34 ###
28 Aug 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.34&key=4b3403665fea6|CxWordPress2 (v2.14.34)]] 
  * Fixed issue with 'ghost' entities in WPML plugin table

### Version 2.14.33 ###
18 Jul 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.33&key=4b3403665fea6|CxWordPress2 (v2.14.33)]] 
  *  Fixed base64 double encoding of attachments issue



### Version 2.14.30 ###
18 Mar 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.30&key=4b3403665fea6|CxWordPress2 (v2.14.30)]] 
  *  Fixed "Apply with linkedIn URL" functionality 



### Version 2.14.29 ###
09 Mar 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.29&key=4b3403665fea6|CxWordPress2 (v2.14.29)]] 
  * Fixed "homeCity" and "homeCountry" fields in apply candidate action

### Version 2.14.28 ###
09 Feb 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.28&key=4b3403665fea6|CxWordPress2 (v2.14.28)]] 
  * Fixed error in "Auto-Update" functionality

### Version 2.14.27 ###
29 Jan 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.27&key=4b3403665fea6|CxWordPress2 (v2.14.27)]] 
  * Fixed error on "apply candidate" page

### Version 2.14.26 ###
14 Jan 2016 | [[https://tools.carerix.com/wpupdate/?v=2.14.26&key=4b3403665fea6|CxWordPress2 (v2.14.26)]] 
  * Added "Professional level" condition to "Carerix Search" widget

### Version 2.14.25 ###
13 Dec 2015 | [[https://tools.carerix.com/wpupdate/?v=2.14.25&key=4b3403665fea6|CxWordPress2 (v2.14.25)]] 
  * Added "cxwordpress_post_updated" and "cxwordpress_post_deleted" hooks 
### Version 2.14.24 ###
10 Dec 2015 | [[https://tools.carerix.com/wpupdate/?v=2.14.24&key=4b3403665fea6|CxWordPress2 (v2.14.24)]] 
  * Added Function level condition to "Carerix Search" widget

### Version 2.14.23 ###
03 Dec 2015 | [[https://tools.carerix.com/wpupdate/?v=2.14.23&key=4b3403665fea6|CxWordPress2 (v2.14.23)]] 
  * Added plugin Auto-Update functionality

### Version 2.14.22 ###
15 Nov 2015 | {{::cxwordpress2_0_v2.14.22.zip | CxWordPress2 (v2.14.22)}}
  * Fixed security issues 

### Version 2.14.21 ###
13 Nov 2015 | {{::cxwordpress2_0_v2.14.21.zip | CxWordPress2 (v2.14.21)}}
  * Fixed security issues 


### Version 2.14.20 ###
11 Nov 2015 | {{::cxwordpress2_0_v2.14.20.zip| CxWordPress2 (v2.14.20)}}

### Version 2.14.18 ###
20 Aug 2015 | {{::cxwordpress2_0_v2.14.18.zip| CxWordPress2 (v2.14.18)}}
  * Fixed "entire site search" functionality


### Version 2.14.17 ###
13 Aug 2015 | {{::cxwordpress2_0_v2.14.17.zip| CxWordPress2 (v2.14.17)}}
  * Fixed caching issue in 'Apply' form


### Version 2.14.16 ###
12 Aug 2015 | {{::cxwordpress2_0_v2.14.16.zip| CxWordPress2 (v2.14.16)}}
  * Added multilinguality for "select" fields in apply form


### Version 2.14.15 ###
04 Aug 2015 | {{::cxwordpress2_0_v2.14.15.zip| CxWordPress2 (v2.14.15)}}
  * Fixed synchronization issues


### Version 2.14.14 ###
29 Jul 2015 | {{::cxwordpress2_0_v2.14.14.zip| CxWordPress2 (v2.14.14)}}
  * Added "Hobbies" field to application form

### Version 2.14.13 ###
25 Jun 2015 | {{::cxwordpress2_0_v2.14.13.zip| CxWordPress2 (v2.14.13)}}
  * Fixed wrong count of search results in "Carerix Search" widget

### Version 2.14.12 ###
25 May 2015 | {{::cxwordpress2_0_v2.14.12.zip| CxWordPress2 (v2.14.12)}}
  * Added new setting "Skip main category"


### Version 2.14.11 ###
13 May 2015 | {{::cxwordpress2_0_v2.14.11.zip| CxWordPress2 (v2.14.11)}}
  * Removed extra "Back" link in confirmation page after a candidate applies


### Version 2.14.10 ###
30 April 2015 | {{::cxwordpress2_0_v2.14.10.zip| CxWordPress2 (v2.14.10)}}
  * Added: Sort function group alphabetically" option to Carerix Search Widget


### Version 2.14.9 ###
29 April 2015 | {{::cxwordpress2_0_v2.14.9.zip| CxWordPress2 (v2.14.9)}}
  * Added: "Middle name" and "Country/Region" fields to Job-alert subscription form
  * Fixed: Exception which appears during subscribing to a Job-alert


### Version 2.14.8 ###
27 April 2015 | {{::cxwordpress2_0_v2.14.8.zip| CxWordPress2 (v2.14.8)}}
  * Fixed: issue when wp_nav_menu is broken after Carerix Search submitted


### Version 2.14.7 ###
27 April 2015 | {{::cxwordpress2_0_v2.14.7.zip| CxWordPress2 (v2.14.7)}}
  * Added: fields "Salary" and "Desired industry" to Employee Apply form

### Version 2.14.6 ###
25 April 2015 | {{::cxwordpress2_0_v2.14.6.zip| CxWordPress2 (v2.14.6)}}
  * Fixed: issue with multiplying of "Job Default Page"

### Version 2.14.5 ###
23 April 2015 | {{::cxwordpress2_0_v.2.14.5.zip| CxWordPress2 (v2.14.5)}}
  * Added: Function as Category and in hierarchy related to Functiongroup

### Version 2.14.4 ###
23 April 2015 | {{::cxwordpress2_0_v2.14.4.zip| CxWordPress2 (v2.14.4)}}
  * Added: Options to show/hide fields in Carerix Search widget
  * Fixed: Spelling for some labels


### Version 2.14.3 ###
22 April 2015 | {{::cxwordpress2_0_v.2.14.3.zip| CxWordPress2 (v2.14.3)}}
  * Fixed: Bug with splitting of categories which includes "/" in the name


### Version 2.14.2 ###
21 April 2015 | {{::cxwordpress2_0_v2.14.2.zip| CxWordPress2 (v2.14.2)}}
  * Fixed: Bug in Apply Form with required Education field


### Version 2.14.1 ###
14 April 2015 | {{::cxwordpress2_0_v2.14.1.zip| CxWordPress2 (v2.14.1)}}
  * Fixed: Issue when multilingual Categories created in wrong language
  * Added: Multilingual confirmation message/page after successful application


### Version 2.14 ###
31 March 2015 | {{::cxwordpress2_0_v2.14.zip| CxWordPress2 (v2.14)}}
  * Added: Search by multiple function group in "Carerix Search" widget
  * Added: Search conditions saved in URL in "Carerix Search" widget

### Version 2.13 ###
30 March 2015 | {{::cxwordpress2_0_2.13.zip| CxWordPress2 (v2.13)}}\\ 
  * Fixed: Synchronization and search issues
### Version 2.10.9 ###
12 December 2014 | CxWordPress2 (v2.10.9)\\
  * Layout bugfixes
### Version 2.10.4.2 ###
29 October 2014 | CxWordPress2 (v2.10.4.2)\\
  * Added: Deprecated functions in PHP5.5. The plugin was updated to use the alternative mysqli driver, which is not deprecated.
  * Fixed: Extra document gave error message: Invalid document type
  * Fixed: Skills show up multiple times under the form when you +Add skills
### Version 2.10.4 ###
23 October 2014 | CxWordPress2 (v2.10.4)\\
## Added Features ##
  * Added: RSS feed link in jobdetails
  * Added: Customize slug for taxonomies / categories
  * Added: Hide 'Company' from anonymous job order/publication
  * Added: (the desired) 'Education' of a Vacancy as tag to the WP post.
  * Added: Meta description from introtext
  * Added: Forgotten password functionality
  * Added: Confirmation page, after applying
  * Added: Apply form for jobboard publications
  * Added: Customize fields to show for Candidate profile
  * Added: Reorder fields for Application form
  * Added: Option to remove Empty categories
  * Added: Add function1 as taxonomy. Rename function0 to Functiongroup
  * Added: Create a new author for each owner
  * Added: Administrator won't loose Admin rights after applying as Candidate with same email address
  * Added option to remove Empty categories
  * Added option: Confirmation text or Confirmation page after applying. Add the Confirmation page to Google Analytics to track Applicants conversion.
  * Added: Customize Header/footer of vacancy post (with HTML and shortcodes)
  * Added: Shortcodes can be used for the submit button and links in the customized header/footer
  
## Fixed ##
  * Fixed: Synchronization issues
  * Fixed: Check connection with Carerix: When no connection can be made, this could result in empty categories, and WordPress removes empty categories and its menu-items. Now when no connection is made, the categories won't be emptied.
  * Fixed: Title location shows partly in Post title
  * Fixed: Inline styling removed from (confirmation) message
  * Fixed: Broken application form
  * Fixed: Empty form after uploading CV through the Extra apply option
  * Fixed: Issues in application form (Country & region, Desired functions, Education, +Add extra document, mandatory fields and error reporting)
  * Fixed: Different date for driver licence expire date
  * Fixed: Validation in Application form
  * Fixed: Application Form visible in the header of a theme
  * Fixed: Save data form Motivation field in correct Carerix field
  * Fixed: Wrong email addresses fetched from system
  * Fixed: Save and fetch back all fields in Application form (some fields were not fetched)
  * Fixed: Certain Custom Post Types failed when CxPlugin is active
  * Fixed: Correct Link RSS feed
  * Fixed: Link for 'forgotten username/password' for login candidate
  * Fixed: Correct slug of candidate posts
  * Fixed: Small bugs, like issues with javascript, Lightbox popup, error messages webshims, Double javascript

## Previous versions ##
### Version 2.2.1 ###
  * 15 april 2014 | CxWordPress2 (v2.2.1)\\
  * Remove spaces in empty publication text (<p>&#160;</p>)


### Version 2.2 ###
  * Add data as custom fields to posts
  * Add option to sign up for newsletter
  * Add a Captcha to Job alert Form
  * Use the parameter of 'apply='
  * Option to show/hide Location in title
  * A list of posts for each medium
  * Add option for Cronjob (with specific URL) in order to trigger synchronization
  * Fixed: Save motivation field in correct Carerix field

### Version 2.1.4.5 ###
  * RSS feed link in jobdetails
  * Added option to rename taxonomies
  * Apply with LinkedIn feature (the current feature)
  * Fixed: Error after filling in Job alert subscription
  * Fixed: Automatic synchronisation (every 10 min)
  * Multiple fixes (Categories, Taxonomies, Region fields in (Open) Application form)
  * Removed the words 'Alpha version'

### Known Issues ###
The Carerix WordPress Plugin was tested to work in different browsers and WordPress versions. However we cannot guarantee, that the plugin will function with all third party plugins and server environments. See below the Plugins & Themes that we black- and whitelisted.

## Whitelisted Plugins or Themes ##
### Plugins ###
  * add-rel-plugin
  * AddThis
  * Akeeba backup
  * All in One SEO Pack
  * Autoptimize
  * BackWPUp
  * Breeze cache
  * Broken Link Checker
  * Comprehensive Google Map Plugin
  * Contact Form 7
  * Divi Builder
  * Elementor (https://elementor.com)
  * Elementor Pro (https://elementor.com)
  * Essential grid (https://www.essential-grid.com)
  * Google maps
  * Gravity Forms
  * Lazy Widget Loader
  * Lightbox Plus
  * Oxygen builder (https://oxygenbuilder.com)
  * Shareaholic
  * Share This
  * Social Share plugins
  * W3 Total Cache
  * WP Duplicator
  * WP-Optimize
  * What-the-file
  * Widget Context
  * Widget Controller
  * WPTouch Pro
  * WPML - WordPress Multilingual Plugin
  * Yoast WordPress SEO
  * ... (please notify us if you have additional ones)

### Themes ###
  * Avada
  * Divi
  * Hello (https://wordpress.org/themes/hello-elementor/)
  * Jupiter
  * Uncode
  * The7 (with workaround. Programmatically set "post excerpt" to "post title" in your child theme for vacancy posts. Else the apply form page is malformed)
  * ... (please notify us if you have additional ones)
## Blacklisted Plugins or Themes ##
  * **Avia Layout Editor** - Pages generated with Avia Layout Editor don't show forms generated by shortcodes. The Enfold theme makes use of the Avia Layout Editor.

### Issue tracking ###
<WRAP center tip>
If you have an issue with the plugin, please follow these steps:
  - Check whether your hosting server meets the technical requirements. Most errors occur because of PHP memory limit shortage, using an unsupported version of PHP or running behind an Nginx caching server. Also other serverside caching solutions like Kinsta-Cache can produce problems
  - Does the same issue occur on [[http://test.carerix.com/publictest/]] connected with the Carerix database on [[http://publictest.carerix.net/|Publictest]]  ?
  - Is the medium correct (use the code not de name!)
  - Does the issue occur in combination with other themes? Yes/No
  - Does the issue occur when you turn off all other plugins? Yes/No
  - Is the conflicting plugin [[cxwordpress2#known_issues|whitelisted or blacklisted]]? Yes/No
  - Are you using the latest stable version? Yes/No
We don't support any Beta version, so we advise to update to the [[cxwordpress2#release_notes|latest stable version]]. We highly recommend to install the plugin on a testlocation, we cannot and will not provide support for the plugin in a live website if it was not first tested in a test location.

If all above is Yes, please send an email in **English** to [[wordpress@carerix.com]] and provide us with the following:
  * Which plugins/themes conflict with the plugin?
  * Please turn on the Debug function, what is the output?
  * Please give us a precise description of the issue (when, where and how does the issues occur)? Please give us the recipe how we can reproduce the problem.
  * WP login credentials
  * FTP login credentials
  * Server info
  * Please provide us with a Duplicator package, so that our developers can clone the website to their own test location for further investigation (You can create this package with the plugin https://wordpress.org/plugins/duplicator/. With the WP login credentials we can download the ZIP-archive and installer file).

Our developers will look into it as soon possible. You will receive an email with ticket number to follow and communicate with the developer. This is meant for bugtracking and fixing only.

Note: Please don't send any email to support@carerix.com or helpdesk@carerix.com for API questions. Our 1st Line Supporters cannot help you with any API problems.
</WRAP>

BACK UP 
https://development.wiki.carerix.com/doku.php?id=cxwordpress2-getting-started




See also:
Carerix WordPress plugin 2 Technical information
Getting started guide

Installation

Carerix WordPress plugin
Upload & Install the plugin via the WordPress installer
Activate the plugin
Ask the Carerix administrator for the Application Name and Token (or follow the steps in https://help.carerix.com/en/articles/1958063-wordpress-plugin-activate-api)
Once you click 'Save', the publications etc are retrieved / synchronized every 10 min from Carerix.
Application Token
To implement the WordPress plugin, you as WordPress Administrator will be asked for the Application Token to authorize the Carerix plugin with your Carerix Application (applicationname.carerix.net).
To get the token you'll need to contact our support desk. We will generate a token and send it to you. WordPress plugin - Activate API
NB. The Jobs default page is created for reference purposes only. You should not use it otherwise. Instead use WordPress posts and blog listing (i.e. www.website.com/category/vacancies).

Email templates
Make sure that this e-mail templates are installed in the library of the Carerix application:
CxpeForgotPwd - e-mail sent to the candidate to resend the login details
CxpResetPwd - email used to reset the password for a candidate That can no longer access the original email account
JobAlert - Mandatory for sending job alert subscription emails.

Jobs summary
We recommend to use the blog list, eg. http://demo.carerix.com/plugin/en/vacancies/ So do not automatically generated jobs-default page, that page is purely for reference.
Other possibilities for job listings are on http://demo.carerix.com/plugin/en (submenus under jobs) and using plugins is more possible, for example, hang a blog list on a page, so you can create www.website.com/vacancies.

Several job listings (using Carerix media)
Medium 'web' is default, but you can show a different 'job flow' on the website. For example, a list of ZZP projects or jobs per establishment, all published to medium 'web2'.
You can do this by publishing to a different medium. You use this medium as follows:
In the Carerix application: Create a new medium, for example web2 (only admins can create a medium)
Publish least one job created for this additional medium
In WordPress, go to the Carerix WordPress plugin settings
Create a new job flow to (a new ‘Source‘)
Fill the medium behind http://appname.carerix.com/cxtools/wp_feed.php? as follows: medium=web2 and save
During synchronization, created an additional WordPress main category, it is given the name of this additional media.
You can show you the various job listings through blog lists or list of tags.
If you want to separate job each location you hang under the relevant plant in Carerix jobs. Then publish to the appropriate medium, such as the standard medium 'web' for Establishment and A? 'web2' for Company B.



NB: In Carerix publish your default to the medium 'web'. You do this in the settings of the Carerix WordPress plugin to fill out and you therefore blank.

Settings Job candidates (source feeds)
During installation By default, a job source feed created. That is the feed which determines how the associated jobs look like. This source is called Jobs default page. The corresponding medium is standard 'web'.
You can create several job feeds. Determine for each job source feed you which elements you do / do not want to show
Which form is linked to each of these jobs.
Introtekst per vacancy
RSS link
Tell-a-friend
Job subscription
Print
Any job source feed creates each vacancy published a posts in the right category (function), with the right taxonomy (Country & Region, experience, etc) (In addition, each job creates source feed a jobs page This page is named.. you specify (default Jobs default page). This is purely for reference)
You can combine several options to display a job list:
Default WordPress Blog List
Blog List combination with 3rd party plugin (see Recommended Plugins & Widgets)
Using the default page Jobs not recommended. (Installation will be created this page)

Synchronizing
The plugin will synchronize Jobs, Candidates etc every 10 minutes. You cannot change this interval.
To check quickly the result of your edits, you can synchronize Jobs, Candidates from Carerix manually:
Log into the WordPress backend
Go to the general Carerix settings
Click 'Synchronize new items from Carerix.
All job posts and job source page (with list of jobs) will be updated.


Make a (specific) form
By default is Form 1 installed. You can create a new (specific) form with the fields you want to show. Don't forget to connect this to the appropriate 'Source':
Log in WordPress
Go to (form) settings of the plugin Carerix
Create a new form
Select the fields to be shown
Save
Then go to Sources, scroll down and select the newly created form
Click save. All vacancies are synchronized and receive the new form
To use the Open Application: You should use the generated shortcode shown at the top of the form in the red bar
You can create a new form and link it to the desired Job feed source. For each form you can synchronize the fields Carerix. Note that you must first save the title of the form before you can synchronize. You can compose each form yourself by or (un)checking the appropriate (and/or required) fields.






Open Application
Required skill: Carerix administrator + Wordpress theme/frontend designer
Prerequisites: make sure in Carerix there is at least one job order tagged as an 'Open vacancy' and has an active publication generated from it. See also: How to make sure candidates can do an open application?
In Wordpress you can put the following shortcode in the contents of a page:
[cx_open_application]
If you want to use a specific application form, use the following format:
[cx_open_application openFormID="XX"]
Replace 'XX' by the application form ID. You can find the ID in the application forms list (Wordpress→Dashboard→Carerix→Application Forms) If you have multiple open vacancies in your Carerix system, you can add the Carerix publication-ID of the specific open vacancy as a parameter:
[cx_open_application openpubid="XX"]
Replace 'XX' by the ID of the publication of the open vacancy job order
Lastly you can combine the two like this:
[cx_open_application openFormID="3" openpubid="312"]

Multilingual Websites
The Carerix WordPress plugin supports multilingualism. To do this, you use a multilingual plugin. Carerix supports Multilingual Plugin WPML, the most popular plugin on multilingualism. We assume that you all vacancies in both Dutch as a 2nd language publishing (English in this example). Proceed as follows
Make Carerix in another medium (in tables). You've already medium 'web', add a new medium to eg code web-en 'for English.
Create an additional publications of a job
One publication (1st language) already has the medium 'web'. Make an extra publication of the same job 'and web (2nd language) with it. Please note that this publication contains the texts in the 2nd language.
Go to the WordPress Website
Install WPML and adjust it as desired
Go to the Carerix settings and synchronize all items Carerix
In the list of all messages (posts) you can see which posts have been published in any language

NB: Please note that the 'Translation Options' of WPML are good.
WPML → Translate Options
Optionally sync again


Without multilingual plugin
IMPORTANT! You can do steps below only in case when WPML plugin is NOT installed. If you have WPML plugin please skip this section!
You can also show jobs from different languages ​​(different mediums) without multilingual plugin:
Create a medium (per language) a separate job to feed source,
On Set Feed Source Parameters Add 'medium=web' and as parameter behind /cxtools/wp_feed.php?
You now have several job feeds, jobs are created as separate jobs in the'd really rather know categories. The page is created only displays the jobs with the medium 'and web.


Job boards
How can I make candidates through job boards are sent to the correct page on my website to apply
If desired, change the text of the web template confirm. Beware of <brackets> and anyway make a backup of the code (copy paste in text file) and a screen shot of the settings.
Determine the settings of the WordPress plugin which form you want to show to candidates via a job board. Through Carerix settings → Forms Settings → Select the form 'Form to be used on apply from job board.
Change in the Carerix Apply_url. So that candidates from a job board will visit the website to the relevant job where they want to apply for. Use the following code for the apply_url (Settings → Attributes and Fields → Apply_url)
http://www.domainname.com/?pub_id=<cx:write value="$publication.publicationID"/>
this results i.e. in http://www.domainname.com/?pub_id=123 en shows the specific publication to the visitor
Regarding InGoedeBanen: By default there a candidate cannot be traced if he comes via a job board. This is because an IGB single vacancy publication is given to x number of job boards.


Newsletter subscription
Candidates can register for the newsletter.
Enable the checkbox 'Newsletter subscription' in the desired application form (Wordpress→Dashboard→Carerix→Application Forms). Note that newsletter subscriptions are always part of the application form and not available as “stand-alone” signup widget.






Job alerts
In WordPress you can use this shortcode to show a form for job alerts (vacancy subscription). When candidates signup they will receive emails in the future containing vacancies that fit their selected criteria, on a daily basis.
See the example in https://plugin.carerix.com/sollicitatieformulieren/jobalert/
The following fields will be displayed in the form:
Email address
First name
Last name (and prefix)
Gender
Country selection preference (only if multiple countries are published in Carerix)
Three “sub region” selector preferences like provinces, counties and departments (only if these are published in Carerix)
Two function group preferences with an optional parent business-line selector (the business-line selector will only appear if multiple business-lines are published in Carerix)
Agreement to terms checkbox (also enforces the storage term of the personal information to comply to GDPR)
Anti bot abuse system (by captcha)
The process for the candidate is as follows:
Candidate selects the criteria to receive job opportunities for and submits the form
Candidate receives an opt-in activation mail and clicks on the activation link
Candidate starts receiving mail with (new) vacancies on a daily basis that match the selected criteria
To cancel, the candidate can use the unsubscribe link in the job alert mails

Step 1: Preparation in Carerix
Follow the steps in the following help article: https://help.carerix.com/en/articles/1954170
Make sure the email template called “Vacature abonnement bevestiging” (Vacancy subscription confirmation) is also installed. It has the code web-subscribe and it's not described in the help article.

Step 2: Preparation in Wordpress
Create a general page and paste the following shortcode in the content:
[cx_job_alert_subscription]
Optional attributes are can be added to control the confirmation message.
Set a custom confirmation message:
[cx_job_alert_subscription confirmation_message="Thank you for subscribing. Shortly you will receive an email with an activation link. After activation you will start receiving new job opportunities in your mailbox on a daily basis!"]
Set a custom page/url for the confirmation message:
[cx_job_alert_subscription confirmation_url="/jobalert_thank_you/"]

Step 3: Fine-tuning in Carerix
In Carerix, you can fine-tune the following candidate criteria for the job alert form:
Country selection
Business-line selection
Function group selection
For the following instructions you need to be familiar with Carerix Tables editing. The principles explained in Table management are used to edit the tables.
The following table items are used:
For countries the table 'Land' (country)
For business-lines the table 'Vakgebied' (business-line)
For function groups the table 'functie0'
Shorten the country selection
If your working area is a single country (or a few) you can shorten the dropdown box of countries.
For each country you want to disable in the job alert form, edit the item, and uncheck the box “not for web”.
Note: if you only enable one country, the country selection is disabled on the job alert form.
Shorten the business-line selection
In Carerix every function group can be connected to a business-line. If one or more function groups are connected to a business-line the business-line dropdown box on the jobalert form will appear. So if you don't work with multiple business-lines, you need to configure the business-lines as follows:
Edit each business-line item in the table “vakgebied” (business-line) and enable the checkbox “not for web”
Locate the business-line “Standaard” (default) and disable the checkbox “not for web”. This leaves you with one mandatory business-line which will NOT appear for candidates on the job alert form
Finally, in Wordpress, go to Dashboard→Carerix→Application Forms→Tab: Settings, and click on “Clear DataNodes cache”
Configure/shorten function group selection
Edit each function group item (table: functie0) you want to include in the group selection for the candidates. Disable 'not for web' and enable each desired business-line you want to connect the function group to. You need at least connect it to one business-line
Finally, in Wordpress, go to Dashboard→Carerix→Application Forms→Tab: Settings, and click on “Clear DataNodes cache”


Settings Carerix

Change ApplyURL
Change ApplyURL so links in email templates refer correctly to the website. Change the link for the apply_url (Settings → Attributes and Fields → Apply_url)
http://www.domainname.com/?pub_id=<cx:write value="$publication.publicationID"/>
This provides e.g. http://www.domainname.com/?pub_id=123. The plugin will redirect to the appropriate job

Modified URLs
How do I create links to jobs in my emails, alerts and newsletters?
Add to the link in your template: pub_id = xxx, where xxx is the Publication ID \\.
For example http://www.website.com/?pub_id=123
Create link to a template with the website URL: website.com/pubid/xxx, where xxx is the pubID \\.
For example http://www.website.com/pubid/123

Applicant Source Tracking
The apply page supports 2 new GET parameters cx_applysource and cx_applytags as of version 2.14.36
Usage example
https://somecustomer.com/vacancy/1234/apply?cx_applysource=Google&cx_applytags=jobboard.nl,paid,regionA
NOTE: The apply parameters are being stored in a cookie for 30 days. If the same candidate applies for another vacancy through another URL e.g. When a candidate submits the apply form the tracking values will be automatically saved in Match details and become visible in Carerix application as Apply Source and Apply Tags fields in Matches details.
If yours wordpress configured differently and you are not using default urls, be sure that redirect from job board will land on apply page. Usually it is enough to provide apply=true parameter in the url
https://somecustomer.com/vacancy/9876/apply
The resulting match will be created with previous tracking values.


FAQs
The Carerix WordPress plugin is the connection between the Carerix application and the WordPress website. Therefor there are certain roles/rights for different tasks:
Carerix administrator: Has the administrator user role and is able to manage the Carerix data-tables (e.g. Country table), mediums and email templates.
Wordpress administrator: Webbuilder with rights to manage the settings of Wordpress, can install/configure plugins and knows how to create/edit pages (with sidebars). HTML skills are usefull

How do I get the Application Name and Token?
Application name is: applicationname.carerix.net
For the Application Token see: Application Token

Why don't I see any vacancies?
Jobs are displayed under the following conditions (You need Carerix administrator rights for this):
In Carerix, the medium-code of publications have to be set to web
(or intentionally match a custom medium-code which is used in the plugin)
Last publication date is on or after today. Please note, check if necessary in the Carerix application:
Publication Basic tab: Last publication date
Publication Admin tab: Closing date
Job: Start Date
To verify you can look at https:/ / applicationname.carerix.com/cxportal, containing all vacancies are displayed according to the above condition (medium = web) (substitute 'applicationname' to the name of your Carerix application)

Why can't I edit the job posts?
Yes, you can manually add a Featured Image (open the job post and add Featured image). (Be aware that manual changes in the job posts texts are overridden by the next vacancy sync, but as the featured image is not part of vacancy syncs it won't be removed)
You can check by forcing a manual sync: Located in Wordpress → Dashboard → Carerix → Settings → Tab Settings → Button 'Synchronize new/changed items from Carerix'.

Can I show the application form below the vacancy texts?
Yes, go to Wordpress → Dashboard → Carerix → Sources
For each source, locate the section Publication Details Footer, and replace the shortcode [cx_apply_button] with [cx_apply_form]. From now on, the apply button (which links to a separate application page) is replaced by the application form.

Can I show a featured image in a vacancy post?
Yes, you can manually add a Featured Image. Simply open the job post and add Featured image. You need editing rights in WordPress. Be aware that manual changes in the job posts texts are overridden by the next vacancy sync, but as the featured image is not part of vacancy syncs it won't be removed.
You can check by forcing a manual sync: Located in Wordpress → Dashboard → Carerix → Settings → Tab Settings → Button 'Synchronize new/changed items from Carerix'.

Can I add an image within the paragraphs of the vacancy texts?
Yes, you can add HTML in the publication text, so you can add a Youtube video as you would in a WordPress post. In the Carerix application the Carerix user needs to add a little piece of HTML code in the publication text:
In the Carerix application open the publication text where you want to add the image
Switch the editor to HTML mode
Insert the HTML-image-tag in the HTML source code. For example:
<img src="https://carerix.com/.../carerix-logo.png" alt="ALT Text" />
Save the changes
Sync the WordPress plugin on the website

Can I add a youtube video into the vacancy text?
Yes, you can add HTML in the publication text, so you can add a Youtube video as you would in a WordPress post.
In Carerix edit the desired publication text where you want to insert the video.
You can simply insert the youtube link, for example:
https://www.youtube.com/watch?v=4bUS0k5L6v8
Or you can use the shortcode:
[embed width="600px" ]https://www.youtube.com/watch?v=4bUS0k5L6v8[/embed]
Save the changes
Sync the WordPress plugin on the website

It seems as if the jobs do not sync?
Required skill: Wordpress administrator
Perhaps you have moved jobs to the trash. Remove them permanently from the trash. After synchronization, they are recreated again and are visible.
Furthermore, if you use the “Synchronize by REST-API (beta)” setting (WP Dashboard → Carerix → Settings → Tab Settings), make sure you do a full jobs sync by clicking on the “Enforce full sync of all items from Carerix” button.

Can I create a custom text confirmation or confirmation page?
Yes, that's possible. You need Wordpress administrator rights and do the following:
Go to Wordpress → Dashboard → Carerix → Applicaton Forms and open the desired form
Select bottom of the form to 'Confirmation message' if you want a standard confirmation text if you want to refer to a specific WordPress page. You can also enter a URL.


Can I monitor conversions with Google Analytics?
Yes, that's possible:
Make sure the Google Analytics (page) tracker code is already present for all site pages
Create a specific Wordpress page as 'Thank you page' (see above)
In Google Analytics you can track the statistics of this page)
You could also add this as one of your Goals (for more advanced users)
Also see Applicant Source Tracking for tracking candidates in Carerix throughout their application process.

Show Candidates on a website
Candidate information is not available anymore because of General Data Protection Regulation (GDPR).

How to search / filter by taxonomy?
You need WordPress administrator rights to add a plugin with this feature.
Jobs include taxonomy by Country and Region, Function and Training. These can be used with other plugins or widgets. For example, the 'Search & Filter' plugin. See Recommended Plugins & Widgets.
Try this shortcode as a 'getting started' in a sidebar widget if you use the 'Search & Filter' plugin:
[searchandfilter taxonomies="search,category,region,education,functiongroups,procedure" order_by="date" hide_empty="1" submit_label="Search" search_placeholder="Search"]

Can I use a search radius from a postal code area?
With the 'Carerix Search widget' it is possible to search by radius. These can be found under Wordpress → Dashboard → View → Widgets. You need WordPress editing rights. However, if you use a third party search-plugin (like Search & Filter or Jet SmartFilters) you cannot use this radius function because of technical limitations.

See the example in http://demo.carerix.com/plugin/zoeken-filteren/

Can I change the styling of various plug-in elements like headings and forms?
Yes, the plugin has minimal styling so it basically follows the theme used. Additionally, you can of course use their own styling. We recommend that you do this in a child theme. If you wish to update this theme than this stylesheet is in fact not overwritten.
see also Tips & Tricks about styling

Can I make a form 'Create Job' (submit a vacancy)?
The plugin does not support this functionality.
You can create a 3rd party form (e.g. plugin Contactform7) to offer this. However you still need to manually process this submission in Carerix (create client and job order).

The titles and buttons show in the wrong language?
Required skill: Wordpress administrator

Assuming you use the site in a single-language setup.
The plugin follows the language of the website as set in Wordpress→Dashboard→Settings→General. If you change the site language to Dutch than all the titles of the jobs will be regenerated (after a fulle jobs sync).
Please note: Some links could change due tot the language conversion .

Can I change the text of the headings, labels, buttons for vacancy texts and application forms?
Required skill: Wordpress theme/frontend designer
Yes, starting from version 2.21.0 this is possible.
New method
You need (s)FTP credentials for the WordPress website to do this. The idea is to override portions of the plugin's language file within your own child theme. That way you are sure the language modifications aren't reverted when a new plugin version is released.
In this example we will change the heading text “Introductie” (introduction) which appears in the vacancy texts. We assume you've set the Wordpress site language to Dutch and have the site running in a child theme.
1. Create a blank PHP-file called nl-NL.resources.php in {WORDPRESS-ROOT}/wp-content/themes/your-child-theme/CxWordpress/assets/resources/ Change your-child-theme to your child theme directory name and create the subdirectories (CxWordpress/assets/resources) if needed.
2. Edit the new file nl-NL.resources.php as follows:
;<?php die()?>

[CxPortal.message.field]
introduction = "Intro (formerly Introductie)"
requirements = "Wat neem jij mee? (formerly Functie-eisen)"
offer = "Wat bieden wij? (formerly Aanbod)"
organization = "Over deze werkgever (formerly Organisatie)"
function = "Wat ga je doen? (formerly Functie)"
information = "Meer informatie (formerly Inlichtingen)"
application = "Solliciteren bij (formerly Sollicitatie)"
closingDate = "Sluitingsdatum (formerly Sluitdatum)"

[general.button]
apply = "Versturen (formerly Solliciteren)"
3. Do a full sync from Carerix to regenerate the job posts (Wordpress→Dashboard → Carerix → Settings → Button “Enforce full sync of all items from Carerix” or “Synchronize new/changed items from Carerix”)
Notes:
Our new file nl-NL.resources.php is based on {WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/assets/resources/nl-NL.resources.php. You can copy all desired elements from there to your own resource file.
Each section of language elements starts with a section heading [xxxxxxx] (recognized by the brackets).
Alternative method
To change the default titles or lyrics of the plugin, you could use this plugin: Real-time Find and Replace allows you to change text or HTML code (client-side), eg. You could modify the HTML code like in the example below:


How do I show the vacancies in other languages ​​on a multilingual website?
The Carerix plugin works perfectly with WPML, one of the best WordPress plugins multilingual. The price of +/- € 80 for WPML is worth it, see https://wpml.org/
Use Carerix media such as 'web' and 'web-fr' etc … and publish jobs to the appropriate medium for each language. The plugin will automatically use the medium, every job post will be created in the language installed on as WPML and corresponding to the used medium.
For example
Publication 1 with Dutch text (Vacancy 123 published to web)
Publication 2 with English text (Vacancy 123 published to web-en)
Publication 3 with French text (Vacancy 123 published to web-fr)
Publication 4 with German text (Vacancy 123 published to the web-de)
etc
Use the medium code web-XX ', where XX is the ICU Locale is a language.
N.B. Suppose you already publish vacancies in Dutch. Then you don't want to lose or have to re-publish vacancies while implementing the multilingual feature. You can change media very simple in the Carerix Application: Rename 'web' to 'web-en'.
Note : Do this only if WPML is arranged on the site, the plugin will pick this at the next synchronization. Standard reads the plugin 'web'.
For more text and explanation Getting started guide: Multilingual websites

Can I offer an RSS feed of all job vacancies or by function?
Required skill: Wordpress administrator
Yes, before you can use standard WordPress RSS feeds. The URLs for this example:
/Category/publications/feed /
/Tag/Utrecht/feed/
For an example http://demo.carerix.com/plugin/category/vacancies/feed/

Can I submit a sitemap to Google Search Console?
Yes, use the following URL:
https://your-website.com/?carerix_sitemap

When I enable 'Google For Jobs' why do I get warnings from a (structured data) testing tool?
These are warnings and not blocking errors.
Google recommends you to provide detailed information about the vacancies. At the moment it's not possible to fully map the Carerix vacancy information to the Google For Jobs structure. But the most important data is covered
Also, Google For Jobs wants to know the address location of the jobs. Most clients of Carerix don't want to reveal this because it's sensitive business information. So this high level of detail is left out.

Can I customize the labels in the URL (such as ../category/, ../publications/ etc)?
No, this can not (yet)

I want to use my own social media plugin to share jobs. Is that possible?
Required skill: Wordpress theme/frontend designer
Yes, that's possible. The job source feed check your social media out. And installing your own social media plugin.
See Recommended Plugins & Widgets. We recommend Shareaholic wholeheartedly. }

Why should I enable this: 'Reporting its location'?
We can continue to make the plugin better and better with the necessary feedback that we receive from the plugin. No vacancy or candidate data is send, so there is no privacy issue, and it gives no performance issues.

How to enable logging and where is the logfile?
You can enable the logging in Wordpress → Dashboard → Carerix → Settings → Tab Settings. The logfile is created in
{WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/tmp/logs/
The logfile directory can grow fast in size which may lead to your site running out of diskspace. So make sure you only enable it if you experience problems.

Where are the uploaded documents?
Candidate documents (e.g. a CV because of a job application) are submitted to the Carerix system, but temporarily uploaded to the following folder to process it:
{WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/tmp/uploads/
After a few hours the files are automatically removed by the plugin and will only reside in the Carerix system.
Note: make sure you have disabled “developers logging” (see elsewhere in this FAQ), because candidate details (needed for debugging) are stored in the logfile too.

I got a warning some directories are not writeable by PHP?
Carerix Warning: The Following directories are not writeable by PHP
Please make sure all subdirectories of {WORDPRESS-ROOT}/wp-content/plugins/CxWordpress/tmp/ are writable by PHP. Generally you can change these permissions by your (s)FTP client.

Why not Custom Post Types instead of regular posts for vacancies?
There are pros and cons to read jobs Custom Post Types in Wordpress.

Benefits
Templates: Web builder can use a custom template specifically for job post types.
Filters: 3rd Party filters specifically for Custom post types are set
Consistency: Difference between news and jobs is clearly in the admin area.
Disadvantages
Blog post listings: It is not possible to show vacancies in major blog listing.
Compatibility: Switch between regular and post types Custom post types can cause synchronization problems.
Currently we have chosen to jobs not offering as Custom Post Types because many of our customers use the standard features like blog listing.

I see tailstocks without text

Perhaps there is a space in your publication text. Because the field contains the text shown on the website, including the head. Check the according publication text in the Carerix application, as in the example above:
You can also clean the publication text by clicking on the button 'Code' and editing the code. In this case some HTML knowledge would be handy. In this case you have to remove the code <p>&#160;</p> , see example below:


How to use the 'cxwordpress_post_updated' hook?
Required skill: Wordpress theme/frontend designer with PHP knowledge
With this hook you can apply changes to a vacancy-post upon (creation/update) to have it better fit into your site/theme. It's useful to apply changes in text formatting or post-statuses.
Example, edit the file 'functions.php' in your activated child theme. Add the following:
function my_cx_post_preparation(array $postids, array $data, array $cxfields ) {
  $post_id = (int) $postids[0]; // First item is the WP post ID
  $post_data_v1 = $data[0]; // The original data that the CX WP plugin has saved/updated
  $_post = get_post( $post_id ); // Another way to access the post data
  $post_cxfields = $cxfields[0]; // First item holds an associative array of retrieved (raw) CX fields
  $pub_id = get_post_meta($post_id, 'guid', true); // CX publication ID
  
  
  // Example to retrieve some specific CX fields
  $cx_requirements = get_post_meta($post_id, 'requirementsInformation', true);
  $cx_function_group = get_the_terms($post_id, "functiongroups")[0]->name ?? "";
  $cx_function_name = get_the_terms($post_id, "functions")[0]->name ?? "";
  $cx_min_salary = $post_cxfields['minSalary'] + 0;
  $cx_max_salary = $post_cxfields['maxSalary'] + 0;
  $cx_period_salary = $post_cxfields['salaryPeriodClassification']; // MonthTag = per hour, HourTag = per month, etc.
 

  // Example to update the post content
  $_post ->post_content = "<h1>Hook `cxwordpress_post_updated` altered this post contents!</h1>" . $_post ->post_content;
  wp_update_post( $_post ); // Update post

  
  // Example to set post meta info. This is specifically for posts in the Divi theme. Note "_et" is an abbreviation for Elegant Themes.
  update_post_meta( $post_id, '_et_pb_page_layout', 'et_full_width_page'); // force Divi post as a full width page
  update_post_meta( $post_id, '_et_pb_show_title', 'off'); // turn Divi post titles off
 

  // Clean cache  
  wp_cache_delete( $post_id, 'posts' );
}

// Add the hook with prio 3 (default) and accepting 3 arguments
add_action( 'cxwordpress_post_updated', 'my_cx_post_preparation', 10, 3);

Create your own adjustments to the plugin
If someone alters (the code of) the plugin this will invalidate any form of support. Carerix can not support customizations. Also customizations will be lost at each update of the plugin!


Recommended Plugins & Widgets

Multilingual
The Carerix plugin works perfectly with WordPress Multilingual Language (WPML), one of the best WordPress plugins multilangual. The price of +/- € 80 for WPML is well worth it. https://wpml.org/
for more text and explanation: Carerix Plugin and multilingual websites

Search & Filter

http://wordpress.org/plugins/search-filter/ (Search & Filter)
http://wordpress.org/plugins/query-multiple-taxonomies/ (Query Multiple Taxonomies)
http://wordpress.org/plugins/cat-tag-filter-widget/ (Cat + Tag Filter)
http://codecanyon.net/item/taxonomies-filter-widget/full_screen_preview/4282257 (paid)

Related Jobs
http://wordpress.org/plugins/related-posts-by-taxonomy/
http://wordpress.org/plugins/wordpress-23-related-posts-plugin/
http://wordpress.org/plugins/nrelate-related-content/

Page / Post related widgets
http://wordpress.org/plugins/conditional-widgets/
http://wordpress.org/plugins/display-widgets/
http://wordpress.org/plugins/dynamic-widgets/
http://wordpress.org/plugins/widgets-controller/
http://wordpress.org/plugins/widget-context/
http://wordpress.org/plugins/widget-logic/

Social Sharing
http://wordpress.org/plugins/shareaholic/

Jobs at
http://wordpress.org/plugins/advanced-post-list/
http://wordpress.org/plugins/list-category-posts/
https://wordpress.org/plugins/sorttable-post/ (not maintained, but it works)
http://wordpress.org/plugins/category-post-list-widget/

Other
Remove extra blank line below the intro text:
https://wordpress.org/plugins/wpautop-control/


Tips & Tricks

Styling
Styling of the radio buttons (behind the input field):
{.carerix_labels
display: inline;
border: none! important;
}

Hide titles in vacancy text
(i.e. Introduction)
In the excerpt of posts you can hide titles:
div.post-body h4.cx_h4 {
display: none;
}

Hide titles job description in widget
In the standard 'Recent Posts' widget allows you to hide cups approximately as follows:
div # posts-3.widget.widget_posts div.inner p ul li: first-of-type {
display: none;
}
You can use the IDs of the sections in the Application Form for styling:
#personal,
#contact,
#address,
#motivationAndSource {
background: #EEE;
}
That way you can styling alternating rows, eg .:
#personal div: nth-child (odd) {
background-color: #fff;
width: 100%;
border: 1px solid #CCC;
padding: 5px 10px;
}

Truncate text or titles
Example how to cut through CSS titles and / or text, as in the attached example.

.box {
-o-text-overflow: ellipsis; / * Opera * /
text-overflow: ellipsis; / * IE, Safari (WebKit) * /
overflow: hidden; / * Do not show excess chars * /
white-space: nowrap; / * Force single line * /
width: 300px; / * Fixed width * /
}

Extra blank line
Job posts sometimes display an extra blank line after the 'Introduction'. This is because Wordpress automatically add a blank line after the 'Read more' code. You can remove it by adding the following to the functions.php in your theme (at the bottom, before the closing>?):
remove_filter ( 'the_content', 'wpautop');
You can also use this plugin https://wordpress.org/plugins/wpautop-control/

List of vacancies filled in WordPress
Add a meta tag in the Carerix application, such as 'medical' (via Publications → Admin tab)
These meta tags are published in the WordPress Post, each publication receives it's meta tag(s).
You can use this meta tag in a URL, like www.website-name.com/tags/medical and you see the list of all jobs with this tag (you can find this list also through the WordPress Admin → Messaging → Tags → 'Medical' View)


Create RSS feeds per category
Build an RSS feed for all your jobs as posts in WordPress or build a Feed for each Category or any tag. Use the built-in feature of WordPress for generating feeds.
Ex: Build the feed for category = publications on website example.com like this:
http://example.com/category/publications/feed
This will result in a standard RSS page containing all posts from category publications as generated by the Carerix plugin.
Read about all options and variants you can use: http://codex.wordpress.org/WordPress_Feeds


Known Issues

No default theme
If you use a self-made theme: Use Php code 'the_content ()' not 'get_the_content ()'.

The layout of my website is staggered (eg. Double application). How do I fix this?
Perhaps this is due to the WordPress SEO plugin 'Add Open Graph meta '.
Turn this feature off: WordPress SEO (Yoast) Social → → → Add Facebook Open Graph meta data

Error RSS feed
I get an error when I use the RSS feed of my WordPress site open (../category/publications/feed) and thus also the RSS feed of vacancies and / or candidates. This error is caused by a character in the 'Title' which disrupts the RSS feed.

Comprehensive Google Map Plugin
The Comprehensive Google Map Plugin version conflicts with CxWordPressPlugin. Updating the Comprehensive Google Map Plugin to the latest version will solve the issue. CxPlugin Protects itself as much as it can against other plugins, but it can not be protected if other plugins If you'll check the update log for the Comprehensive Google Map Plugin, you'll see That it had fixed its javascript bugs after version 8.0.0.

Captcha is not shown
If the Captcha is not or not displayed properly, it may be that you do not appear correctly Session path. This is a setting on the server.
Solution: Ensure that the path of the 'session.save_path' exists and is writable.
Go to the Control Panel of your server, go to the PHP settings, the section 'session.save_path'. Fill in a writable path. Example: /var/www/vhosts/website.com/private/php_sess/

Slideshow does not show
(Level slider, part of Triassic website)
This issue is related to the level slider embedded in the theme. You can find many similar problems all over the internet. The solution is to disable the loading of the jquery.nivo.slider.pack.js from the plugin:
Go to /wp-content/themes/trias/plugins/slideshow/slideshow.php, find and comment out this code
wp_enqueue_script (level-slider script, get_template_directory_uri () '/plugins/slideshow/nivo-slider/jquery.nivo.slider.pack.js', array ( 'jQuery').);
Place this code in the footer of the theme, under <? Php wp_footer (); ?>
<Script src = '<? Php echo get_template_directory_uri ();?> / Plugins / slideshow / level slider / jquery.nivo.slider.pack.js' type = 'text / javascript'> </script>

error on getOwner, no open publication
Error message: “Call to undefined method Carerix_Api_Rest_Collection::getOwner()”. Explanation: mostly this is caused because there is no active publication by the Open Vacancy.

cxwordpress2-getting-started.txt · Last modified: 2023/04/12 15:35 by 127.0.0.1

Page Tools
    


