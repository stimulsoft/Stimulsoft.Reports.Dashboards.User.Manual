## HTML Tags

Stimulsoft Reports has the ability to format text using standard HTML formatting tags. Sometimes it is necessary to make part of a text expression look Bold, Italic, or Underlined. For example you may wish to achieve something like this:


The fifth word is **bold**


HTML tags can help achieve this. The output shown above could be generated using the following expression:

The fifth word is &lt;b&gt;bold&lt;/b&gt;


It is possible to get a similar result without using HTML by using the Rich text component, but there are some difficulties and the Rich text component works very slowly, so using HTML tags is often the best way to achieve the desired result.


HTML tags can be included only in the text part of expression, in other words their use is possible only in the **Text** property of the **Text** component.


> **Information**
>
> HTML tags can be included only in the text part of an expression.

For example, the following expressions are correct:

This is a simple &lt;i&gt;expression {1+2}&lt;/i&gt;
This is a simple &lt;i&gt;expression&lt;/i&gt; {1+2}
This is a simple expression &lt;i&gt;{1+2}&lt;/i&gt;

These expressions however are incorrect:


The is a simple &lt;i&gt;expression {1&lt;/i&gt;+2}


The is a simple &lt;i&gt;expression {1+2&lt;/i&gt;}


The is a simple expression {&lt;i&gt;1+2}&lt;/i&gt;

In the examples above the HTML tags are placed within the body of an expression that will be calculated by C# or VB.Net, shown by the curly braces, so they are impossible to process.


> **Information**
>
> Do NOT place HTML tags inside the curly braces of any expression or the expression will fail.

**Available Tags**

There are few limitations  - most valid HTML style tags can be inserted, with the exception of ordered list and unordered list tags.  If you need to generate such lists you can use the Rich Text control or create the layout manually.


> **Information**
>
> You cannot use Ordered and Unordered List tags within expressions.

HTML tags can be nested to an unlimited depth. For example:


This is a &lt;b&gt;simple &lt;i&gt;expression {1+2}&lt;/i&gt;&lt;/b&gt;


If a tag is not closed, then the tag works to the end of the text line.


If HTML tags are used in a text expression then any line breaks in that expression are ignored. If you need to enforce a line break in your text, use the &lt;br&gt; tag.


> **Information**
>
> Use the &lt;br&gt; tag to break a line when using HTML tags.

**Activating HTML Tags**

It is important to know that by default HTML tags in expressions are simply ignored. To allow the use of HTML tags it is necessary to set the **AllowHtmlTags** property of the Text component to true.


> **Information**
>
> Set the AllowHtmlTags property to true to allow the use of HTML tags in the text expression.

The list of HTML tags, which are supported in the Stimulsoft software


| **Name** | **Description** |
| --- | --- |
| **Font tags****:** |  |
| &lt;font color="#rrggbb" face="FontName" size="1..n"&gt; &lt;/font&gt; | Defines the color, font and size of a text. [Learn More.](Font_Tag/index.md) |
| &lt;font-face="FontName"&gt; &lt;/font-face&gt; | Defines the font of a text. [Learn More.](Font_Tag/Face_Parameter.md) |
| &lt;font-name="FontName"&gt; &lt;/font-name&gt; | Defines the font of a text. [Learn More.](Font_Tag/Face_Parameter.md) |
| &lt;font-family="FontName"&gt; &lt;/font-family&gt; | Defines the font of a text. [Learn More.](Font_Tag/Face_Parameter.md) |
| &lt;font-size="1..n"&gt; &lt;/font-size&gt; | Defines the size of a text. [Learn More.](Font_Tag/Size_Parameter.md) |
| &lt;font-color="#rrggbb"&gt; &lt;/font-color&gt; | Defines the color of a text. [Learn More.](Font_Tag/Color_Parameter.md) |
| **Font style tags****:** |  |
| &lt;b&gt; &lt;/b&gt; | Makes a text bold. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_b.md) |
| &lt;i&gt; &lt;/i&gt; | Makes a text italicized. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_i.md) |
| &lt;u&gt; &lt;/u&gt; | Underlines a text. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_u.md) |
| &lt;s&gt; &lt;/s&gt; | Displays an underlined text. It is a shorthand note of the &lt;strike&gt; tag. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_s.md) |
| &lt;sub&gt; &lt;/sub&gt; | Displays a text as a subscript. The text will be located below the base text line and its size will be reduced. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_sub.md) |
| &lt;sup&gt; &lt;/sup&gt; | Displays a text as a superscript. The text will be located above the base text line and its size will be reduced. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_sup.md) |
| &lt;strong&gt; &lt;/strong&gt; | Accentuates a text, i.e determines the importance of the text and makes it in bold in the browser.  [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_strong.md) |
| &lt;em&gt; &lt;/em&gt; | Accentuates a text, in other words determines the importance of the text, and highlights it in a browser in the italic font style. [Learn More.](HTML_Tags_to_Change_Font_Style/HTML_Tag_em.md) |
| &lt;strike&gt; &lt;/strike&gt; | Displays an underlined text, it's analogous to the &lt;s&gt; tag. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_s.md) |
| **Spacing tags****:** |  |
| &lt;letter-spacing="0"&gt; &lt;/letter-spacing&gt; | Defines a spacing between symbols within an element, in units of a font height. [Learn More.](Letter_Spacing.md) |
| &lt;word-spacing="0"&gt; &lt;/word-spacing&gt; | Sets a spacing between words, in units of a font height. [Learn More.](Html_tag_word-spacing.md) |
| &lt;line-height="1"&gt; &lt;/line-height&gt; | Sets a line spacing of a text. [Learn More.](Html_tag_line-height.md) |
| &lt;text-align="left"&gt; &lt;/text-align&gt; | Changes the horizontal alignment of a text - **left**, **right**, **center** and **justify**.  [Learn More.](Html_tag_text_align.md) |
| **Paragraph tags****:** |  |
| &lt;br&gt; , &lt;br /&gt; | Inserts a line break. Unlike the &lt;p&gt; tag, it doesn`t add a blank indent before a line. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_br.md) |
| &lt;p&gt; &lt;/p&gt; | Defines a text paragraph. The tag is a block element, a blank line is always added before it, and paragraphs of a text following each other are separated by vertical space. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_p.md) |
| **Tags of lists****:** |  |
| &lt;ul&gt; &lt;/ul&gt; | Sets a bulleted list. Each element of the list should start with the **&lt;li&gt;** tag. [Learn More.](HTML_Tags_to_Change_Font_Style/HTML_ul_Tag.md) |
| &lt;ol&gt; &lt;/ol&gt; | Sets a numbered list. Each element of the list should start with the **&lt;li&gt;** tag. [Learn More.](HTML_Tags_to_Change_Font_Style/Html_tag_ol.md) |
| &lt;li&gt; &lt;/li&gt; | Defines a separate item of a bulleted or a numbered list. |
| **URL tags****:** |  |
| &lt;a href="..."&gt;…&lt;/a&gt; | Sets a URL address to insert, when clicking on a text which is enclosed between opening and closing tags |
| **Color and background tags****:** |  |
| &lt;color="#rrggbb"&gt; &lt;/color&gt; | Defines the color of a text. |
| &lt;background-color="#rrggbb"&gt; &lt;/background-color&gt; | Defines the color of a text background. |
| **Style attributes****:** |  |
| color | Defines the color of a text in an element. |
| background-color | Defines the color of an element background. |
| text-decoration: underline, line-through, none | Sets the kind of text decoration: underline - underline text; line-through - cross out text; none - cancels all effects, including effects for links. |
| font-weight: bold, normal | Defines a font weight – bold or normal. |
| font-style: normal, italic | Defines font style – normal or italic. |
| font-size | Defines font size. |
| font-face, font-family, font-name | Defines a font. |
| vertical-align: baseline, sub, super | Defines the vertical alignment: baseline is analogous to the &lt;/sub&gt; or the &lt;/super&gt; tags. sub. An element is displayed as a subscript. And font size won't be changed. It is analogous to the &lt;sup&gt; tag. super. An element is displayed as superscript. This will not change the font size. Similar to the &lt;sup&gt; tag. |
| letter-spacing: normal, x.x | Defines a spacing between symbols within an element: normal is a value by default; x.x is a custom value in a font height units. |
| word-spacing: normal, x.x | Defines a spacing between symbols within an element: normal is a value by default; x.x is a custom value in a font height units. |
| line-height: normal, x.x | Sets a line spacing: normal is a value by default; x.x is a custom value in a font height units. |
| text-align: left, center, right, justify | Defines the horizontal alignment: left - align an element to the left; center - align an element to the center; right - align an element to the right; justify - align an element to the width |
| margin-top, margin-bottom | Sets the amount of an indent from the top and the bottom edge of an element. It is relevant only for the &lt;p&gt; tag. |
| margin | Sets the amount of an indent from the top and the bottom edge of an element. It is relevant only for the &lt;p&gt; tag. |
| **Color formats:** |  |
| #rrggbb | Defines a color in the RGB format as a HEX code. |
| #rgb | Defines a color in the RGB format as a HEX code in a short form. |
| rgb(r,g,b) | Defines a color in the RGB format with the help of decimal values. |
| **Special characters** **(**[more than 200](Special_Characters.md)**)****. Below is a list of the most frequently used:** |  |
| &amp; | Displays the ampersand - &. [Learn More.](Special_Characters.md) |
| &lt; | Displays the sign less than - &lt;. [Learn More.](Special_Characters.md) |
| &gt; | Displays the sign greater than - &gt;. [Learn More.](Special_Characters.md) |
| &quot; | It gives the ability to display the double quote - ". [Learn More.](Special_Characters.md) |
| &apos; | It gives the ability to display the quote - '. [Learn More.](Special_Characters.md) |
| &nbsp; | Displays the no-break space. [Learn More.](Special_Characters.md) |
| &#xxxx; | The template of symbol entry in the ASCII encryption. [Learn More.](Special_Characters.md) |
| **Font format:** |  |
| Font name formats: name name1,name2 | Specifies several fonts. |
