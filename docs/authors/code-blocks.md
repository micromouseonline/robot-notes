---
icon: 
subtitle: 
---

# Code blocks

Code blocks and examples are an essential part of technical project
documentation. Material for MkDocs provides an easy method to provide
syntax highlighted bolck of source during build time using [Pygments].

  [Pygments]: https://pygments.org


## Usage

Code blocks must be enclosed with two separate lines containing three backticks.
To add syntax highlighting to those blocks, add the language shortcode directly
after the opening block. See the [list of available lexers] to find the
shortcode for a given language:

```` markdown title="Page source for simple code block"
``` py
import tensorflow as tf
```
````
Is displayed as:
<div class="result" markdown>

``` py
import tensorflow as tf
```
</div>

  [list of available lexers]: https://pygments.org/docs/lexers/

### Providing alternatives

You can place different language versions of your code in separate tabs to 
provide choice for the reader without taking up excessive space on the page.

Here are five code blocks that show how to output the integers from 0 to 100.

=== "C"
    ``` C
    #include <stdio.h>

    int main() {
        for (int i = 0; i <= 100; i++) {
            printf("%d\n", i);
        }
        return 0;
    }
    ```
=== "C++"
    ``` cpp
    #include <iostream>
    using namespace std;

    int main() {
        for (int i = 0; i <= 100; i++) {
            cout << i << endl;
        }
        return 0;
    }
    ```

===  "Python"
    ``` python
    for i in range(101):
        print(i)
    ```

=== "Basic"
    ``` basic
    FOR I = 0 TO 100
        PRINT I
    NEXT I
    ```

=== "Forth"
    ``` forth
    101 0 DO
      I .
    LOOP
    ```


### Adding a title

To provide additional context, a custom title can be added to a code
block by using the `title="<custom title>"` option directly after the shortcode,
e.g. to display the name of a file:

```` markdown title="Page source for code block with title"
``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````
Is displayed as:
<div class="result" markdown>
``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
</div>


### Adding line numbers

Line numbers can be added to a code block by using the `linenums="<start>"`
option directly after the shortcode, whereas `<start>` represents the starting
line number. A code block can start from a line number other than `1`, which
allows to split large code blocks for readability:

```` markdown title="Page source for code block with line numbers"
``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````
Is displayed as:
<div class="result" markdown>
``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
</div>

### Code copy and select buttons

<!-- md:version 9.0.0 -->
<!-- md:feature -->

Code blocks normally render a pair button on the right side to allow the
user to copy a code block's contents to the clipboard. 

  ```{ .cpp }
  # Code block content has a copy button
    for (int a = 0; a < 100; a++){
      total += a;
    }
  ```

Note that there must be a language shortcode, which 
has to come first and must also be prefixed by a `.`. Similarly, 
the copy and select buttons can also be disabled for a specific code block:

  ``` { .cpp .no-copy .no-select}
  # Code block content has no copy button
    for (int a = 0; a < 100; a++){
      total += a;
    }
  ```
To enable or disable the copy button without syntax highlighting, you also can
use the `.text` language shortcode, which doesn't highlight anything.    

``` { .text .no-copy }
  this has
  no copy
  button
```


### Highlighting specific lines

Specific lines can be highlighted by passing the line numbers to the `hl_lines`
argument placed right after the language shortcode. Note that line counts start
at `1`, regardless of the starting line number specified as part of
[`linenums`][Adding line numbers]. You can highlight individual lines or a range of lines

=== "Lines"

    ```` markdown title="Code block with highlighted lines"
    ``` py hl_lines="3 5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````

    <div class="result" markdown>

    ``` py linenums="1" hl_lines="3 5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    </div>

=== "Line ranges"

    ```` markdown title="Code block with highlighted line range"
    ``` py hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````

    <div class="result" markdown>

    ``` py linenums="1" hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    </div>

  [Adding line numbers]: #adding-line-numbers

### Highlighting inline code blocks

Syntax highlighting can be applied to inline
code blocks by prefixing them with a shebang, i.e. `#!`, directly followed by
the corresponding [language shortcode][list of available lexers].

``` markdown title="Page source for an inline code block"
The `#!python range()` function is used to generate a sequence of numbers.
```

<div class="result" markdown>
The `#!python range()` function is used to generate a sequence of numbers.
</div>
