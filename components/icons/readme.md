---
component: willow-icon
collection:
    - component
---
# **Willow-Icon**

[Demo](http://codepen.io/team/UnumUX/pen/gmXRWg)

**Willow-Icons** are symbols that can be used to convey information and help users comprehend directions, actions, messages and interfaces.

**Willow-Icons** can placed inside a piece of content or an actionable component or element.

When placed in content **Willow-Icons** serve as a decorative item to enhance the message but they are not required for the user to understand the message. _Example: An error message includes a "!" icon at the beginning of the message._

When **Willow-Icons** are used inside of actionable components or elements, such as [willow-button](../button) or a link, they can be used to convey meaning instead of being only decorative. _Example: A close button that does not include the word close, but only an "X" icon._ When used this way, extra steps are required to ensure the meaning is conveyed to user's that use assistive technologies such as screen readers.

---

## HTML Snippet

```html
<!-- modified versions -->
<span class="willow-icon willow-icon--menu"></span>
<span class="willow-icon willow-icon--menu-inverse"></span>
<span class="willow-icon willow-icon--menu-close"></span>
<span class="willow-icon willow-icon--menu-close-inverse"></span>
<span class="willow-icon willow-icon--close"></span>
<span class="willow-icon willow-icon--close-inverse"></span>
<span class="willow-icon willow-icon--info"></span>
<span class="willow-icon willow-icon--info-inverse"></span>
<span class="willow-icon willow-icon--success"></span>
<span class="willow-icon willow-icon--success-inverse"></span>
<span class="willow-icon willow-icon--warning"></span>
<span class="willow-icon willow-icon--warning-inverse"></span>
<span class="willow-icon willow-icon--error"></span>
<span class="willow-icon willow-icon--error-inverse"></span>
```

---

## Elements

### willow-icon

- Required
- Restrictions
  - Should Contain: nothing
  - Must have a modifier added to class name

#### _Modifiers_

`--menu` : displays a collapsed menu icon often called a hamburger

`--menu-inverse` : same as `--menu` but in an inverse color

`--menu-close` : displays a close icon that should only be used on menus

`--menu-close-inverse` : same as `--menu-close` but in an inverse color

`--close` : displays a close icon for global alerts and dialogs

`--close-inverse` : same as `--close` but in an inverse color

`--info` : displays an information or i symbol to mark something for consideration

`--info-inverse` : same as `--info` but in an inverse color

`--success` : displays a checkmark to signify success or completion

`--success-inverse` : same as `--success` but in an inverse color

`--warning` : displays a yield symbol to signify something that needs attention

`--warning-inverse` : same as `--warning` but in an inverse color

`--error` : displays an exclamation point icon to signify an error

`--error-inverse` : same as `--error` but in an inverse color

#### _Notes_

- **willow-icon** requires the addition of a modifier or no icon will appear
- if used to convey meaning in side of an actionable component or element, the `title` attribute should be added to the icon element and given a value to explain the purpose. `<button><span class="willow-icon--menu-close" title="Close Menu"></span></button>`