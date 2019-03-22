# WebCare integration
External developers can integrate WebCare into their websites, CM - Systems or Webshops. Examples would be our Magento integration or modules for WordPress or Typo3

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

Those IDs consist of alphanumerical characters (case sensitive) and a "-" sign. No spaces are allowed.

The IDs are used to build the path for the included contents (CSS and JavaScript files) to include in your HTML code.

Paths are always built using the following scheme:

    https://webcache.datareporter.eu/c/<ClientID>/<OrganizationID>/<WebsiteID>/<Filename>.<Extension>
    
or (without the optional Website ID:
    
    https://webcache.datareporter.eu/c/<ClientID>/<OrganizationID>/<Filename>.<Extension>


