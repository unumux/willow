---
component: willow-modal
collection: 
    - component
    - information
---
# **Willow-Modal**

[Demo](http://codepen.io/team/UnumUX/pen/yMgJbb)

**Willow-Modal** is a small window that overlays (pops up over) the content of a webpage in order to draw the user’s attention to crucial information that requires action. The modal will halt the user from continuing until they provide the required action. Unlike the [willow-dialog](../dialog) component, the modal cannot be closed by pressing escape or clicking outside of the window.

_Examples: Confirming deletion of information, entering an email address to download something, agreeing to terms of use._

---

## HTML Snippet

```html
<div class="willow-modal">
  <section class="willow-modal__container" role="alertdialog">
    <h1 class="willow-modal__heading">Modal</h1>
    <div class="willow-modal__content">
        <!-- insert content components here -->
    </div>
    <ul class="willow-modal__actions">
      <li class="willow-modal__action"><!-- insert action component here --></li>
    </ul>
  </section>
</div>
```

---

## Elements

### willow-modal

- Required
- Restrictions
  - Should Contain: the **willow-modal__container** element

#### _States_

`<section class="willow-modal" data-modal-close="true">` : closes the modal

#### _Notes_

- **willow-modal** produces a semi-transparent overlay over the page content to help a user focus on the modal and to stop interaction with the page  until the user closes the modal
- clicking outside of the **willow-modal__container** should **NOT** trigger the **willow-modal** to close

---

### willow-modal__container

- Required
- Restrictions
  - Should Contain: modal content elements (**__heading**, **__content**, and **__actions**)

#### _Notes_

- **willow-modal__container** contains all content and action based items for the modal
- clicking outside of the **willow-modal__container** window should **NOT** trigger the **willow-modal** to close
- **willow-modal__container** has a `role="alertdialog"` for accessibility

---

### willow-modal__heading

- Required
- Restrictions
  - Should Contain: text

#### _Modifiers_

`--sr`: hides **willow-modal__heading**

#### _Notes_

- **willow-modal__heading** is visible by default and even if it is hidden, it is required to meet accessibility standards

---

### willow-modal__content

- Required
- Restrictions
  - Should Contain: one or more components

---

### willow-modal__actions

- Required
- Restrictions
  - Should Contain: one or more **willow-modal__action** elements

---

### willow-modal__action

- Required
- Restrictions
  - Should Contain: one _actionable_ component (such as [willow-button](../button) or a link)

#### _Notes_

- completing the actionable component should record the response and trigger the **willow-modal** to close
