## HTML &lt;background-color&gt; Tag

The tag `<background-color>` is used to change the background color of text. The color value is specified in the same way as the `color` parameter of the `<font>` tag. If the report generator does not find a closing tag, the text background will remain changed until the end of the output text or until it is changed by another tag. An example of a text expression using the `<background-color>` tag:


`Test <background-color="red">Test</background-color> Test`

You can also specify an RGB or HEX value:


`Test <background-color="rgb(255, 0, 0)">Test</background-color> Test`

`Test <background-color="#FF0000">Test</background-color> Test`

In this case, the output text will be as follows:


Test Test Test
