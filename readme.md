WP-tevko-responsive-images
---

Bringing automatic default responsive images to wordpress.

This plugin works by including 4 additional image sizes for each image upload. Whenever wordpress outputs the image through the media uploader, those 4 sizes will be included in the image tag via the [srcsizes](http://css-tricks.com/responsive-images-youre-just-changing-resolutions-use-srcset/) attribute.

##Hardcoding in template files

 You can output a responsive image anywhere you'd like by using the following syntax:

``<?php echo tevkori_get_src_sizes( TheIdOfYourImage ); ?>``

##Version

2.0.0

##Changelog

 - Uses [Picturefill 2.2.2 (Beta)](http://scottjehl.github.io/picturefill/)
 - Scripts are async
 - Thumbnail support is added if not previously supported
 - Image sizes adjusted
 - If alt tag is left blank, image title is used
 - Most importantly, the srcset syntax is being used
 - The structure of the plugin is significantly different. The plugin now works by extending the default wordpress image tag functionality to include the srcset sizes syntax. In doing this, the width and height attributes are removed from the origional wordpress image tag. The title is also removed
 - another thing to note, tinyMCE doesn't support the srcsizes attribute. To get around that bug, we had to disable a piece of functionality in tinyMCE. Specifically, tinyMCE will no longer remove what it thinks to be invalid html markup as long as this plugin is installed.