---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
title: Adding Diagrams
subtitle: 
description:
icon:
status:
---

# Diagrams

Diagrams can be a valuable addition to your documentation, helping to 
clarify otherwise complicated ideas and relationships.
This site makes use of [Mermaid.js], a popular and flexible 
solution for drawing diagrams, if a little clunky at times

  [Mermaid.js]: https://mermaid.js.org/


 
??? info "Limitations"
    While all [Mermaid.js] features should work out-of-the-box, Material for
    MkDocs will currently only adjust the fonts and colors for flowcharts,
    sequence diagrams, class diagrams, state diagrams and entity relationship
    diagrams. See the section on [other diagrams] for more information why this
    is currently not implemented for all diagrams.

 
## Usage

### Flowcharts

[Flowcharts] are diagrams that represent workflows or processes. The steps
are rendered as nodes of various kinds and are connected by edges, describing
the necessary order of steps. Flowcharts can be drawn top-to-bottom or left-to-right.
The only difference is the direction directive:

!!! info "Flow chart"

    === "Top Down"
        ```` markdown
            ``` mermaid
            flowchart TD
                ReadMe[Documentation] --> Guides[Guides]
                ReadMe --> API[API]    
                Guides --> Editor[UI]
                API --> APIREF[Reference]
                API --> APIEXAMPLE[Examples]
            ```
        ````


    === "Left To Right"
        ```` markdown
            ``` mermaid
            flowchart LR
                ReadMe[Documentation] --> Guides[Guides]
                ReadMe --> API[API]    
                Guides --> Editor[UI]
                API --> APIREF[Reference]
                API --> APIEXAMPLE[Examples]
            ```
        ````


<div class="result" markdown>

``` mermaid
flowchart TD
    ReadMe[Documentation] --> Guides[Guides]
    ReadMe --> API[API]
    Guides --> Editor[UI]
    API --> APIREF[Reference]
    API --> APIEXAMPLE[Examples]
```


``` mermaid
flowchart LR
    ReadMe --> API[API]
    ReadMe[Documentation] --> Guides[Guides]
    Guides --> Editor[UI]
    API --> APIREF[Reference]
    API --> APIEXAMPLE[Examples]
```

</div>

  [Flowcharts]: https://mermaid.js.org/syntax/flowchart.html

### Sequence diagrams

[Sequence diagrams] are used to illustrate the interactions between 
entities, including the passing of messages or changes in state. This diagram shows how data is transferred between master and slave SPI devices.

```` markdown title="Sequence diagram"
``` mermaid
sequenceDiagram
    participant Master
    participant Slave

    Master->>Slave: SS low (select slave)
    Master->>Slave: Send MOSI byte (clocked)
    Slave-->>Master: Return MISO byte (simultaneous)
    Master->>Slave: SS high (end transaction)
```
````

<div class="result" markdown>
``` mermaid
sequenceDiagram
    participant Master
    participant Slave

    Master->>Slave: SS low (select slave)
    loop Byte 1..N
        Master->>Slave: MOSI byte[i] (clocked)
        Slave-->>Master: MISO byte[i] (simultaneous)
    end
    Master->>Slave: SS high (end transaction)
```
</div>

``` mermaid
sequenceDiagram
    participant Master
    participant Slave

    Master->>Slave: SS low (select slave)
    loop Byte 1..N
        Master->>Slave: MOSI byte[i] (clocked)
        Slave-->>Master: MISO byte[i] (simultaneous)
    end
    Master->>Slave: SS high (end transaction)

```


  [Sequence diagrams]: https://mermaid.js.org/syntax/sequenceDiagram.html

### State diagrams

[State diagrams] are great for showing how the various states of a system are
reached as a consequence of the permitted actions. Mermaid is not really very
good at state diagrams - especially where there are tactions that lead back
to the same state. Consider this button debouncer updated at some fixed debounce 
interval:


```` markdown title="State diagram"
``` mermaid
stateDiagram-v2
    [*] --> Released
    Released --> Pressing : HIGH
    Pressing --> Pressed : HIGH
    Pressing --> Released : LOW

    Pressed --> Releasing : LOW
    Releasing --> Pressed : HIGH
    Releasing --> Released : LOW
```
````

<div class="result" markdown>

``` mermaid
stateDiagram-v2 
    [*] --> Released

    Released --> Pressing : HIGH
    Pressing --> Pressed : HIGH
    Pressing --> Released : LOW

    Pressed --> Releasing : LOW
    Releasing --> Pressed : HIGH
    Releasing --> Released : LOW

```


### Other diagram types

Material for MkDocs also supports Class diagrams and Entiyty-Relationship diagrams.

Besides the diagram types listed above, [Mermaid.js] provides support for
[pie charts], [gantt charts], [user journeys], [git graphs] and
[requirement diagrams], all of which are not officially supported by Material
for MkDocs. Those diagrams should still work as advertised by [Mermaid.js], but
we don't consider them a good choice, mostly as they don't work well on mobile.

  [pie charts]: https://mermaid.js.org/syntax/pie.html
  [gantt charts]: https://mermaid.js.org/syntax/gantt.html
  [user journeys]: https://mermaid.js.org/syntax/userJourney.html
  [git graphs]: https://mermaid.js.org/syntax/gitgraph.html
  [requirement diagrams]: https://mermaid.js.org/syntax/requirementDiagram.html

