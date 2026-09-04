## Face Attribute

The face attribute defines the name of the font of the text within the font element. To use this attribute you must specify the font name. If the font is not found, then the font of the text component or the previous font specified in the tag is used.


The sample below shows how to use the **face** attribute:

&lt;font face="Arial" ...&gt;


### Alternative Attributes

Instead of the "**face**" attribute the attributes "**name**" and "**family**" can be used. All these attributes are identical. For example:

&lt;font face="Courier" ...&gt;
&lt;font name="Courier" ...&gt;
&lt;font family="Courier" ...&gt;


All the text expressions above specify the same font.

### Alternative Tags

The &lt;font-face&gt; tag is the same as the &lt;font&gt; tag with the **face** attribute. For example:

&lt;font-face="Arial"&gt;
