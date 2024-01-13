---
title: "Text formatting"
description: "Formatting text in Resonite."
---

# Text formatting

## Hey! The [official Resonite wiki is out](https://wiki.resonite.com). It means this is now unmaintained.


[Go back to index.](/wiki/resonite/).

There is a variety of tags available to format text in Resonite.  
Those tags looks like HTML while not being HTML.
The biggest difference from HTML is that tags don't have to fully encapsulate each other, for example: `<b>test <i>test </b>test</i>` is valid in resonite but is invalid in HTML.
It is considered good practice to close tags after using them, for instance `<tag>content</tag>` so the effects of the tag do not overflow.

- `<align=side>` - Aligns the text on the specified side; sides available:
  - Left (`left`)
  - Right (`right`)
  - Center (`center`)
  - Justified (`justify`)
- `<allcaps>` or `<smallcaps>` - Renders lowercase characters as small uppercase characters.
- `<alpha=number>` - Sets the Alpha of the text; number must be between 0 and FF (255). Can also be used with color names such as `<alpha=red>` because of an oversight.
- `<b>` - Renders the text bold.
- `<br>` - Inserts a line break.
- `</closeall>` - Closes all the tags previously used and not closed. (See example below)
- `<closeallblock>` - Creates a block for the `closeall` tag to operate.
- `<color=color>` - Sets the text a specific colour (hex, text like "black", "blue", "red"), platform-specific colours ("hero.red", "hero.blue"; see the component `Utility`->`PlatformColorPalette`).
- `<font="font name">` - Renders the text with the specified font, the font name MUST be in quotes, otherwise the game assumes it's a number; requires the use of the component `Rendering`->`Text`->`FontCollection`; note: font can also be a number to reference by index.
- `<glyph="glyph">` or `<sprite="glyph">` - Inserts a glyph within the text, requires the use of the components `Rendering`->`Text`->`FontChain` and `Assets`->`Procedural Fonts`->`DynamicSpriteFont`.
- `<gradient=color1,color2>` - Creates a gradient between the provided colours (inputs are the same as the `color` tag); note: [the gradient tag is not implemented at the moment](https://github.com/Yellow-Dog-Man/Resonite-Issues/issues/426).
- `<i>` - Renders the text italic.
- `<line-height=number>` - Sets the line height.
- `<lowercase>` - Forces all the text to be lowercase.
- `<mark=color>` - Highlights text with the selected colour.
- `<nobr>` - Ignores automatic line breaks.
- `<noparse>` - No tags will be parsed within this tag.
- `<s>` - Renders text strike-through.
- `<size=number>` - Sets the size of the text.
- `<sub>` - Renders the text subscript.
- `<sup>` - Renders the text superscript.
- `<u>` - Renders the text underlined.
- `<uppercase>` - Forces all the text to be uppercase.

## CloseAll and CloseAllBlock Example

The `</closeall>` tag does not have an opening tag, instead it acts as a closing tag for every tag which is currently open.
If there are no currently open tags within the text to be closed, the tag will simply be shown in plaintext.

The `<closeallblock>` will make all tags before it not get closed by the `</closeall>` tag.
For example:
`<color=red>foo <closeallblock><b>bar </closeall>baz </closeallblock></closeall> qux`
will result in foo being red, bar being red and bold, baz being red and qux being the default color.
