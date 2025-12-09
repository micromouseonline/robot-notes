---
layout: default
title: Author Notes
nav_order: 999 # always put it at the top
# nav_exclude: true
# has_children: true
has_toc: true
mermaid: true
# heading_anchor_links: true | false
# You can optionally add "permalink: /section-title" if you want a cleaner URL
---



# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Hungry?};
        
        C -- Yes --> D[Eat Food];
        D --> H[End]; 
        
        C -- No --> E{Thirsty?};
        
        E -- Yes --> F[Get Drink];
        F --> H; 
        
        E -- No --> G[Keep Working];
        G --> H; 
        
        H([Done!])
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```
---
layout: default
title: Authors Guide
parent: Site Maintenance
nav_order: 1
has_children: false
# Note: You should adjust the 'parent' and 'nav_order' to fit your actual hierarchy
---

# ✍️ Authors Guide

This guide provides an overview of the key formatting tools and features available to authors contributing to this documentation site.

---

## 📝 1. Basic Markdown Features

Always use Markdown for formatting, not raw HTML.

### Headings

Use the hash symbol (`#`) to create headings, which automatically generate the page's structure and the Table of Contents.

| Level | Markdown | Appearance |
| :--- | :--- | :--- |
| Main Page Title | `# Heading 1` (Used for page `title` in front matter) | Not used in body |
| Section | `## Heading 2` | **Large Section Title** |
| Sub-Section | `### Heading 3` | **Medium Section Title** |

### Text Formatting

| Feature | Markdown | Appearance |
| :--- | :--- | :--- |
| **Bold** | `**bold text**` | **bold text** |
| *Italics* | `*italic text*` | *italic text* |
| Code Snippet | `` `inline code` `` | `inline code` |
| Blockquote | `> This is a note.` | > This is a note. |

### Lists and Links

* **Unordered Lists:** Use a hyphen (`-`) or asterisk (`*`).
    ```markdown
    * Item 1
    * Item 2
    ```
* **Ordered Lists:** Use numbers followed by a period (`.`).
    ```markdown
    1. First Step
    2. Second Step
    ```
* **Links:** Always use **relative links** for internal pages, excluding the `.md` extension.
    ```markdown
    [Link Text](../getting-started/installation)
    ```

---

## 📐 2. Mathematical Expressions

This site supports standard LaTeX syntax for mathematical expressions, rendered using MathJax.

### Inline Expressions

To insert an expression *within a line of text*, enclose it in single dollar signs (`$`).

* **Markdown:** `The equation is $E = mc^2$ for any mass $m$.`
* **Appearance:** The equation is $E = mc^2$ for any mass $m$.

### Display Equations

To display a large, complex equation on its own line, centered, enclose it in double dollar signs (`$$`).

* **Markdown:**
    ```markdown
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
    ```
* **Appearance:**
    $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

## 📊 3. Mermaid Diagrams

The **Mermaid** feature allows you to create flowcharts, sequence diagrams, and other visuals using simple text syntax. This feature is **enabled by default** on all pages.

### Usage

1. Use a standard code block fenced with **`mermaid`**.
2. Specify the diagram type (e.g., `graph TD` for a Top-Down flowchart).
3. Define the nodes and connections.

* **Markdown:**
    ```mermaid
    graph TD
        A[Start] --> B(Process);
        B --> C{Decision?};
        C -- Yes --> D[End];
        C -- No --> B;
    ```

---

## 🧭 4. Table of Contents (TOC)

The Table of Contents feature is **automatic** and controlled by the theme, but it's important to know how it works.

* **Auto-Generation:** The TOC is automatically generated on the **right side** of the screen for any page that has headings of level $\text{H}2$ or lower (`##` and `###`).
* **Minimum Headings:** If a page has very few headings, the TOC may not appear, as the theme hides it to save screen space.
* **TOC Control:** If you need to force the TOC to appear or hide it, you can use the following front matter attribute (though it's usually best to let the theme manage this):
    ```yaml
    ---
    has_toc: true # or false
    ---
    ```