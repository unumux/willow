---
component: willow-dialog
collection: 
    - component
    - information
---
# **Willow-Dialog**

[Demo](http://codepen.io/team/UnumUX/pen/JWEKRZ)

**Willow-Dialog** is a small window that overlays (pops up over) the content of a webpage. Dialogs communicate information to a user and can prompt them with questions that **do not** require a response. If any of your questions require an answer use the [willow-modal](../modal) component instead. The dialog should disappear once the user has entered the requested information, pressed the `esc` key, or clicked outside of the response area/window.

_Examples: errors, warnings, to collect data, to inform users of important information, to provide opt-in options like email signup_

---

## HTML Snippet

```html
<section class="willow-dialog" role="dialog">
  <div class="willow-dialog__container">
    <h1 class="willow-dialog__heading">Heading Text</h1>
    <div class="willow-dialog__content">
        <!-- insert content components here-->
    </div>
    <ul class="willow-dialog__actions">
        <li class="willow-dialog__action"><!-- insert action component here --></li>
    </ul>
  </div>
</section>
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
- **willow-dialog__container** has a `role="dialog"` for accessibility

---

### willow-dialog__heading

- Required
- Restrictions
  - Should Contain: text

#### _Modifiers_

`--sr`: hides **willow-dialog__heading**

#### _Notes_

- **willow-dialog__heading** is visible by default and even if it is hidden, it is required to meet accessibility standards

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