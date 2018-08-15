# **Willow-Button**

[Demo](https://unumux.github.io/willow-testing-site/components/buttons.html)

Buttons are used as triggers for actions. Depending on the use case, buttons contain a combination of a clear label and an icon. _Example actions may be to create, edit, delete, submit, etc._

Buttons can be created by adding the **willow-button** class to a `<button>` or `<a>` html element.

## Should I use `<button>` or `<a>`???

`<button>` should be used as a form of action for the user to provide a change or information to your app/website.
`<a>` should be used for navigation actions. Navigation means revealing or moving a user to different content.

|Use `<button>` buttons to...         |Use `<a>` buttons to...                        |
|------------------------------------ |---------------------------------------------- |
|login/logout                         |take a user to a new page                      |
|save                                 |open or closes a modal, dialog or other pop-up |
|submit                               |initiate a download                            |
|delete                               |                                               |
|cancel                               |                                               |
|reset                                |                                               |
|clear                                |                                               |

## What if my button is an action and navigation?!?!

Use a `<button>` becuase the primary purpose of these buttons is often the action (Example: **Save** and Continue in a wizard or multi-page form).

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
<button class="willow-button willow-button--ghost-inverse">Button Text</button>

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
<a href="" class="willow-button willow-button--ghost-inverse" aria-label="">Button Text</a>
```

---

## Elements

### willow-button

- Required
- Restrictions
  - Should Contain: text
- _Modifiers_

  `--primary` : use to call attention to a primary or common action such as _Learn More_

  `--positive`: use to signify a positive action such as _Submit Form_

  `--negative`: use to signify a negative action such as _Delete Account_

  `--cta` : use to emphasize a button by making it larger and the primary call to action color

  `--inline` : use to restrict a button's width based on its content

  `--ghost` : use for deemphasized actions to create a button outline that is filled with color on hover, focus and active actions

  `--ghost-inverse` : use for deemphasized actions to create a button outline that is filled with color on hover, focus and active actions

- _States_

  `<button disabled>` : disables `<button>`

  `<a data-disabled="true">` : disables `<a>` button

- _Notes_

  - Buttons created with `<a>` tags require an `href` value that triggers an action or navigation
  - Buttons created with `<a>` tags need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link

---

## [Variables](./styles/_default-variables.scss)

`$component-button-border-radius` : sets `border-radius` property on **willow-button**

`$component-button-border-color` : sets `border-color` property on **willow-button**

Default Buttons

`$component-button-background-color` : sets `background-color` property on **willow-button**

`$component-button-background-color-visited` : sets `background-color` property on **willow-button:visited**

`$component-button-background-color-hover` : sets `background-color` property on **willow-button:hover**

`$component-button-background-color-active` : sets `background-color` property on **willow-button:active**

`$component-button-background-color-focus` : sets `background-color` property on **willow-button:focus**

`$component-button-background-color-disabled` : sets `background-color` property on **willow-button[disabled]**

`$component-button-text-color` : sets `color` property on **willow-button**

`$component-button-text-color-visited` : sets `color` property on **willow-button:visited**

`$component-button-text-color-hover` : sets `color` property on **willow-button:hover**

`$component-button-text-color-active` : sets `color` property on **willow-button:active**

`$component-button-text-color-focus` : sets `color` property on **willow-button:focus**

`$component-button-text-color-disabled` : sets `color` property on **willow-button:disabled**

`$component-button-border` : sets `border` properties on **willow-button**

`$component-button-border-visited` : sets `border` properties on **willow-button:visited**

`$component-button-border-hover` : sets `border` properties on **willow-button:hover**

`$component-button-border-active` : sets `border` properties on **willow-button:active**

`$component-button-border-focus` : sets `border` properties on **willow-button:focus**

`$component-button-border-disabled` : sets `border` properties on **willow-button:disabled**

Primary Buttons

`$component-button-primary-background-color` : sets `background-color` property on **willow-button--primary**

`$component-button-primary-background-color-visited` : sets `background-color` property on **willow-button--primary:visited**

`$component-button-primary-background-color-hover` : sets `background-color` property on **willow-button--primary:hover**

`$component-button-primary-background-color-active` : sets `background-color` property on **willow-button--primary:active**

`$component-button-primary-background-color-focus` : sets `background-color` property on **willow-button--primary:focus**

`$component-button-primary-background-color-disabled` : sets `background-color` property on **willow-button--primary[disabled]**

`$component-button-primary-text-color` : sets `color` property on **willow-button--primary**

`$component-button-primary-text-color-visited` : sets `color` property on **willow-button--primary:visited**

`$component-button-primary-text-color-hover` : sets `color` property on **willow-button--primary:hover**

`$component-button-primary-text-color-active` : sets `color` property on **willow-button--primary:active**

`$component-button-primary-text-color-focus` : sets `color` property on **willow-button--primary:focus**

`$component-button-primary-text-color-disabled` : sets `color` property on **willow-button--primary[disabled]**

`$component-button-primary-border` : sets `border` property on **willow-button--primary**

`$component-button-primary-border-visited` : sets `border` property on **willow-button--primary:visited**

`$component-button-primary-border-hover` : sets `border` property on **willow-button--primary:hover**

`$component-button-primary-border-active` : sets `border` property on **willow-button--primary:active**

`$component-button-primary-border-focus` : sets `border` property on **willow-button--primary:focus**

`$component-button-primary-border-disabled` : sets `border` property on **willow-button--primary[disabled]**

Positive Buttons

`$component-button-positive-background-color` : sets `background-color` property on **willow-button--positive**

`$component-button-positive-background-color-visited` : sets `background-color` property on **willow-button--positive:visited**

`$component-button-positive-background-color-hover` : sets `background-color` property on **willow-button--positive:hover**

`$component-button-positive-background-color-active` : sets `background-color` property on **willow-button--positive:active**

`$component-button-positive-background-color-focus` : sets `background-color` property on **willow-button--positive:focus**

`$component-button-positive-background-color-disabled` : sets `background-color` property on **willow-button--positive[disabled]**

`$component-button-positive-text-color` : sets `color` property on **willow-button--positive**

`$component-button-positive-text-color-visited` : sets `color` property on **willow-button--positive:visited**

`$component-button-positive-text-color-hover` : sets `color` property on **willow-button--positive:hover**

`$component-button-positive-text-color-active` : sets `color` property on **willow-button--positive:active**

`$component-button-positive-text-color-focus` : sets `color` property on **willow-button--positive:focus**

`$component-button-positive-text-color-disabled` : sets `color` property on **willow-button--positive[disabled]**

`$component-button-positive-border` : sets `border` property on **willow-button--positive**

`$component-button-positive-border-visited` : sets `border` property on **willow-button--positive:visited**

`$component-button-positive-border-hover` : sets `border` property on **willow-button--positive:hover**

`$component-button-positive-border-active` : sets `border` property on **willow-button--positive:active**

`$component-button-positive-border-focus` : sets `border` property on **willow-button--positive:focus**

`$component-button-positive-border-disabled` : sets `border` property on **willow-button--positive[disabled]**

Negative Buttons

`$component-button-negative-background-color` : sets `background-color` property on **willow-button--negative**

`$component-button-negative-background-color-visited` : sets `background-color` property on **willow-button--negative:visited**

`$component-button-negative-background-color-hover` : sets `background-color` property on **willow-button--negative:hover**

`$component-button-negative-background-color-active` : sets `background-color` property on **willow-button--negative:active**

`$component-button-negative-background-color-focus` : sets `background-color` property on **willow-button--negative:focus**

`$component-button-negative-background-color-disabled` : sets `background-color` property on **willow-button--negative[disabled]**

`$component-button-negative-text-color` : sets `color` property on **willow-button--negative**

`$component-button-negative-text-color-visited` : sets `color` property on **willow-button--negative:visited**

`$component-button-negative-text-color-hover` : sets `color` property on **willow-button--negative:hover**

`$component-button-negative-text-color-active` : sets `color` property on **willow-button--negative:active**

`$component-button-negative-text-color-focus` : sets `color` property on **willow-button--negative:focus**

`$component-button-negative-text-color-disabled` : sets `color` property on **willow-button--negative[disabled]**

`$component-button-negative-border` : sets `border` property on **willow-button--negative**

`$component-button-negative-border-visited` : sets `border` property on **willow-button--negative:visited**

`$component-button-negative-border-hover` : sets `border` property on **willow-button--negative:hover**

`$component-button-negative-border-active` : sets `border` property on **willow-button--negative:active**

`$component-button-negative-border-focus` : sets `border` property on **willow-button--negative:focus**

`$component-button-negative-border-disabled` : sets `border` property on **willow-button--negative[disabled]**

Ghost Button

`$component-button-ghost-background-color` : sets `background-color` property on **willow-button--ghost**

`$component-button-ghost-background-color-visited` : sets `background-color` property on **willow-button--ghost:visited**

`$component-button-ghost-background-color-hover` : sets `background-color` property on **willow-button--ghost:hover**

`$component-button-ghost-background-color-active` : sets `background-color` property on **willow-button--ghost:active**

`$component-button-ghost-background-color-focus` : sets `background-color` property on **willow-button--ghost:focus**

`$component-button-ghost-background-color-disabled` : sets `background-color` property on **willow-button--ghost[disabled]**

`$component-button-ghost-text-color` : sets `color` property on **willow-button--ghost**

`$component-button-ghost-text-color-visited` : sets `color` property on **willow-button--ghost:visited**

`$component-button-ghost-text-color-hover` : sets `color` property on **willow-button--ghost:hover**

`$component-button-ghost-text-color-active` : sets `color` property on **willow-button--ghost:active**

`$component-button-ghost-text-color-focus` : sets `color` property on **willow-button--ghost:focus**

`$component-button-ghost-text-color-disabled` : sets `color` property on **willow-button--ghost[disabled]**

`$component-button-ghost-border` : sets `border` property on **willow-button--ghost**

`$component-button-ghost-border-visited` : sets `border` property on **willow-button--ghost:visited**

`$component-button-ghost-border-hover` : sets `border` property on **willow-button--ghost:hover**

`$component-button-ghost-border-active` : sets `border` property on **willow-button--ghost:active**

`$component-button-ghost-border-focus` : sets `border` property on **willow-button--ghost:focus**

`$component-button-ghost-border-disabled` : sets `border` property on **willow-button--ghost[disabled]**

Inverse Ghost Button

`$component-button-ghost-inverse-background-color` : sets `background-color` property on **willow-button--ghost-inverse**

`$component-button-ghost-inverse-background-color-visited` : sets `background-color` property on **willow-button--ghost-inverse:visited**

`$component-button-ghost-inverse-background-color-hover` : sets `background-color` property on **willow-button--ghost-inverse:hover**

`$component-button-ghost-inverse-background-color-active` : sets `background-color` property on **willow-button--ghost-inverse:active**

`$component-button-ghost-inverse-background-color-focus` : sets `background-color` property on **willow-button--ghost-inverse:focus**

`$component-button-ghost-inverse-background-color-disabled` : sets `background-color` property on **willow-button--ghost-inverse[disabled]**

`$component-button-ghost-inverse-text-color` : sets `color` property on **willow-button--ghost-inverse**

`$component-button-ghost-inverse-text-color-visited` : sets `color` property on **willow-button--ghost-inverse:visited**

`$component-button-ghost-inverse-text-color-hover` : sets `color` property on **willow-button--ghost-inverse:hover**

`$component-button-ghost-inverse-text-color-active` : sets `color` property on **willow-button--ghost-inverse:active**

`$component-button-ghost-inverse-text-color-focus` : sets `color` property on **willow-button--ghost-inverse:focus**

`$component-button-ghost-inverse-text-color-disabled` : sets `color` property on **willow-button--ghost-inverse[disabled]**

`$component-button-ghost-inverse-border` : sets `border` property on **willow-button--ghost-inverse**

`$component-button-ghost-inverse-border-visited` : sets `border` property on **willow-button--ghost-inverse:visited**

`$component-button-ghost-inverse-border-hover` : sets `border` property on **willow-button--ghost-inverse:hover**

`$component-button-ghost-inverse-border-active` : sets `border` property on **willow-button--ghost-inverse:active**

`$component-button-ghost-inverse-border-focus` : sets `border` property on **willow-button--ghost-inverse:focus**

`$component-button-ghost-inverse-border-disabled` : sets `border` property on **willow-button--ghost-inverse[disabled]**

