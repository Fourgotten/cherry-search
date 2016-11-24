[![AUR](https://img.shields.io/aur/license/yaourt.svg?maxAge=2592000?style=plastic)](https://github.com/CherryFramework/cherry-search/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/CherryFramework/cherry-search.svg?branch=master)](https://travis-ci.org/CherryFramework/cherry-search)

# cherry-search
WordPress plug-in for quick and easy search for information on your site.

## Authors
[@Behaart](https://github.com/MakhonkoDenis) - **Developer**

## Help
Found a bug? Feature requests? [Create an issue - Thanks!](https://github.com/CherryFramework/cherry-search/issues/new)

# Cherry Search #
* Requires at least: 4.4
* Tested up to: 4.6.1

# Description #
With this plugin you will be able to add advanced search functionality to your WordPress website. It is multilingual, and is fully compatible with WooCommerce themes, so you can enhance your eCommerce website with a powerful conversion booster.
The plugin is based on AJAX, which means that the results will be displayed dynamically. Your visitors will immediately see not only the titles of suitable search results, but also their image previews, author, date and other metadata.

[Online documentation]( http://documentation.templatemonster.com/index.php?project=cherry_search "Cherry search documentation" )

# How to use? #
There are several ways to enable the plugin on your website. You can either:

1. Turn on a “Replace the standard search” option in your dashboard
2. Insert a shortcode **[cherry_search_form]** into any element of the layout
3. Or insert the following PHP code into the necessary files of your website:
`<?php if ( function_exists( 'cherry_get_search_form' ) ) { cherry_get_search_form(); } ?>`

# Changelog #
## 1.0.0 ##
* Initial release

# Arbitrary section #

## Plugin Settings##
Once the plugin is installed you can see a Cherry Search button in the right sidebar of your admin panel:

### Main Settings ###
Here you can find major plugin settings:
* **Replace the standard search form** - This option allows to replace all the standard search forms on your website.
* **Search Button Icon** - This option sets search button text.
* **Search Button Text** - This option sets search button text.
* **Caption / Placeholder text** - This option sets placeholder text in input field.

### Search Result Settings ###
* **Search in** - You can select particular search sources. If nothing is selected in the option, search will be made over the entire site.
* **Exclude categories from search results** - This option allows to set categories in which search will not be made.
* **Exclude tags from search results** - This option allows to set tags in which search will not be made.
* **Exclude post types from search results** - This option allows to set post types in which search will not be made.
* **Number of results displayed in one search query** -This option will allow you to limit the number of displayed search results. If the overall number of results exceeds previous set limit, the "load more" button will come up..
* **Sort search results by** - sort search results by a certain criteria
* **Filter results by** - filter search results by ascending or descending order

### Visual Settings ###
* **Show post titles** - show/hide post titles
* **Post word count** - specify the post word count
* **Show post authors** - show/hide post authors
* **Prefix before author's name** - specify the prefix that will be displayed before author’s name
* **Show post thumbnails** - show/hide posts thumbnails
* **Enable scrolling for dropdown lists** - enable disable scrolling for dropdown search results lists
* **Dropdown list height** - specify the dropdown list heigh
* **"View more" button text** - add text for “View more button”

### Notifications###
* **Negative search results** - text that will be displayed if nothing is found
* **Technical error** - text that will be displayed during technical error

## For developers ##

### Templates ###

The plugin contains templates that can be rewritten in the theme. For that you need to create a templates folder in the root catalog of the theme. In the templates folder, create a cherry-search.

Templates list:
* **Ssearch-form** - search form template
* **Ssearch-form-input** - search form input template
* **Ssearch-form-submit** - search form submit button template
* **Ssearch-form-results-item** - template of the element that is displayed in search results
* **Ssearch-form-results-list** - dropdown search results list template

If you want to change the search results display type, you need to copy the **search-form-results-item.tmpl** file into the theme folder.

Example: *theme_name / templates / cherry-search / search-form-results-item.tmpl*

### Macros ###

**%%INPUT%%** - Returns *search-form-input* template content

**%%SUBMIT%%** - Returns *search-form-submit* template content

**%%RESULTS_LIST%%** - Returns *search-form-results-list* template content.

**%%SPINNER%%** - Contains loader HTML structure
The macro works with filters:
* **cherry_search_spinner_holder** -contains loader HTML wrapper markup
* **cherry_search_spinner** - contains loader HTML markup

**%%ICON%%** - Returns *Main Settings option value > Search Button Icon*

**%%SUBMIT_TEXT%%** - Returns *Main Settings option value > Search Button Text*

**%%THUMBNAIL%%** - Contains post thumbnail. If post doesn’t have a thumbnail, empty string will be returned

**$$ACTION$$** - Macro contains links to action forms

**$$LINK$$** - Contains post link

**$$TITLE$$** - Contains post title

**$$CONTENT$$** - Contains part of the post contain

**$$AUTHOR$$** - Contains post author

**$$READER_TEXT$$** - Contains  "Search for:" text
Macro works with **cherry_search_reader_text** filter

**$$PLACEHOLDER$$** - Returns *Main Settings -> Placeholder text option value*

### Filters ###

**cherry_search_button_icon** - Allows to change the icons set, which you want to use buttons for search.
* Type - *array*
* By default: *''*

Filter contains an array with the following values:
* Icon set title
* Path to css file with icons
* Css icon prefix css (if required)


**cherry_search_limit_content_word** - Allows to change search elements word length  default value.
* Type - *number*
* By default: *50*


**cherry_search_reader_text** - Allows to change Search for: text.
* Type - *string*


**cherry_search_icon_prefix** - Filter defines whether to add a prefix class to the icon font. For example in font-awesome - fa fa-search font
* Type - *bool*
* By default: *true*


**cherry_search_icon** - Filter allows to change the HTML markup of the search button icon.
* Type - *string*
* By default: `<span class="cherry-search__icon %s"></span>`


**cherry_search_submite_text** - Filter allows to change the HTML markup of the search button text.
* Type - *string*
* By default: `<span class="cherry-search__submite_text">%s</span>`


**cherry_search_spinner_holder** - Filter allows to change the loader wrapper  HTML markup.
* Type - *string*
* By default: `<div class="cherry-search__spinner_holder">%s</div>`

**cherry_search_spinner** - Filter allows to change the loader HTML markdown.
* Type - *string*
* By default: `<div class="cherry-search__spinner"><div class="rect1"></div><div class="rect2"></div><div class="rect3"></div><div class="rect4"></div><div class="rect5"></div></div>`


**cherry_search_thumbnail_html** - Filter allows to change post thumbnail HTML wrapper markup.
* Type - *string*
* By default: `<span class="cherry-search__item-thumbnail">%s</span>`


**cherry_search_author_html** - Filter allows to change Filter allows to change post author name  HTML wrapper markup.
* Type - *string*
* By default: `<span>%1$s </span> <em>%2$s</em>`


**cherry_search_more_button_html** - Filter allows to change the more-button HTML markdown. Button text is set in the option Visual settings -> "Show more" button text.
* Type - *string*
* By default: `<li class="cherry-search__more-button">%s</li>`

