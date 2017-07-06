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
- The use of `role="alertdialog"` with the `<section>` element ensures that **willow-modal__container** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="alertdialog">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-modal__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-modal__heading** is visible by default, and even if it is hidden, it is required to meet accessibility standards
- To hide the **willow-modal__heading** add the `sr-only` utility class to the element

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
