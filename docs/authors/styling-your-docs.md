---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Styling Documents with Markdown

Although quite simple, markdown documents have a range of basic options 
for styling. These include headings, line breaks, paragraphs, emphasis, blockquotes
lists, code. rules and links

## Headings

Headings are created by starting the line with a number of `#` characters, followed 
by a space. Use one for the top level heading, two for the second and so on. In 
Material for MkDocs, the heading levels are used to create the Table Of Contents (TOC)
that you see to the right of the page so plan accordingly and use headings as part 
of the page navigation. Try ro restrict yourself to no more than four levels. 
Keep the headings short to keep the TOC neat

### Heading 3
Nothing to see here

#### Heading 4
Nothing here either

## Paragraphs and Line Breaks

Normally markdown text is rendered as a continuous block even if the source has a new 
line character or additional spaces. These are all counted as whitespace and reduced to
a single space on the finished page.

To start a new paragraph, you need to leave at least one blank line. Leaving more than one
blank line does not increase the gap. Like the other whitespace, blank lines are condensed 
down to one.

Paragraphs are always rendered without a first line indent so don't add one. Indeed, 
indenting text has a special meaning in markdown.

Line breaks can be tricky. A single line break in the source markdown will be ignored. However,
if you end a line with two or more spaces, a newline will be inserted. This can be a bit
of a surprise if newlines are appearing in unexpected places or if you expect them but
your text editor is in the habit of removing trailing spaces.

To be explicit, you can force a new line with the `<br>` tag from HTML. In general, always
prefer this explicit method so that your intent is clear.


## Emphasis
!!! info "Emphasis"

    | markup               | result            |
    |----------------------|-------------------|
    | `*italic text*`      | *italic text*     |
    | `**bold text**`      | **bold text**     |
    | `***bold italics***` | ***bold italic*** |

## Blockquotes

Blockquotes are used to provide emphasis for a paragraph or content block. To generate
a blockquote, start the paragraph with a single `>` followed by a space:

> There is no need to indent the text, it will be indented and highlighted automatically 
when rendered. As with normal text, you need to use an empty line to move on to the 
next, plain paragraph.<br>
If you need an empty line, use two linebreaks like this:  `<br><br>`<br><br>
The normal line break methods work inside block quotes just fine.<br>
Always put a blannk line before and after a blockquote to ensure it is rendered as expected.

You may see a recommendation to prefix each line in a blockquote with a `>` character 
but this is likely to cause problems when the page resizes. It is sometimes possible 
to use blockquotes with other markup option. There is no real guarantee about what 
will work correctly.


## Lists

You can have ordered and unordered lists. These are quite basic but easy enough to use:

### Unordered Lists

Start each entry on its own line with a `-` or `*` followed by a space

<div class="grid grid-2" markdown>

``` title="Markdown"
* Sed sagittis eleifend rutrum
* Donec vitae suscipit est
* Nulla tempor lobortis orci
```

* Sed sagittis eleifend rutrum
* Donec vitae suscipit est
* Nulla tempor lobortis orci

</div>

You can have a list within a list by indenting the sublist by four spaces. There is 
no guarantee that the sublist will use different markers.
<div class="grid grid-2" markdown>

``` title="Markdown"
- Install the required software
- Configure the project settings
- Prepare the hardware components
    - Connect the power supply
    - Attach the sensor module
    - Verify all cable connections
- Run initial diagnostics
- Review the system logs
- Deploy the final build

```

- Install the required software
- Configure the project settings
- Prepare the hardware components
    - Connect the power supply
    - Attach the sensor module
    - Verify all cable connections
- Run initial diagnostics
- Review the system logs
- Deploy the final build
</div>


### Ordered Lists

These work just like unordered lists except that you start each line with a number 
followed by a dot. 
Topreserve your sanity, or not, items are sequentially numbered from 1 regardless of 
what number you actually use. Ordered list can also have sublists.
Sublists will restart their sequening but should use a different symbol - most
likely a letter instead of a number.

<div class="grid grid-2" markdown>

``` title="Markdown"
1. Install the required software
1. Configure the project settings
1. Prepare the hardware components
    1. Connect the power supply
    1. Attach the sensor module
    1. Verify all cable connections
       (Carefully)
1. Run initial diagnostics
1. Review the system logs
1. Deploy the final build

```

1. Install the required software
1. Configure the project settings
1. Prepare the hardware components
    1. Connect the power supply
    1. Attach the sensor module
    1. Verify all cable connections
       (carefully)
2. Run initial diagnostics
3. Review the system logs
4. Deploy the final build
</div>

List items for both types of list can extend over more than one line by matching 
the indent and omitting the start marker.

## Code

There are many occasions when you do not want to have your source text interpreted or transformed 
in any way. Most commonly, this is to allow the display of program source code. Markdown has a 
number of ways to achieve this. First, you can use a single backtick character (\`) around
some text to make sure it is displayed as plain text. You might use this inside sentences to
mark a variable name or menu option as plain text. 

For example, \`main()\` is displayed as `main()`.

When you have several lines of code, you can construct a block by placing three backticks on a line,
then your code and finally another three backticks to terminate the complete code block. Adding a 
language type after the first set of backticks will enable syntax highlighting

<div class="grid grid-2" markdown>

``` title="Markdown"
   ``` C
   int max_val(int* arr, int n) {
     int max = arr[0];
     for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
     }
     return max;
   }
   ```
```

``` C
int max_val(int* arr, int n) {
  int max = arr[0];
  for (int i = 1; i < n; i++) {
      if (arr[i] > max) {
          max = arr[i];
      }
  }
  return max;
}
```
</div>
See the separate [page on code blocks](code-blocks.md) for more  examples

## Horizontal dividers

Sections of the page can be separated with a horizontal line if you place three hyphens
together on a line of their own.

`---`

Produces a divider

---

Like that

## Links

Links to other pages or external content generally consist of two parts. The first part is 
the text that will be displayed and must go inside square brackets. The second part is the 
actual path or URL and it goes insde parentheses. You could link to Wikipedia for
example like this:

` Wikipedia has an entry for [Markdown](https://en.wikipedia.org/wiki/Markdown) `

Wikipedia has an entry for [Markdown](https://en.wikipedia.org/wiki/Markdown) 

Or you could just place the path or URL inside angle brackets like this:

`<https://www.markdownguide.org>`

<https://www.markdownguide.org>