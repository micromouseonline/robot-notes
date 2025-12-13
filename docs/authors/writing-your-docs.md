---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---


# Writing your documentation

Writing the content is really just a question ot typing a load of text. 

For that, pretty well any text editor will do the trick. If you are writing 
documentation for your code then use the same editor or IDE that you use for
the code itself. 

The source text for our documents is plain ascii text that has some embellishments
that let you use flexible formatting optionsfor creating headings, highlights,
lists and many more features. All of this is achieved with simple sequences of
plain text characters. For example the main heading of this page is recognised
as a heading just because the line starts with a `#` character followed by a space.

I can easily **highlight** a word just by placing a pair of `*` characters either 
side. of it.

Want a list? All you need is to start each line with `- ` and you are done:

- Headings
- Highlights
- Lists
- ... and many more

That was made with this source text:

```
- Headings
- Highlights
- Lists
- ... and many more
```

These features, and many more, are descriped in the rest of the pages in this section.
Collectively, they are described as `markdown` and it is normal to crteate the source 
pages with the `.md` extension to the file name/

Markdown is _very_ popular. On github, for example, you can write your `readme.md` file 
for a repository using markdown and the github server will render it automatically for you.

Find out more about markdown at 

- <https://www.markdownguide.org/>
- [Start Writing  on Github](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

This site uses an extension called [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
which extends the feature set considerably.

## Editors

Although you can use any text editor to create the source pages, some editors may provide 
additional facilities to help with things like auto completion or automatic preview of
the generated pages. I use VSCode because it handles pretty well anything and there are
specific extensions for Markdown documents
