---
component: willow-inline-alert
collection: 
    - component
    - information
---
# **Willow-Inline-Alert**

[Demo](http://codepen.io/team/UnumUX/pen/yMgJMM)

An inline alert is a highlighted message related to the content of the current page or to the user’s current process. Inline alerts may or may not require the user to respond to a question. Messages can include error messages, warnings, alerts and success messages.

_Examples: Presented on the user’s account page - “Your account is about to expire, please renew online”. Presented in a registration form - “The email address entered is already registered”. Presented in a wizard - “You have successfully submitted your information”._

---

## HTML Snippet

```html
<section class="willow-alert" role="alert">
    <h1 class="willow-alert__heading">Heading Text</h1>
    <div class="willow-alert__content">
        <!-- insert components here -->
    </div>
</section>

<!-- modified versions -->
<section class="willow-alert willow-alert--positive" role="alert">
    <h1 class="willow-alert__heading">Heading Text</h1>
    <div class="willow-alert__content">
        <!-- insert components here -->
    </div>
</section>

<section class="willow-alert willow-alert--warning" role="alert">
    <h1 class="willow-alert__heading">Heading Text</h1>
    <div class="willow-alert__content">
        <!-- insert components here -->
    </div>
</section>

<section class="willow-alert willow-alert--negative" role="alert">
    <h1 class="willow-alert__heading">Heading Text</h1>
    <div class="willow-alert__content">
        <!-- insert components here -->
    </div>
</section>
```

---

## Elements

### willow-alert

- Required
- Restrictions
  - Should Contain: **willow-alert** elements

#### _Modifiers_

`--positive`: Applies colors to give user positive feedback

`--negative`: Applies colors to give user negative feedback

`--warning`: Applies colors to give user a warning

#### _Notes_

- The use of `role="alert"` with the `<section>` element ensures that **willow-alert** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="alert">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.
- **willow-alerts** should be contained in the [willow-page-content](../page-content) component of a site, and will usually appear in forms, dialogs or modals

---

### willow-alert__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-alert__heading** is visible by default, and even if it is hidden it is required to meet accessibility standards
- To hide the **willow-alert__heading** add the `sr-only` utility class to the element

---

### willow-alert__content

- Required
- Restrictions
  - Should Contain: one or more components
