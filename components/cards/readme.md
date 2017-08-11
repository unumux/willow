---
component: willow-card
collection: 
    - component
    - information
---
# **Willow-Card**

<!-- [Demo](http://codepen.io/team/UnumUX/pen/yMgJbb) -->

**Willow-Card** is a UI design pattern that groups related information visually, resembling a playing card, to encourage users to click or tap to view more details.

**Willow-Card** has 3 key properties:

1. Cards are used for grouping information.
1. Cards present a summary and link to additional details..
1. Cards resemble physical cards.

_Note:_ The content in a card should be kept brief. Remember a card should give just enough content to entice a user to click or tap on the card to view more. Truncating content on cards is also acceptable and is represented by adding ellipsis ("...") at the end of the content.

_Examples: Articles on a news website, products on an eCommerce site, or posts on a social app._

**Willow-Card** has two html options for providing the user an action, `<article>` and `<a>`.

- `<article>` should be used with the **willow-card__actions** element to offer buttons to the user
- `<a>` should be used to make the entire card content a clickable action. This version should **not** include the **willow-card__image** or the **willow-card__actions** elements

---

## HTML Snippet

```html
<!-- article tag version -->
<article class="willow-card">
  <div class="willow-card__image"></div>
  <div class="willow-card__content">
      <div class="willow-card__icon"></div>
      <h1 class="willow-card__heading">Heading Text</h1>
      <div class="willow-card__description">
          <!-- insert content components here -->
      </div>
      <ul class="willow-card__actions">
          <li class="willow-card__action"><!-- insert action component here --></li>
          <li class="willow-card__action"><!-- insert action component here --></li>
      </ul>
  </div>
</article>

<!-- anchor tag version -->
<a class="willow-card willow-card--link" href="" aria-label="">
  <div class="willow-card__content">
      <div class="willow-card__icon"></div>
      <h1 class="willow-card__heading">Heading Text</h1>
      <div class="willow-card__description">
          <!-- insert content components here -->
      </div>
  </div>
</a>
```

---

## Elements

### willow-card-grid

- Optional
- Restrictions
  - Should Contain: Multiple **willow-card** components

#### _Notes_

- Cards wrapped in **willow-card-grid** will take the layout of a standard grid that sets its column count based on the device/browser size.

---

#### willow-card-columns

- Optional
- Restrictions
  - Should Contain: Multiple **willow-card** components

#### _Notes_

- Cards wrapped in **willow-card-columns** will have a column layout that orders them from top to bottom and left to right.

---

### willow-card

- Required
- Restrictions
  - Should Contain: **willow-card** elements

#### _Modifiers_

`--link` : use to make the entire content area a link. _Requires use of the `<a>` html version_

#### _Notes_

- Cards created with `<a>` tags require an `href` value that triggers an action or navigation
- Cards created with `<a>` tags need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link

---

### willow-card__image

- Optional
- Restrictions
  - Should Contain: Nothing
  - Do not use with the `<a>` version of **willow-card**

#### _Notes_

- To include an image in **willow-card__image** you will need to add your own class to the element and target that in your SCSS/CSS and set the `background-image` property. Adding a new class allows the images to be different on each card. If you set the background image using the `.willow-card__image` class every card on your site will have the same image.

---

### willow-card__content

- Optional
- Restrictions
  - Should Contain:
    - **willow-card__icon** : `<article>` or `<a>` versions
    - **willow-card__heading** : `<article>` or `<a>` versions
    - **willow-card__description** : `<article>` or `<a>` versions
    - **willow-card__actions** : `<article>` version only

---

### willow-card__icon

- Optional
- Restrictions
  - Should Contain: Nothing

#### _Notes_

- To include an icon image in **willow-card__icon** you will need to add your own class to the element and target that in your SCSS/CSS and set the `background-image` property. Adding a new class allows the icon to be different on each card. If you set the background image using the `.willow-card__icon` class every card on your site will have the same icon.

---

### willow-card__heading

- Optional
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-card__heading** is visible by default and even if it is hidden, it is required to meet accessibility standards
- To hide the **willow-card__heading** add the `sr-only` utility class to the element

---

### willow-card__description

- Optional
- Restrictions
  - Should Contain: one or more components

---

### willow-card__actions

- Optional
- Restrictions
  - Should Contain: one or more **willow-card__action** elements
  - Do not use with the `<a>` version of **willow-card**

---

### willow-card__action

- Optional
- Restrictions
  - Should Contain: one _actionable_ component (such as [willow-button](../button) or a link)'
  - Do not use with the `<a>` version of **willow-card**

---

## Resources

Laubheimer, Page. "Cards: UI-Component Definition." Nielsen Norman Group. [https://www.nngroup.com/articles/cards-component/](https://www.nngroup.com/articles/cards-component/) (accessed August 7, 2017).