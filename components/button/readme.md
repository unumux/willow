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

#### _Modifiers_

`--primary` : use to call attention to a primary or common action such as _Learn More_

`--positive`: use to signify a positive action such as _Submit Form_

`--negative`: use to signify a negative action such as _Delete Account_

`--cta` : use to emphasize a button by making it larger and the primary call to action color

`--inline` : use to restrict a button's width based on its content

`--ghost` : use for deemphasized actions to create a button outline that is filled with color on hover, focus and active actions

`--ghost-inverse` : use for deemphasized actions to create a button outline that is filled with color on hover, focus and active actions

#### _States_

`<button disabled>` : disables `<button>`

`<a data-disabled="true">` : disables `<a>` button

#### _Notes_

- Buttons created with `<a>` tags require an `href` value that triggers an action or navigation
- Buttons created with `<a>` tags need an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link

---

## Mixins

**willow-button** uses the `set-button-style` mixin to apply styles to a button based on the button type ($modifier) and $state (ie. hover, focus, active, visited).

[See the `set-button-style` details](../../utilities.md#set-button-stylemodifier-state)

---

## [Variables](./styles/_default-variables.scss)

**willow-button** variables exist for each button type (default, primary, positive, negative, ghost, ghost-inverse), and for each state within each button type (default, visited, hover, active, focus, disabled). So there are a lot of button variables.

To keep styles concise, a [variable map](./styles/_variable-maps.scss) organizes button variables into groups based on button type and the `set-button-style` mixin is used in the button SCSS files to get variables from this map and set them to the correct style property.

### Variables for all buttons:

- `$component-button-border-radius` : sets `border-radius` property on **willow-button**
- `$component-button-border-color` : sets `border-color` property in the `$component-button-border` variable

### Variables for the default button:

`background-color` property

- `$component-button-background-color` : set on **willow-button**
- `$component-button-background-color-visited` : set on **willow-button:visited**
- `$component-button-background-color-hover` : set on **willow-button:hover**
- `$component-button-background-color-active` : set on **willow-button:active**
- `$component-button-background-color-focus` : set on **willow-button:focus**
- `$component-button-background-color-disabled` : set on **willow-button[disabled]**

`color` property

- `$component-button-text-color` : set on **willow-button**
- `$component-button-text-color-visited` : set on **willow-button:visited**
- `$component-button-text-color-hover` : set on **willow-button:hover**
- `$component-button-text-color-active` : set on **willow-button:active**
- `$component-button-text-color-focus` : set on **willow-button:focus**
- `$component-button-text-color-disabled` : set on **willow-button:disabled**

`border` properties

- `$component-button-border` : set on **willow-button**
- `$component-button-border-visited` : set on **willow-button:visited**
- `$component-button-border-hover` : set on **willow-button:hover**
- `$component-button-border-active` : set on **willow-button:active**
- `$component-button-border-focus` : set on **willow-button:focus**
- `$component-button-border-disabled` : set on **willow-button:disabled*

### Variables for other types of buttons will follow this naming convention:

`$component-button-[type name]-[property-name]-[state]`

Examples:

- `$component-button-primary-background-color`
- `$component-button-positive-background-color:visited`
- `$component-button-negative-background-color:focus`

Find the full list of **willow-button** variables [here](./styles/_default-variables.scss).
