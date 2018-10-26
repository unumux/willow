# **Willow-Inline-Alert**

[Demo](https://unumux.github.io/willow-testing-site/components/inline-alert.html)

An inline alert is a highlighted message related to the content of the current page or to the user’s current process. Inline alerts may or may not require the user to respond to a question. Messages can include error messages, warnings, alerts and success messages.

_Examples: Presented on the user’s account page - “Your account is about to expire, please renew online”. Presented in a registration form - “The email address entered is already registered”. Presented in a wizard - “You have successfully submitted your information”._

---

## HTML Snippet

```html
<section class="willow-alert" role="alert">
    <div class="willow-alert__icon"><!-- insert icon here --></div>
    <div class="willow-alert__content-container">
        <a class="willow-alert__close" href="#"><!-- insert close text and optional icon here --></a>
        <h1 class="willow-alert__heading"><!-- insert heading text here --></h1>
        <div class="willow-alert__content">
            <!-- insert components here -->
        </div>
    </div>
</section>

<!-- modified versions -->
<section class="willow-alert willow-alert--positive" role="alert">
    <div class="willow-alert__icon"><!-- insert icon here --></div>
    <div class="willow-alert__content-container">
        <a class="willow-alert__close" href="#"><!-- insert close text and optional icon here --></a>
        <h1 class="willow-alert__heading"><!-- insert heading text here --></h1>
        <div class="willow-alert__content">
            <!-- insert components here -->
        </div>
    </div>
</section>
<section class="willow-alert willow-alert--warning" role="alert">
    <div class="willow-alert__icon"><!-- insert icon here --></div>
    <div class="willow-alert__content-container">
        <a class="willow-alert__close" href="#"><!-- insert close text and optional icon here --></a>
        <h1 class="willow-alert__heading"><!-- insert heading text here --></h1>
        <div class="willow-alert__content">
            <!-- insert components here -->
        </div>
    </div>
</section>
<section class="willow-alert willow-alert--negative" role="alert">
    <div class="willow-alert__icon"><!-- insert icon here --></div>
    <div class="willow-alert__content-container">
        <a class="willow-alert__close" href="#"><!-- insert close text and optional icon here --></a>
        <h1 class="willow-alert__heading"><!-- insert heading text here --></h1>
        <div class="willow-alert__content">
            <!-- insert components here -->
        </div>
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

#### _States_

`<div class="willow-alert" data-alert-is-open="true">` : when set to anything other than true the alert will not be shown

#### _Notes_

- The use of `role="alert"` with the `<section>` element ensures that **willow-alert** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="alert">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.
- **willow-alerts** should be contained in the [willow-page-content](../page-content) component of a site, and will usually appear in forms, dialogs or modals

---

### willow-alert__icon

- Optional
- Restrictions
  - Should Contain: icon

---

### willow-alert__content-container

- Required
- Restrictions
  - Should Contain: alert content elements (**__heading**, **__content**, and **__close**)

#### _Notes_

- **willow-alert__content-container** contains all content and action items for the alert

---

### willow-alert__close

- Optional
- Restrictions
  - Should Contain: text
  - Can Also Contain: icon

#### _Notes_

- clicking **willow-alert__close** (with mouse or keyboard) should toggle the close state for **willow-alert** and store the fact that the user dismissed the alert - so it does not continue to show after page navigation or refresh.

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

---

## [Variables](./styles/_default-variables.scss)

`$component-inline-alert-border-radius` : sets `border-radius` property on **willow-alert**

`$component-inline-alert-background-color` : sets `background-color` property on **willow-alert**

`$component-inline-alert-text-color` : sets `color` property on **willow-alert**

`$component-inline-alert-icon` : passed to the `icon` mixin which sets the `background-image`, `height` and `width` on **willow-alert::before**

`$component-inline-alert-positive-background-color` : sets `background-color` property on **willow-alert--positive**

`$component-inline-alert-positive-text-color` : sets `color` property on **willow-alert--positive**

`$component-inline-alert-positive-icon` : passed to the `icon` mixin which sets the `background-image`, `height` and `width` on **willow-alert--positive::before**

`$component-inline-alert-negative-background-color` : sets `background-color` property on **willow-alert--negative**

`$component-inline-alert-negative-text-color` : sets `color` property on **willow-alert--negative**

`$component-inline-alert-negative-icon` : passed to the `icon` mixin which sets the `background-image`, `height` and `width` on **willow-alert--negative::before**

`$component-inline-alert-warning-background-color` : sets `background-color` property on **willow-alert--warning**

`$component-inline-alert-warning-icon` : passed to the `icon` mixin which sets the `background-image`, `height` and `width` on **willow-alert--warning::before**

`$component-inline-alert-warning-text-color` : sets `color` property on **willow-alert--warning**
