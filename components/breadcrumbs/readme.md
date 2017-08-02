---
component: willow-breadcrumb
collection: 
    - component
    - navigation
permalink: false
---
# **Willow-Breadcrumb**

[Demo](http://codepen.io/team/UnumUX/pen/aJpbyK)

Breadcrumbs are a specialized secondary navigation that show users their location within a section of the website. The purpose is to plot the user's path back to their starting point. Breadcrumbs are typically used when there is a large volume of organized content.

---

## HTML Snippet

```html
<nav class="willow-breadcrumbs" role="navigation" aria-label="breadcrumb">
    <h1 class="willow-breadcrumbs__heading sr-only">You are here:</h1>
    <ol class="willow-breadcrumbs__list">
        <li class="willow-breadcrumbs__item"><a class="willow-breadcrumbs__link" href="" aria-label="">Nav Item 1</a></li>
        <li class="willow-breadcrumbs__item"><a class="willow-breadcrumbs__link" href="" aria-label="">Nav Item 2</a></li>
        <li class="willow-breadcrumbs__item willow-breadcrumbs__item--active">Current Item</li>
    </ol>
</nav>
```

---

## Elements

### willow-breadcrumbs

- Required
- Restrictions
  - Should Contain: **willow-breadcrumbs** elements

#### _Notes_

- The use of `role="navigation"` with the `<nav>` element ensures that **willow-breadcrumbs** is accessible for user agents that do not support HTML5. The use of both `<nav>` and `<role="navigation">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-breadcrumbs__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-breadcrumbs__heading** is hidden by default with the `sr-only` utility class, and is required to meet accessibility standards

---

### willow-breadcrumbs__list

- Required
- Restrictions
  - Should Contain: one or more **willow-breadcrumbs_item** elements

#### _Notes_

- The order of items in **willow-breadcrumbs__list** is important, so the list is marked up as an `<ol>` element

---

### willow-breadcrumbs__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one **willow-breadcrumbs__link** element

#### _Modifiers_

`--active` : identifies the current item

#### _Notes_

- If a **willow-breadcrumbs__item** is a previous page it should contain an `<a>` link, if it is the current page then it should contain text and its class appended with the `--active` modifier

---

### willow-breadcrumbs__link

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-breadcrumbs__link** elements require an `href` value that links to the page they reference
- **willow-breadcrumbs__link** elements need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link