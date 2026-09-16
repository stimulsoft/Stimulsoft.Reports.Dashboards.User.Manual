# Markdown Examples

This chapter describes text formatting examples for the Markdown component.

### Supported standard and extensions

The base syntax is the full official specification [CommonMark 0.31.2](https://spec.commonmark.org/0.31.2/). A brief overview of the supported formatting follows; the extensions on top of CommonMark are enabled by default. The name of each item is a link to the official description of its syntax.

- [Code formatting](https://spec.commonmark.org/0.31.2/#fenced-code-blocks) - inline code ``code``, a fenced block of ````` (a language tag can be given) and an indented block of 4 spaces.
- [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) - tables, task list items, strikethrough, autolinks.
- [Footnotes](https://michelf.ca/projects/php-markdown/extra/#footnotes) - references like `[^id]` with a definition later in the text.
- [Definition lists](https://michelf.ca/projects/php-markdown/extra/#def-list) - a term and a definition indented under it.
- [Highlight, superscript and subscript](https://pandoc.org/MANUAL.html#superscripts-and-subscripts) - `==text==`, `x^2^`, `H~2~O`.
- [SmartyPants](https://daringfireball.net/projects/smartypants/) - typographic quotes, dashes and ellipsis.
- [Obsidian-style callouts](https://help.obsidian.md/callouts) - `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`, `> [!WARNING]`, `> [!CAUTION]`.


Each item is covered in detail with examples below.

### What you get from CommonMark

- **Headings** - `# H1` / `## H2` / `### H3` / `#### H4` / `##### H5` / `###### H6`.
- **Setext headings** - a line of text with `===` (level 1) or `---` (level 2) underneath it.
- **Paragraphs** - blank line separates paragraphs. Hard break: two trailing spaces or `\` at line end.
- **Emphasis** - `*italic*` → *italic*, `**bold**` → **bold**, `***both***` → ***both***.
- **Code formatting** - inline ``code`` → `code`; a fenced block of ````` or `~~~` (the language tag is preserved as text); an indented block - start every line with 4 spaces or a tab.
- **Bulleted list** - `- item`, `* item` or `+ item`; indent for nesting.
- **Ordered list** - `1. item`, `2. item` …; numbers don't have to be sequential.
- **Links** -`[text](https://example.com)` → text, with optional `"title"`.
- **Reference links** - `[text][id]` in the text and `[id]: https://example.com` on a line of its own.
- **Images** - `![alt](https://example.com/pic.png)` on a line of its own.
- **Blockquotes** - `> quoted line`; nest with `>> deeper`.
- **Thematic break** - `---`, `***` or `___` on a line of its own.
- **HTML entities** - `&copy;` → ©, `&mdash;` → -, `&amp;` → &.
- **Raw HTML** - HTML blocks and inline tags are output as-is in a monospaced font; HTML markup is not interpreted.
- **Backslash escapes** - `\*`, `\#`, `\_` … for literal punctuation.

### CommonMark - fenced code block

Fence a block with three backticks (or three tildes); an optional language tag is remembered but doesn't affect rendering. Example:

```csharp

public override string ToString()

{

return "hello";

}

```

public override string ToString()

{

return "hello";

}

### GFM extensions

On top of CommonMark the component enables the [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) extensions:

- **Tables** - pipe-delimited, header separated by `|---|---|`.
- **Task list items** - `- [x] done`, `- [ ] todo`.
- **Strikethrough** - `~~text~~` → text.
- **Autolinks** - bare `https://...` URLs become clickable, and `<https://...>` works too.

### GFM - tables

Pipe-delimited cells. The header row is required, separated from the body by a row of dashes. Trailing pipes are optional. Alignment markers in the separator row (`:---`, `:--:`, `---:`) are recognized but have no effect in the current version - cell content is left-aligned. Example:

| Column A | Column B | Column C |

|----------|----------|----------|

| A1       | B1       | C1       |

| A2       | B2       | C2       |

| **Column A** | **Column B** | **Column C** |
| --- | --- | --- |
| A1 | B1 | C1 |
| A2 | B2 | C2 |

### GFM - task list

A bulleted item that starts with `[ ]` or `[x]` is rendered with a checkbox. Example:

- [x] Done

- [ ] To do

- [ ] Also to do

☑ Done

☐ To do

**☐ Also to do**

### Additional extensions

Beyond CommonMark and GFM the following extensions are enabled by default:

- **Footnotes** - `text[^1]` with `[^1]: definition` later.
- **Definition lists** - a term, then `:   definition` indented under it.
- **Highlight** - `==marker==` → marker.
- **Superscript** - `x^2^` or `x^(2)` → x2.
- **Subscript** - `H~2~O` → H2O.
- **SmartyPants** - `"text"` → “text”, `--` → –, `---` → -, `...` → ….
- **Obsidian-style callouts** - `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`, `> [!WARNING]`, `> [!CAUTION]`.

### Extension - Obsidian-style callouts

A blockquote that starts with `[!TYPE]` is rendered as a coloured box for that type. The five types and how they look:

> [!NOTE] Side information you don't want to miss.

> [!TIP] Pro tip - make your reports better.

> [!IMPORTANT] Important context the reader has to know.

> [!WARNING] Something that needs the reader's attention.

> [!CAUTION] Risk of negative consequences.

**NOTE**

Side information you don't want to miss.

**TIP**

Pro tip - make your reports better.

**IMPORTANT**

Important context the reader has to know.

**WARNING**

Something that needs the reader's attention.

**CAUTION**

Risk of negative consequences.

### Extension - footnotes

Drop `[^id]` anywhere in the text to add a reference, then define it later with `[^id]: text`. The id can be any word. Example:

Here is a footnote reference[^1] and another[^longnote].


[^1]: First footnote.

[^longnote]: Second footnote with more detail.

Here is a footnote reference[1] and another[2].

The footnotes themselves are collected at the bottom of the component under a horizontal rule:

___________________________________

[1] First footnote.

[2] Second footnote with more detail.

### Extension - definition list

Put the term on its own line, then indent the definition with `:` followed by spaces. Blank line separates entries. Example:

Term

:  Definition of the term.


Another term

:  Definition of the other term.

In the report the colon itself is not shown: the term is displayed in bold, the definition is indented under it, and entries are separated by a blank line.

**Term**

Definition of the term.


**Another term**

Definition of the other term.

### Tips

- The editor and preview scroll in sync - click in either pane to navigate.
- Drag the central splitter to resize the editor and preview.
- Use the toolbar above for quick formatting shortcuts.
- Press **Ctrl+F** to open the Find / Replace dialog.
- Pick a theme from the top-right combo to change preview colors.
