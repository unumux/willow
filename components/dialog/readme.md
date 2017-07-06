---
component: willow-dialog
collection: 
    - component
    - information
---
# **Willow-Dialog**

[Demo](http://codepen.io/team/UnumUX/pen/JWEKRZ)

**Willow-Dialog** is a small window that overlays (pops up over) the content of a webpage. Dialogs communicate information to a user and can prompt them with questions that **do not** require a response. If any of your questions require an answer use the [willow-modal](../modal) component instead. The dialog should disappear if the user has completed the task or action, pressed the `esc` key, or clicked outside of the dialog.

_Examples: errors, warnings, to collect data, to inform users of important information, to provide opt-in options like email signup_

---

## Willow Dialog vs Willow Modal

|           Dialog                  |      |               Modal                       |
|:----------------------------------|:----:|:------------------------------------------|
|         Contains a Message        |      |     Contains a Message                    |
| Can Contain an Action or Question |      |   Must Contain an Action or Question      |
|Does Not Require Action or Answer  |      |     Requires Action or Answer             |
|    Multiple Ways to Close Window  |      | Action or Answer Required to Close Window |

---

## HTML Snippet

```html
<div class="willow-dialog">
    <section class="willow-dialog__container" role="dialog">
        <h1 class="willow-dialog__heading">Heading Text</h1>
        <div class="willow-dialog__content">
            <!-- insert content components here-->
        </div>
        <ul class="willow-dialog__actions">
            <li class="willow-dialog__action"><!-- insert action component here --></li>
        </ul>
    </section>
</div>
```

---

## Elements

### willow-dialog

- Required
- Restrictions
  - Should Contain: the **willow-dialog__container** element

#### _States_

`<section class="willow-dialog" data-dialog-close="true">` : closes the dialog

#### _Notes_

- **willow-dialog** produces a semi-transparent overlay over the page content to help a user focus on the dialog and to stop interaction with the page until the user closes the dialog
- the **willow-dialog** should close when a user clicks outside of the **willow-dialog__container** element
- pressing the `esc` key on the keyboard should trigger the **willow-dialog** to close

---

### willow-dialog__container

- Required
- Restrictions
  - Should Contain: dialog content elements (**__heading**, **__content**, and **__actions**)

#### _Notes_

- **willow-dialog__container** contains all content and action based items for the dialog
- clicking outside of the **willow-dialog__container** window should trigger the **willow-dialog** to close
- The use of `role="dialog"` with the `<section>` element ensures that **willow-dialog__container** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="dialog">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-dialog__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-dialog__heading** is visible by default, and even if it is hidden, it is required to meet accessibility standards
- To hide the **willow-dialog__heading** add the `sr-only` utility class to the element

---

### willow-dialog__content

- Required
- Restrictions
  - Should Contain: one or more components

---

### willow-dialog__actions

- Optional
- Restrictions
  - Should Contain: one or more **willow-dialog__action** elements

---

### willow-dialog__action

- Optional
- Repeatable
- Restrictions
  - Should Contain: one _actionable_ component (such as [willow-button](../button) or a link)

#### _Notes_

- completing the actionable component should record the response and trigger the **willow-dialog** to close
