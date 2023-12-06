---
title: "Text formatting"
---

# Text formatting

[Go back to index.](/wiki/resonite).

There is a variety of tags available to format text in Resonite.  
Those tags looks like HTML while not being HTML.  
It is considered good practice to close tags after using them, for instance `<tag>content</tag>` so the effects of the tag do not overflow.

- `<align=side>` - Aligns the text on the specified side; sides available:
  - Left
  - Right
  - Center
  - Justified
- `<allcaps>` | `<smallcaps>` - Renders lowercase characters as small uppercase characters.
- `<alpha=number>` - Sets the Alpha of the text; number must be between 0 and FF (255).
- `<b>` - Renders the text bold.
- `<br>` - Inserts a line break.
- `<closeall>` - Closes all the tags previously used and not closed.
- `<closeallblock>` - Creates a block for the `closeall` tag to operate.
- `<color=color>` - Sets the text a specific colour (hex, text like "black", "blue", "red"), platform-specific colours ("hero.red", "hero.blue"; see the component `Utility`->`PlatformColorPalette`).
- `<font="font name">` - Renders the text with the specified font; requires the use of the component `Rendering`->`Text`->`FontCollection`; note: font can also be a number to reference by index.
- `<glyph="glyph">` | `<sprite="glyph">` - Inserts a glyph within the text, requires the use of the components `Rendering`->`Text`->`FontChain` and `Assets`->`Procedural Fonts`->`DynamicSpriteFont`.
- `<gradient=color1,color2>` - Creates a gradient between the same colours (inputs are the same as the `color` tag); note: [the gradient tag is broken at the moment](https://github.com/Yellow-Dog-Man/Resonite-Issues/issues/426).
- `<i>` - Renders the text italic.
- `<line-height=number>` - Sets the line height.
- `<lowercase>` - Forces all the text to be lowercase.
- `<mark=color>` - Highlights text with the selected colour.
- `<nobr>` - Ignores automatic line breaks.
- `<noparse>` - No tags will be parsed within this tag.
- `<s>` - Renders text strikethrough.
- `<size=number>` - Sets the size of the text.
- `<sub>` - Renders the text subscript.
- `<sup>` - Renders the text superscript.
- `<u>` - Renders the text underlined.
- `<uppercase>` - Forces all the text to be uppercase.
