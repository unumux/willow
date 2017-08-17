---
component: willow-button
collection: 
    - component
    - action
---
# **Willow-Button**

[Demo](http://codepen.io/team/UnumUX/pen/BWpzLa)

Buttons are used as triggers for actions. Depending on the use case, buttons contain a combination of a clear label and an icon. _Example actions may be to create, edit, delete, submit, etc._

Buttons can be created by adding the **willow-button** class to a `<button>` or `<a>` html element.

- `<button>` should be used as a form of action for the user to accomplish something
- `<a>` should be used as a form of action for the user to go somewhere

---

## HTML Snippet

```html
<!-- button tag version -->
<button class="willow-button">Button Text</button>
<!-- button tag disabled -->
<button class="willow-button" disabled>Disabled Button Text</button>
<!-- button tag modified versions -->
<button class="willow-button willow-button--primary">Button Text</button>
<button class="willow-button willow-button--positive">Button Text</button>
<button class="willow-button willow-button--negative">Button Text</button>
<button class="willow-button willow-button--cta">Button Text</button>
<button class="willow-button willow-button--inline">Button Text</button>
<button class="willow-button willow-button--ghost">Button Text</button>
<button class="willow-button willow-button--ghost-secondary">Button Text</button>

<!-- anchor tag version -->
<a href="" class="willow-button" aria-label="">Button Text</a>
<!-- anchor tag disabled -->
<a href="" class="willow-button" data-disabled="true" aria-disabled="true" aria-label="">Disabled Button Text</a>
<!-- anchor tag modified versions -->
<a href="" class="willow-button willow-button--primary" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--positive" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--negative" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--cta" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--inline" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--ghost" aria-label="">Button Text</a>
<a href="" class="willow-button willow-button--ghost-secondary" aria-label="">Button Text</a>
```

---

## Elements

### willow-button

- Required
- Restrictions
  - Should Contain: text

#### _Modifiers_

`--primary` : use to call attention to a primary or common action such as _Learn More_

`--positive`: use to signify a positive action such as _Submit Form_

`--negative`: use to signify a negative action such as _Delete Account_

`--cta` : use to emphasize a button by making it larger and the primary call to action color

`--inline` : use to restrict a button's width based on its content

`--ghost` : use on a dark-colored background for a deemphasized action

`--ghost-secondary` : use on a dark-colored background for a secondary deemphasized action

#### _States_

`<button disabled>` : disables `<button>`

`<a data-disabled="true">` : disables `<a>` button

#### _Notes_

- Buttons created with `<a>` tags require an `href` value that triggers an action or navigation
- Buttons created with `<a>` tags need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link