---
$title: Custom fonts
$order: 5
---
[TOC]

AMP pages can’t include external stylesheets, with the exception of custom fonts.
You can embed custom fonts into your page in two ways:

1. Through a `<link>` tag (white-listed font providers only)
2. Via `@font-face` (no restrictions, all fonts allowed)

### 1. Using `<link>`

Use a `<link>` tag (usually in the head of your page), like so:

[sourcecode:html]
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Tangerine">
[/sourcecode]

The following origins are whitelisted and allowed for font serving via link tags:

* Typography.com: **https://cloud.typography.com**
* Fonts.com: **https://fast.fonts.net**
* Google Fonts: **https://fonts.googleapis.com**
* Font Awesome: **https://maxcdn.bootstrapcdn.com**

### 2. Using `@font-face`

Alternatively, you can use [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
within your AMP stylesheet:

[sourcecode:html]
<style amp-custom>
  @font-face {
    font-family: "Bitstream Vera Serif Bold";
    src: url("https://somedomain.org/VeraSeBd.ttf");
  }

  body {
    font-family: "Bitstream Vera Serif Bold", serif;
  }
</style>
[/sourcecode]

{% call callout('Note', type='note') %}
Fonts included via `@font-face` must be fetched
via the HTTP or HTTPS scheme.
{% endcall %}


