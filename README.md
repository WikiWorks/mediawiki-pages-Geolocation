# Geolocation package

Provides a collection of wiki pages for easy inclusion of Geolocation fields and semantics in Mediawiki projects. 

# Requirements
* SemanticMediaWiki
* PageForms
* Maps
* ParserFunctions (with `$wgPFEnableStringFunctions = true;`)
* PageExchange or PagePort

# Setup

## via PagePort 

* download the repository
* run `php extensions/PagePort/maintenance/importPages.php --source ~/mediawiki-pages-Geolocation`

## via PageExchange

* add the following to the bottom of your `LocalSettings.php`: `$wgPageExchangePackageFiles[] = 'https://raw.githubusercontent.com/NationalGalleryOfArt/mediawiki-pages-Geolocation/main/page-exchange.json';`
* navigate to `Special:Packages` and install the package
* (optional) from the wiki root, run `php maintenance/runJobs.php`

# Usage

## Transclude into the form

Transclude the [Geolocation fields set](https://github.com/NationalGalleryOfArt/mediawiki-pages-Geolocation/blob/main/Template/Geolocation%20field%20set.mediawiki) into your form once:
```
{{Geolocation fields set}}
```
Note, the field set is intended to be included as rows into an existing table with the other form field annotations. If you do not use a table layout in your form, wrap the template call:
```
{| class="formtable"
{{Geolocation fields set}}
|}
```
To use `feeds to map` feature, add the host template name as a parameter. For example if the template we call the geolocation field set from is called `Person`, put: 
```
{{Geolocation fields set|Person}}
```

## Features

* Full address string
* Coordinates calculation based on the full address
* Map input for setting coordinates manually
* Printout settings (coordinates|message|suppress)

See examples at [Project:Geolocation](https://github.com/NationalGalleryOfArt/mediawiki-pages-Geolocation/blob/main/Project/Geolocation.mediawiki)


