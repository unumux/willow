# **Willow-Global-Alert**

[Demo](https://unumux.github.io/willow-testing-site/components/global-alert.html)

The purpose of a global alert is to communicate a major site or global level message to all users no matter what page they are on or whether they are logged in. Global alerts should be placed at the top of the website so that they appear above the [willow-page-header](../page-header) component on every page. These alerts do not require a user response and can optionally have a close or dismiss button.  If a global alert contains a close button and the user selects to close it, then the message should no longer appear on the current page or any other page. Messages can be errors, warnings, successes, and updates. _Examples: “Due to the hurricane, our Call Center is currently closed”, “Our Website will undergo scheduled maintenance next Wednesday at 6am”, “Our new amazing service is now available!”_

---

## HTML Snippet

```html
<section class="willow-global-alert" data-global-alert-is-open="true" role="alert">
    <div class="container-fluid">
        <div class="willow-global-alert__container">
            <div class="willow-global-alert__icon"><!-- insert icon here --></div>
            <div class="willow-global-alert__content-container">
                <a class="willow-global-alert__close" href="#"><!-- insert close text and optional icon here --></a>
                <h1 class="willow-global-alert__heading"><!-- insert heading text here --></h1>
                <div class="willow-global-alert__content">
                    <!-- insert components here -->
                </div>
            </div>
        </div>
    </div>
</section>


<!-- modified versions -->
<section class="willow-global-alert willow-global-alert--positive" data-global-alert-is-open="true" role="alert">
    <div class="container-fluid">
        <div class="willow-global-alert__container">
            <div class="willow-global-alert__icon"><!-- insert icon here --></div>
            <div class="willow-global-alert__content-container">
                <a class="willow-global-alert__close" href="#"><!-- insert close text and optional icon here --></a>
                <h1 class="willow-global-alert__heading"><!-- insert heading text here --></h1>
                <div class="willow-global-alert__content">
                    <!-- insert components here -->
                </div>
            </div>
        </div>
    </div>
</section>

<section class="willow-global-alert willow-global-alert--warning" data-global-alert-is-open="true" role="alert">
    <div class="container-fluid">
        <div class="willow-global-alert__container">
            <div class="willow-global-alert__icon"><!-- insert icon here --></div>
            <div class="willow-global-alert__content-container">
                <a class="willow-global-alert__close" href="#"><!-- insert close text and optional icon here --></a>
                <h1 class="willow-global-alert__heading"><!-- insert heading text here --></h1>
                <div class="willow-global-alert__content">
                    <!-- insert components here -->
                </div>
            </div>
        </div>
    </div>
</section>

<section class="willow-global-alert willow-global-alert--negative" data-global-alert-is-open="true" role="alert">
    <div class="container-fluid">
        <div class="willow-global-alert__container">
            <div class="willow-global-alert__icon"><!-- insert icon here --></div>
            <div class="willow-global-alert__content-container">
                <a class="willow-global-alert__close" href="#"><!-- insert close text and optional icon here --></a>
                <h1 class="willow-global-alert__heading"><!-- insert heading text here --></h1>
                <div class="willow-global-alert__content">
                    <!-- insert components here -->
                </div>
            </div>
        </div>
    </div>
</section>
```

---

## Elements

### willow-global-alert

- Required
- Restrictions
  - Should Contain: the Bootstrap `.container-fluid` element

#### _Modifiers_

`--positive`: use to give user positive feedback such as _Success Messages_

`--warning`: use to give user a warning such as _Negative Non-Error Messages_

`--negative`: use to give user negative feedback such as _Error Messages_

#### _States_

`<div class="willow-global-alert" data-global-alert-is-open="true">` : when set to anything other than true the global-alert will not be shown

#### _Notes_

- **willow-global-alert** should be used only once and be placed immediately after the opening [willow-page-container](../willow-page-container) tag.
- **willow-global-alert** should come before the[willow-skip-nav](../skip-nav) component
- The use of `role="alert"` with the `<section>` element ensures that **willow-global-alert** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="alert">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### container-fluid

- Required
- Restrictions
  - Should Contain: **willow-global-alert** elements

#### _Notes_

- The `container-fluid` class from Bootstrap is used within **willow-global-alert** to restrict the width of the component's content while allowing styles applied to the main **willow-global-alert** block to span the full-width of the [willow-page-container](../page-container) component.

---

### willow-global-alert__icon

- Optional
- Restrictions
  - Should Contain: icon

---

### willow-global-alert__container

- Required
- Restrictions
  - Should Contain: alert content elements (**__heading**, **__content**, and **__close**)

#### _Notes_

- **willow-global-alert__container** contains all content and action items for the alert

---

### willow-global-alert__close

- Optional
- Restrictions
  - Should Contain: text
  - Can Also Contain: icon

#### _Notes_

- clicking **willow-global-alert__close** (with mouse or keyboard) should toggle the close state for **willow-global-alert** and store the fact that the user dismissed the alert - so it does not continue to show on other pages

---

### willow-global-alert__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-global-alert__heading** is visible by default, and even if it is hidden it is required to meet accessibility standards
- To hide the **willow-global-alert__heading** add the [`sr-only`](../../utilities.md) utility class to the element

---

### willow-global-alert__content

- Required
- Restrictions
  - Should Contain: one or more components

---

## [Variables](./styles/_default-variables.scss)

`$component-global-alert-background-color` : sets `background-color` property on **willow-global-alert**

`$component-global-alert-text-color` : sets `color` property on **willow-global-alert**

`$component-global-alert-positive-background-color` : sets `background-color` property on **willow-global-alert--positive**

`$component-global-alert-positive-text-color` : sets `color` property on **willow-global-alert--positive**

`$component-global-alert-warning-background-color` : sets `background-color` property on **willow-global-alert--warning**

`$component-global-alert-warning-text-color` : sets `color` property on **willow-global-alert--warning**

`$component-global-alert-negative-background-color` : sets `background-color` property on **willow-global-alert--negative**

`$component-global-alert-negative-text-color` : sets `color` property on **willow-global-alert--negative**
