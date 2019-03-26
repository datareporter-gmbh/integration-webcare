# WebCare integration
External developers can integrate WebCare into their websites, CM - Systems or Webshops. Examples would be our Magento integration or modules for WordPress or Typo3

# Existing integrations
Existing integrations are:

* Magento 2: https://github.com/datareporter-gmbh/module-webcare
* WordPress: in Development, arriving soon (March 2019)

# Prerequisites
You would need an active WebCare installation to generate the needed IDs and files for your website. However, you can use our demo keys for development as the integration will not change (except for those IDs).

The demo IDs for an organization are:

    Client ID: cac205cf-151f-4694-a7eb-4eadfe543cbe
    Organization ID: jeSnrpV83Ln

The demo IDs for a single website in an organization are:

    Client ID: cac205cf-151f-4694-a7eb-4eadfe543cbe
    Organization ID: jeSnrpV83Ln
    Website ID: q68

# Description for the IDs
There are three IDs, and one of them is optional:

* Client ID: Identifies the client (mandatory)
* Organization ID: Identifies the organization of the client (mandatory)
* Website ID: If the organization has multiple websites, this ID identifies the website (optional)

The IDs are used to build the path for the included contents (CSS and JavaScript files) to include in your HTML code.

Paths are always built using the following scheme:

    https://webcache.datareporter.eu/c/<ClientID>/<OrganizationID>/<WebsiteID>/<Filename>.<Extension>
    
or (without the optional Website ID:
    
    https://webcache.datareporter.eu/c/<ClientID>/<OrganizationID>/<Filename>.<Extension>

# Best Practice for Modules
When designing a module GUI you should keep ease of use in mind. Simply let the user enter those IDs and alert them if one of the mandatory fields is not entered.

For the privacy statement and the imprint, use the preferred way of your system to place the content where it should be displayed on the website.

For the cookie banner, use the preferred way of your system to include the banner on every page in your website (like the page header).

# Cookie Banner integration
The cookie banner integration code containing the demo IDs would be:

```html
<link href="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/q68/banner.css" rel="stylesheet">
<script src="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/q68/banner.js"></script>
<script>
  window.cookieconsent.initialise(dr_cookiebanner_options);
</script>
```

In this case, the paths are generated with the optional website ID. This can be omitted.

The code can be included in your website between your ```<body> ... </body>``` tags. Nothing more is needed to show the cookiebanner and remove cookies without the user´s consent.

Styling of the cookiebanner and its options are managed using the WebCare GUI.

# Privacy Statement integration
The privacy statement integration code looks like this:

```html
<script src="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/privacynotice.js"></script>
```

In this case, the website ID is not included.

The code should be included exactly in the place where the privacy statement should appear (the integration code is replaced by the HTML - generated privacy statement)

The styles used in the privacy statement are default HTML styles like ```<h1>...</h1>```, ```<p>...</p>```and so on, so if your page stylesheet covers the default tags, you should be fine.

## Alternative integration with div tag
For some CMS systems it may be necessary to separate JavaScript code and the insertion place. In this case you can opt to integrate using our "v2" versions of the integration. You can simply add "\_v2" to the javascript filename - resulting in a filename ```privacynotice_v2.js```.

Using this, you can add an empty div tag to your website with the id ```dr-privacynotice-div``` where the privacy notice will be inserted when page loading has finished.

This is how the integration would look like:

```html
<script src="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/privacynotice_v2.js"></script>
...
<div id="dr-privacynotice-div"></div>
...
```

# Imprint integration
The imprint integration would look like this:

```html
<script src="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/imprint.js"></script>
```

** As the imprint is always generated for an organization, no website ID is allowed here! **

The code should be included exactly in the place where the imprint should appear (the integration code is replaced by the HTML - generated imprint)

The styles used in the imprint are default HTML styles like ```<h1>...</h1>```, ```<p>...</p>```and so on, so if your page stylesheet covers the default tags, you should be fine.

## Alternative integration with div tag
For some CMS systems it may be necessary to separate JavaScript code and the insertion place. In this case you can opt to integrate using our "v2" versions of the integration. You can simply add "\_v2" to the javascript filename - resulting in a filename ```imprint_v2.js```.

Using this, you can add an empty div tag to your website with the id ```dr-imprint-div``` where the imprint will be inserted when page loading has finished.

This is how the integration would look like:

```html
<script src="https://webcache.datareporter.eu/c/cac205cf-151f-4694-a7eb-4eadfe543cbe/jeSnrpV83Ln/imprint_v2.js"></script>
...
<div id="dr-imprint-div"></div>
...
```


# Congratulations
You are now good to go implementing a module for your favourite CMS or WebShop. 

Please let us know if any questions arise or something is not entirely clear. 



