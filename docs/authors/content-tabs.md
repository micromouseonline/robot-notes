---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Content tabs

Sometimes, it's desirable to group alternative content under different tabs,
e.g. when illustrating some function written in different programming languages. 
Material for MkDocs allows for beautiful and functional tabs, grouping code blocks 
and other content.


=== "red" 
    This is red stuff. It must be indented by 4 spaces

=== "green" 
    This is green stuff. It too must be indented by 4 spaces

=== "blue" 
    This is blue stuff. Always indent the content by 4 spaces



## Usage

### Basic tabs

Tab names/titles follow a marker like `=== Tab Title`. Always indent the tab content by four spaces.
The three tabs above were created with this markdown
```
=== "red" 
    This is red stuff. It must be indented by 4 spaces

=== "green" 
    This is green stuff. It too must be indented by 4 spaces

=== "blue" 
    This is blue stuff. Always indent the content by 4 spaces
```

### Grouping code blocks

Code blocks are one of the common targets to be grouped:

``` title="Markup for tabs with code blocks"
=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
```

<div class="result" markdown>
Produces

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

</div>

### Grouping other content

Content tabs can contain arbitrary content. Just be sure to indent the 
content by 4 spaces:

``` title="Content tabs"
=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci

=== "Equation"

     $\begin{align}
     2x	+	y	−	2z  &=	3   \\\
     x	−	y	−	z    &=	0   \\\
     x	+	y	+	3z   &=	12
     \end{align}$

=== "Image"

     ![llk](../assets/pie-chart-thumbnail.png)    

=== "Table"

    | Method      | Description                          |
    | ----------- | ------------------------------------ |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |     
```

<div class="result" markdown>
Produces
=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci

=== "Equations"

     $\begin{align}
     2x	+	y	−	2z  &=	3   \\\
     x	−	y	−	z    &=	0   \\\
     x	+	y	+	3z   &=	12
     \end{align}$

=== "Image"

     ![llk](../assets/pie-chart-thumbnail.png)

=== "Table"

    | Method      | Description                          |
    | ----------- | ------------------------------------ |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |

</div>

### Embedded content

Not only can content tabs can contain arbitrary nested content, 
including further content tabs, they can be nested in other blocks 
like [admonitions] or blockquotes:

``` title="Content tabs in an admonition block"
!!! example

    === "Unordered List"

        ``` markdown
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci
        ```

    === "Ordered List"

        ``` markdown
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci
        ```
```

<div class="result" markdown>

!!! example

    === "Unordered List"

        ``` markdown
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci
        ```

    === "Ordered List"

        ``` markdown
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci
        ```

</div>

