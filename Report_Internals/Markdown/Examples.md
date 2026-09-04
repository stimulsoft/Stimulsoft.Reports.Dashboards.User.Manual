# Markdown Examples

This chapter describes text formatting examples for the Markdown component.

### Supported standard

The component supports [CommonMark 0.31.2](https://spec.commonmark.org/0.31.2/) - the full official specification.

### What you get from CommonMark

- **Headings** - `# H1` / `## H2` / `### H3` / `#### H4` / `##### H5` / `###### H6`.
- **Paragraphs** - blank line separates paragraphs. Hard break: two trailing spaces or `\` at line end.
- **Emphasis** - `*italic*` → *italic*, `**bold**` → **bold**, `***both***` → ***both***.
- **Inline code** - ``code`` → `code`.
- **Fenced code block** - ````` opens / closes a block; the language tag is preserved as text.
- **Indented code block** - start every line with 4 spaces (or a tab).
- **Bulleted list** - `- item`, `* item` or `+ item`; indent for nesting.
- **Ordered list** - `1. item`, `2. item` …; numbers don't have to be sequential.
- **Links** -`[text](https://example.com)` → text, with optional `"title"`.
- **Images** - `![alt](https://example.com/pic.png)` on a line of its own.
- **Blockquotes** - `> quoted line`; nest with `>> deeper`.
- **Thematic break** - `---`, `***` or `___` on a line of its own.
- **HTML entities** - `&copy;` → ©, `&mdash;` → -, `&amp;` → &.
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

Pipe-delimited cells. The header row is required, separated from the body by a row of dashes. Trailing pipes are optional. Example:

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
- **Superscript** - `x^2^` → x2.
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

**Here is a footnote reference[1] and another[2].**

### Extension - definition list

Put the term on its own line, then indent the definition with `:` followed by spaces. Blank line separates entries. Example:

Term

:  Definition of the term.


Another term

:  Definition of the other term.

### Term

Definition of the term.

**Another term**

Definition of the other term.

### Tips

- The editor and preview scroll in sync - click in either pane to navigate.
- Drag the central splitter to resize the editor and preview.
- Use the toolbar above for quick formatting shortcuts.
- Press **Ctrl+F** to open the Find / Replace dialog.
- Pick a theme from the top-right combo to change preview colors.
