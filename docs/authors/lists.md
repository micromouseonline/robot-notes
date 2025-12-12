---
# 1. FRONT MATTER (REQUIRED)
# The MkDocs title is automatically used for the navigation and the page heading.
# title: Template
subtitle: 
description:
icon:
status:
---

# Lists

You should already have seen how to do basic ordered and unordered lists in
the [styling  your docs](styling-your-docs.md) page.

Besides those, you can also create definition lists and task lists.

## Definition Lists

Lists of arbitrary key-value pairs, e.g. the parameters of functions or 
modules, can be enumerated with a simple syntax. If your definition has more than one 
paragraph, be sure to indent it by four or more spaces.

Notice that you can style the terms or leave them plain

``` markdown title="Definition list"
**Negative Feedback**

:   Negative feedback is a regulatory process in which a system responds to a 
change by initiating actions that counteract or reduce that change, helping 
maintain stability.

    It is when a system notices things getting out of hand and calmly says, 
“Alright, let’s dial it back before this turns into a whole situation.”


**Positive Feedback**

:   Positive feedback is a process in which a change in a system triggers 
    responses that amplify or reinforce that change, driving the system 
    further in the same direction.

    It is when a system gets excited about a change and says, “Yes, 
    more of that, please,” until things spiral gloriously out of hand.
```

<div class="result" markdown>

**Negative Feedback**

:   Negative feedback is a regulatory process in which a system responds to a 
change by initiating actions that counteract or reduce that change, helping 
maintain stability.

    It is when a system notices things getting out of hand and calmly says, 
“Alright, let’s dial it back before this turns into a whole situation.”


**Positive Feedback**

:   Positive feedback is a process in which a change in a system triggers 
    responses that amplify or reinforce that change, driving the system 
    further in the same direction.

    It is when a system gets excited about a change and says, “Yes, 
    more of that, please,” until things spiral gloriously out of hand.

</div>

## Task Lists

You may want a list of tasks with some way to indicate which ones are
complete or have some other distinct status. To do that, create an 
unordered list and prefix each entry with `[ ]` to render an unchecked 
checkbox or `[x]` to render a checked checkbox.

These lists can be nested if you wish.

``` markdown title="Task list"
- [x] Assemble the primary chassis and mount the drive motors
- [ ] Integrate the control electronics and verify power distribution
    * [x] Flash the microcontroller with the base firmware
    * [x] Test sensor inputs for correct voltage and signal stability
    * [ ] Calibrate the IMU and update the configuration file
- [ ] Implement obstacle‑avoidance logic and run a full movement test

```

<div class="result" markdown>

- [x] Assemble the primary chassis and mount the drive motors
- [ ] Integrate the control electronics and verify power distribution
    * [x] Flash the microcontroller with the base firmware
    * [x] Test sensor inputs for correct voltage and signal stability
    * [ ] Calibrate the IMU and update the configuration file
- [ ] Implement obstacle‑avoidance logic and run a full movement test


</div>