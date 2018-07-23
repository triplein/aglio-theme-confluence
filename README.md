# Confluence theme for Aglio based on the Olio default theme



This is Olio-Confluence, a fork of the original Olio theme engine for [Aglio](https://github.com/danielgtaylor/aglio), developed specifically to be used in Confluence HTML embeds.

## Difference to Olio
+ Necessary html elements for page styling moved from ```<head>``` to ```<body>```, since Confluence strips the ```<head>``` element
+ Changed to single column display
+ Changed vertical navigation to horizontal navigation

## Example use

```bash
$ sudo npm install -g aglio
$ aglio -i blueprint.apib \
        --theme-template node_modules/aglio-theme-confluence/templates/index.jade \
        --theme-variables node_modules/aglio-theme-confluence/styles/variables-default.less \
        --theme-style node_modules/aglio-theme-confluence/styles/layout-default.less \
        --theme-full-width -o MyAPI.html
```
Theme engines for Aglio are described in more detail in the [Aglio documentation](https://github.com/danielgtaylor/aglio#customizing-output).


## Known Issues
Mind the following issues and limitations when using Aglio-Theme-Confluence in production:


Issue                                                       | Workaround
----------------------------------------------------------- | -----------
[#1 Rendered HTML in Confluence displaces footer by 300px](https://github.com/triplein/aglio-theme-confluence/issues/1)|
[#2 Three-column templates produces broken HTML](https://github.com/triplein/aglio-theme-confluence/issues/2) | Use only the (default) two-column layout
[#3 Using --theme-full-width does not make any difference](https://github.com/triplein/aglio-theme-confluence/issues/3) | Ignore the parameter, the result is always full-width to help with the embed layout


## Design Philosophy
Olio is designed from the ground up to be both **fast** and **extensible** while maintaining backward compatibility with most of the original Aglio theme. It uses the following technologies:

* [Less](http://lesscss.org/) to produce CSS
* [Markdown-it](https://github.com/markdown-it/markdown-it#readme) to render Markdown
* [Jade](http://jade-lang.com/) to produce HTML
* [Highlight.js](https://highlightjs.org/) to highlight code snippets

For backward compatibility, Jade templates can continue to use inline Stylus and CoffeeScript.

## Theme Options

Olio comes with a handful of configurable theme options. These are set via the `--theme-XXX` parameter, where `XXX` is one of the following:

Name           | Description
-------------- | ------------------
`condense-nav` | Whether to condense nagivation for resources with only a single action (default is `true`).
`full-width`   | Whether to use the full page width or a responsive layout (default is responsive).
`style`        | LESS or CSS to control the layout and style of the document using the variables from below. Can be a path to your own file or one of the following presets: `default`. May be an array of paths and/or presets.
`template`     | Jade template to render HTML. Can be a path to your own file or one of the following presets: `default`.
`variables`    | LESS variables that control theme colors, fonts, and spacing. Can be a path to your own file or one of the following presets: `default`, `flatly`, `slate`, `cyborg`. May be an array of paths and/or presets.

**Note**: When using this theme programmatically, these options are cased like you would expect in Javascript: `--theme-full-width` becomes `options.themeFullWidth`.

License
=======
Copyright &copy; 2018 TripleIn software solutions GmbH

[](http://dgt.mit-license.org/)
