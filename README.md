# jekyll-posts-json

A Jekyll plug-in to generate a posts.json file of available posts for consumption by whatever.

By default, this plug-in will will generate a file called `posts.json` in the
site's destination path.

The JSON structure is as follows:

```json
[
  {
    date:    "2013-09-19 00:00:00 -0700",
    url:     "/blog/2013/09/19 00:00:00 -0700",
    title:   "First post!",
    excerpt: "Wherein I talk about teh first post.",
    tags:    [ "foo", "bar", "bat", "baz" ]
  }
]
```

You can configure the filename/output path in the Jekyll `_config.yml`:

    posts_json_path: awesome_posts.json

This file can be loaded in via any standard AJAX means.

Alternative, a Liquid tag is available for embedding the contents of the generated file into your page:

```javascript
<script type="text/javascript">
  var posts = new Backbone.Collection();
  posts.reset({% posts_json %});
</script>
```

