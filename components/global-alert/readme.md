---
component: willow-global-alert
collection: 
    - component
    - information
---
# **Willow-Global-Alert**

[Demo](http://codepen.io/team/UnumUX/pen/XMpKpz)

The purpose of a global alert is to communicate a major site or global level message to all users no matter what page they are on or whether they are logged in. Global alerts should be placed at the top of the website so that they appear above the [willow-page-header](../page-header) component on every page. These alerts do not require a user response and can optionally have a close or dismiss button.  If a global alert contains a close button and the user selects to close it, then the message should no longer appear on the current page or any other page. Messages can be errors, warnings, successes, and updates.

_Examples: “Due to the hurricane, our Call Center is currently closed”, “Our Website will undergo scheduled maintenance next Wednesday at 6am”, “Our new amazing service is now available!”_

---

## HTML Snippet

```html
<section class="willow-global-alert" role="alert">
    <button class="willow-global-alert__close">Button Text</button>
    <h1 class="willow-global-alert__heading">Heading Text</h1>
    <div class="willow-global-alert__content">
        <!-- insert components here -->
    </div>
</section>

<!-- modified versions -->
<section class="willow-global-alert willow-global-alert--positive" role="alert">
    <button class="willow-global-alert__close">Button Text</button>
    <h1 class="willow-global-alert__heading">Heading Text</h1>
    <div class="willow-global-alert__content">
        <!-- insert components here -->
    </div>
</section>

<section class="willow-global-alert willow-global-alert--warning" role="alert">
    <button class="willow-global-alert__close">Button Text</button>
    <h1 class="willow-global-alert__heading">Heading Text</h1>
    <div class="willow-global-alert__content">
        <!-- insert components here -->
    </div>
</section>

<section class="willow-global-alert willow-global-alert--negative" role="alert">
    <button class="willow-global-alert__close">Button Text</button>
    <h1 class="willow-global-alert__heading">Heading Text</h1>
    <div class="willow-global-alert__content">
        <!-- insert components here -->
    </div>
</section>
```

---

## Elements

### willow-global-alert

- Required
- Restrictions
  - Should Contain: **willow-global-alert** elements

#### _Modifiers_

`--positive`: use to give user positive feedback such as _Success Messages_

`--warning`: use to give user a warning such as _Negative Non-Error Messages_

`--negative`: use to give user negative feedback such as _Error Messages_

#### _States_

`<div class="willow-global-alert" data-global-alert-close="true">` : closes the global-alert

#### _Notes_

- **willow-global-alert** should be used only once and be placed immediately after the opening [willow-page](../page) tag or the opening `<body>` tag if not using **willow-page**. 
- **willow-global-alert** should come before the[willow-skip-nav](../skip-nav) component
- The use of `role="alert"` with the `<section>` element ensures that **willow-global-alert** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="alert">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.


---

### willow-global-alert__close

- Optional
- Restrictions
  - Should Contain: text and/or [willow-icon](../icons)

#### _Notes_

- clicking **willow-global-alert__close** (with mouse or keyboard) should toggle the close state for **willow-global-alert** and store the fact that the user dismissed the alert - so it does not continue to show on other pages

---

### willow-global-alert__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-global-alert__heading** is visible by default, and even if it is hidden it is required to meet accessibility standards
- To hide the **willow-global-alert__heading** add the `sr-only` utility class to the element

---

### willow-global-alert__content

- Required
- Restrictions
  - Should Contain: one or more components