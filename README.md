# Hoggle

An inline-block based grid system. Still very much in its early stages.

[Read the docs](https://github.com/TheRealAlan/hoggle-docs).

This is an inline-block based grid system built on Sass. There are no other requirements. Whitespace may be an issue with the inline-block columns. If you’re using HAML, you can clear out the whitespace with a `>` at the end of tags. Since this is an inline-block grid, it’s easy to vertically align content. Yay!

## Get the Gem

For now there’s just a gem. Add this to your gemfile.

```
gem "hoggle", :github => "TheRealAlan/hoggle"
```

Then run `bundle install` and you should get the goods.

## Include the SCSS

If you’re using the Rails asset pipeline, including the Hoggle stylesheets is easy:

``` scss
@import "hoggle";
```

If not, just download the zip and dig into the vendor folder.

## Another Grid? Why?

I’ve used a lot of grid systems - Bootstrap, Foundation, Bourbon’s Neat - and all of them are great, but also too much. I wanted a reusable grid that was simple, lightweight, unobtrusive, and just a grid. I wanted responsive flexibility that I didn’t get with other grid systems, as well as the ability to easily vertically center elements. Most other grid systems are float based. Hoggle is inline-block based.