=== OpenPublishing ===
Contributors: OpenPublishing GmbH
Tags: openpublishing, ebook, books
Requires at least: 3.1
Tested up to: 5.3.3
Stable tag: 1.6

Enrich content with data from the OpenPublishing service
== Description ==

To visualize Open Publishing data on your page please use smart substitution tags in place you want to insert a data, like so `[large_document_view:document.123]` or `[sidebar:newest.1:de]`

This substitution tag will be replaced by the data this plugin retrieve from OP server.

Smart substitution notation contain: ``[ "tag_name":"object"."object_id":"language" ]``
`language` is an optional parameter, use it to get language specific results. Possible values: `en`, `de`, `fr`, `es`.

You can use: `document`, `bestseller`, `newest`, `most_read` objects.

Also you can access document count from brand statistics. 
To print document count use 'openpublishing_document_count' option.

= Special Features =

**Openpublishing substitution**
To make substitution work please create templates for each tag_name you would like to use. You can do this in two different ways.

* Using Elementor plugin:

  1. Go to Elementor <a href="/wp-admin/edit.php?post_type=elementor_library">page</a>
  2. Create new template, remember a template id (you can see it in the edit url)
  3. You can easily style your template by means of Elementor


* Using WordPress posts:
  1. Go to Pages > Add New
  2. Create new post and treat it like a template, remember a template id (you can see it in the edit url)
  3. (Optional) you can assign special category (like op-templates) to each post to distinguish between others
  4. Use special keywords in your template:`{title} {subtitle} {price} {grin_url} {source_url} {document_id} {cdn_host} {realm_id}`


Add newly created templates/posts on this page with corresponding ids.

### Usage: ###

To use substitution please insert into your page this tag with desired 'tag_name' and 'object_id' like:

    <h2>Our bestsellers:</h2>
      <div>[large_document_view:bestseller.1] [large_document_view:bestseller.2] [large_document_view:bestseller.3]</div>

This tags should be replaced right away.

**Openpublishing document count**
There is a scheduled job which is retrieving the brand statistics from OP server and saves the value to Document count on a daily basis.


### Debug: ###

To debug plugin work please add next code into your page after all text:

    <script type="text/javascript">
      var debug = document.getElementsByClassName("OP_debug");
      for(i=0; i<debug.length; i++) { debug[i].style.display = 'inline'; }
    </script>

This will allow you to see some more information about substitution.


== Installation ==

1. Install using the WordPress built-in Plugin installer, or clone repository and drop the contents in the `wp-content/plugins/openpublishing` directory of your WordPress installation.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Go to Open Publishing settings on left menu bar
4. Proceed with further instructions: set realm id, brand name and API host.

