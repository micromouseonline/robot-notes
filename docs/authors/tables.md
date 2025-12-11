---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Data tables

While there are very few ways to align content in markdown, data tables are very easy
to set up and use. Tables are rendered with a default style that has few
customisation options.


## Usage

Data tables can be used at any position in your project documentation and can
contain arbitrary Markdown, including inline code blocks, as well as icons and
emojis:

``` markdown title="Data table"
| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |
```

<div class="result" markdown>
| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |
</div>


### Column alignment

If you want to align a specific column to the `left`, `center` or `right`, you
can use the [regular Markdown syntax] placing `:` characters at the beginning
and/or end of the divider. 

=== "Left"

    ``` markdown hl_lines="2" title="Data table, columns aligned to left"
    | Method      | Description                          |
    | :---------- | :----------------------------------- |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |
    ```

    <div class="result" markdown>

    | Method      | Description                          |
    | :---------- | :----------------------------------- |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |

    </div>

=== "Center"

    ``` markdown hl_lines="2" title="Data table, columns centered"
    | Method      | Description                          |
    | :---------: | :----------------------------------: |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |
    ```

    <div class="result" markdown>

    | Method      | Description                          |
    | :---------: | :----------------------------------: |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |

    </div>

=== "Right"

    ``` markdown hl_lines="2" title="Data table, columns aligned to right"
    | Method      | Description                          |
    | ----------: | -----------------------------------: |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |
    ```

    <div class="result" markdown>

    | Method      | Description                          |
    | ----------: | -----------------------------------: |
    | `GET`       | :material-check:     Fetch resource  |
    | `PUT`       | :material-check-all: Update resource |
    | `DELETE`    | :material-close:     Delete resource |

    </div>

  [regular Markdown syntax]: https://www.markdownguide.org/extended-syntax/#tables


### Sortable tables

This implementation of Material for MkDocs implements [tablesort], which is
natively integrated with Material for MkDocs. To make a table sortable, you will 
need to add an inline JavaScript to the page source. This example identifies the 
last table on the page and makes it sortable:

``` javascript
<script src="https://unpkg.com/tablesort@5.3.0/dist/tablesort.min.js"></script>
<script>
  var tables = document.querySelectorAll("article table")
  new Tablesort(tables.item(tables.length - 1));
</script>
```

To identify a **specific** table, you can place it in an HTML DIV with an ID and then 
have the script look for a table within that div

This is how you write the table in the page source

``` markdown title="The data table with a DIV ID"
<div markdown id = "elements">
| Element | Atomic Mass (u)  | Melting Point (°C)  |
|---------|-----------------:|--------------------:|
| Iron    | 55.845           | 1538                |
| Copper  | 63.546           | 1085                |
| Silicon | 28.085           | 1414                |
| Gold    | 196.967          | 1064                |
| Carbon  | 12.011           | 3550                |
| Sodium  | 22.990           | 98                  |
</div>
```

And this is the script that will find it and make it sortable. Note that you only need 
to link in the external script once but it must be done before any attempt to use it.

``` javascript title="The javascript that makes it sortable"

<script src="https://unpkg.com/tablesort@5.3.0/dist/tablesort.min.js"></script>
<script>
  var wrapper = document.querySelector("#elements");
  var table = wrapper.querySelector("table");
  new Tablesort(table);
</script>

```

And this is the result. The table can be sorted by clicking on a column header.
<div markdown id = "elements">
| Element | Atomic Mass (u)  | Melting Point (°C)  |
|---------|-----------------:|--------------------:|
| Iron    | 55.845           | 1538                |
| Copper  | 63.546           | 1085                |
| Silicon | 28.085           | 1414                |
| Gold    | 196.967          | 1064                |
| Carbon  | 12.011           | 3550                |
| Sodium  | 22.990           | 98                  |
</div>

<script src="https://unpkg.com/tablesort@5.3.0/dist/tablesort.min.js"></script>
<script>
  var wrapper = document.querySelector("#elements");
  var table = wrapper.querySelector("table");
  new Tablesort(table);
</script>


Note that [tablesort] provides alternative comparison implementations like
numbers, filesizes, dates and month names. See the [tablesort documentation]
[tablesort] for more information.

  [tablesort]: http://tristen.ca/tablesort/demo/

### Import table from file

The plugin [mkdocs-table-reader-plugin][table-reader-docs] allows you to
import data from a CSV or Excel file.

  [table-reader-docs]: https://timvink.github.io/mkdocs-table-reader-plugin/