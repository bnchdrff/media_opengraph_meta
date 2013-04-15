Media: OpenGraph Meta
=====================

What does it do?
----------------

This module adds image thumbnails from Youtube and Vimeo videos in an entity's media fields to the opengraph_meta modules's list of potential og:image items.

Installation
------------

This module requires a patch to the opengraph_meta module:
    diff --git a/opengraph_meta.common.inc b/opengraph_meta.common.inc
    index 491e401..8810206 100644
    --- a/opengraph_meta.common.inc
    +++ b/opengraph_meta.common.inc
    @@ -319,6 +319,9 @@ class OpenGraphMeta {
           libxml_use_internal_errors(FALSE); // turn libxml errors back on
         }
     
    +    // allow modules to alter $ret
    +    drupal_alter('opengraph_meta_imageharvest', $ret, $node);
    +
         return $ret;
       }
     

Currently this module doesn't use the database, so you can simply enable or disable it without worries.

Credits
-------

Benjamin Chodoroff, Work Department LLC
Created for excellentschoolsdetroit.org

License
-------

Copyright (c) 2013 Benjamin Chodoroff. Licensed under the GNU General Public License, GPL v3.
