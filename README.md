# Hoggle

An inline-block based grid system. Still very much in its early stages.

View the [demo](http://therealalan.github.io/hoggle-test/). There's a [hoggle-test](https://github.com/TheRealAlan/hoggle-test) built on Middleman to play with at.

## Requirements

- Sass
- something like Autoprefixer

This is a prefix free, inline-block based grid system. You'll need something like [Autoprefixer](https://github.com/postcss/autoprefixer) to handle your vendor prefixes. Whitespace may be an issue with the inline-block columns. If you're writing your HTML using HAML, you can clear out the whitespace with a `>` at the end of the tags. Since it's an inline-block grid, there are several advantages, one being the ability to easily vertically align content. 

## Get the Gem

For now, there's just a gem. Add this to your gemfile.

```
gem "hoggle", :github => "TheRealAlan/hoggle"
```

## Include the SCSS

Include the Hoggle stylesheets:

``` scss
@import "hoggle";
```