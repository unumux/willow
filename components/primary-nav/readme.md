---
component: willow-primary-nav
collection: 
    - component
    - navigation
---
# **Willow-Primary-Nav**

[Demo](http://codepen.io/team/UnumUX/pen/gmgMxY)

Primary Navigation is meant to move the user to primary sections of the website or app. It should reside within the [willow-page-header](../page-header) component by default. This navigation should take precedence over any other forms of navigation on the page. Links in the primary navigation should not be a repeat of secondary navigation.

Primary Nav should contain a limited number of items, the shorter the better for the user.

---

## HTML Snippet

```html
<nav class="willow-primary-nav" role="navigation" aria-label="Primary Navigation">
    <h1 class="willow-primary-nav__heading">Primary Navigation</h1>
    <ul class="willow-primary-nav__list">
        <li class="willow-primary-nav__item"><a class="willow-primary-nav__link" href="" aria-label="">Menu Item 1</a></li>
        <li class="willow-primary-nav__item"><a class="willow-primary-nav__link" href="" aria-label="">Menu Item 2</a></li>
        <li class="willow-primary-nav__item"><a class="willow-primary-nav__link" href="" aria-label="">Menu Item 3</a></li>
    </ul>
</nav>
```

---

## Elements

### willow-primary-nav

- Required
- Restrictions
  - Should Contain: **willow-primary-nav** elements

#### _Notes_

- **willow-primary-nav** has a `role="navigation"` for accessibility

---

### willow-primary-nav__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-primary-nav__heading** is hidden by default, and is required to meet accessibility standards

---

### willow-primary-nav__list

- Required
- Restrictions
  - Should Contain: one or more **willow-primary-nav__item**

---

### willow-primary-nav__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one **willow-primary-nav__link**

---

### willow-primary-nav__link

- Required
- Restrictions
  - Should Contain: text

#### _Modifiers_

`--active` : visibly identifies the current selected item

#### _Notes_

- **willow-primary-nav__link** requires an `href` that links to the pages they reference
- **willow-primary-nav__link** elements need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link