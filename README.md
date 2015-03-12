# jekyll-wlinks
WinerLinks for Jekyll posts.

This Jekyll plugin creates Links and anchors to each paragraph 


## Installation
Just place the `wlinks.rb` into the folder `_plugins` in the root directory.

## Configuration
Per default the Plugin will add a hashtag-symbol at the end of paragraphs and
link them to an anchor inserted at the beginning of the paragraph.

Some settings can be changed by adding parameters to `_config.yaml`:

``` yaml
wlinks:
  symbol: #
  check: partial
  title: Anchor
```

* `symbol`  
  Defines the string to show at the end of a paragraph.  
  Default: #

* `check`
  How much of the paragraph shall be used to create the anchor link. Unless set
  to _complete_ only the first 20 character will be used to create the anchor.
  Changes to the paragraph beyond the 20th character will not result in a new
  anchor and links will stay unchanged.  
  Default: partial
  Values: partial|complete

* `title`  
  Value for the title tag used in the link pointing to the anchor. This can be
  used to change the CSS style of the links.  
  Default: Anchor

In order to switch of the wlinks for only a single post, extend the YAML
header with the parameter `wlinks` and set it to `false`:

``` YAML
---
date: '1970-01-01 00:00:01'
title: Example
wlinks: false
---
``` 

## CSS
The title in the anchor links can be used to style the link.  

``` css
/*
 * Change default anchor links
 */
a[title='Anchor'] {
  font-size: 0.5em;
  font-weight: normal;
  color: #bbbbbb;
}

/*
 * Anchor links in Headlines shall be on the right
 */
h1 a[title='Anchor'] {
  float: right;
}
```

