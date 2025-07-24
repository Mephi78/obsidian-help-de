---
permalink: obsidian-flavored-markdown
---
#TODO
Obsidian strives for maximum capability without breaking any existing formats. As a result, we use a combination of flavors of [[Formatierungsgrundlagen|Markdown]].

Obsidian supports [CommonMark](https://commonmark.org/), [GitHub Flavored Markdown](https://github.github.com/gfm/), and [LaTeX](https://www.latex-project.org/). Obsidian does not support using Markdown formatting or blank lines inside of HTML tags.

### Supported Markdown extensions

| Syntax          | Description                                                           |
| --------------- | --------------------------------------------------------------------- |
| `[[Link]]`      | [[Internal links]]                                                    |
| `![[Link]]`     | [[Embed files]]                                                       |
| `![[Link#^id]]` | [[Internal links#Link to a block in a note\|Block references]]        |
| `^id`           | [[Internal links#Link to a block in a note\|Defining a block]]        |
| `[^id]`         | [[Formatierungsgrundlagen#Fußnoten\|Footnotes]]                      |
| `%%Text%%`      | [[Formatierungsgrundlagen#Kommentare\|Comments]]                        |
| `~~Text~~`      | [[Formatierungsgrundlagen#Betonungen\|Strikethroughs]] |
| `==Text==`      | [[Formatierungsgrundlagen#Betonungen\|Highlights]]     |
| `` ``` ``       | [[Formatierungsgrundlagen#Quelltext-Blöcke\|Code blocks]]                  |
| `- [ ]`         | [[Formatierungsgrundlagen#Aufgabenlisten\|Incomplete task]]               |
| `- [x]`         | [[Formatierungsgrundlagen#Aufgabenlisten\|Completed task]]                |
| `> [!note]`     | [[Callouts]]                                                          |
| (see link)      | [[Advanced formatting syntax#Tables\|Tables]]                         |
