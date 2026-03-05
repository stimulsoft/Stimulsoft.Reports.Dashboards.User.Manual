## Formatting Tags

The report generator supports nine tags for changing a font style: &lt;b&gt;, &lt;i&gt;, &lt;u&gt;, &lt;s&gt;, &lt;sup&gt;, &lt;sub&gt;, &lt;strong&gt;, &lt;p&gt;, &lt;br&gt;. These HTML tags are called formatting tags. These formatting tags can make text bold, italic, sub/superscripted, and more.


The example below shows how the &lt;b&gt; tag works in a text expression.  If you enter the following expression:


This &lt;b&gt;text&lt;/b&gt; is bold.


then after calculation the result appearing in the report will be:

This text is bold.

> **Information**
>
> Note that the word 'text' is enclosed within the opening and closing &lt;b&gt; and &lt;/b&gt; tags.

Formatting tags can be used in combination with other formatting tags to changing the text style. For example, if you  enter the following expression:

This &lt;i&gt;&lt;b&gt;text&lt;/b&gt;&lt;/i&gt; is bold italic.

then after calculation the result appearing in the report will be:

This text is bold italic.

Style intersection is not allowed, formatting tags may not be nested partly inside and partly outside another formatting tag. For example:

&lt;b&gt;This &lt;i&gt;text&lt;/b&gt; is bold&lt;/i&gt; italic.  // This will fail

The available formatting tags are discussed in detail in the following topics.
