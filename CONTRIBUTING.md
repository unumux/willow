---
title: Contributing
collection: 
    - index
    - contributing
permalink: false
---
# Contributing to Willow UI Components

Willow is an open-source library being created and maintained by a small team, so any support you want to give by contributing new components, enhancing existing components or adding to documentation are very welcome.

## Table of Contents

- [Submitting Issues](#submitting-issues)
- [Contributing](#contributing)
- [Willow Structure Guide](#willow-structure-guide)

## Submitting Issues

Issues should be created when you find a bug with the project or when you have an enhancement idea you want the Willow team to consider implementing.

- Create an [issue](https://help.github.com/articles/creating-an-issue/)
- Make sure your issue is detailed and covers the following if applicable
  - Expected Behavior
  - Actual Behavior
  - Desired Behavior
  - Steps taken to cause unexpected behavior
  - Version of Willow being used

## Contributing

You can contribute directly to the repo if you find a bug you want to fix, if you want to add or enhance a component or if you want to add to the documentation.

1. [Fork](https://help.github.com/articles/fork-a-repo/) this repo into your local git
1. Create your feature branch (`git checkout -b branch-name`)
   - we recommend a branch name that describes what you're adding (create-card-component)
1. Make your changes
1. Add and Commit your changes (`git add .` then `git commit -m "Adds a feature that does..."`)
1. Push to the branch (`git push origin branch-name`)
1. Create a new [Pull Request]("https://help.github.com/articles/creating-a-pull-request/") with notes about your changes
1. Pull requests will be reviewed and may be accepted by the Willow team

## Willow SCSS Structure Guide

The following scss structure and practices are required if you create a new components to contribute.

Understanding the following structure and practices is also helpful when trying to update an existing component.

### Directory Structure

Each components has a folder. All component folders are kept in the components folder.

```
willow/
|
|-- components/
|   |-- component-one/
|       |-- _component-one.scss
|       |-- _element-one.scss
|       |-- _element-two.scss
|
|   |-- component-two/
|       |-- _component-two.scss
|       |-- _element-one.scss
|       |-- _element-two.scss
```

### SCSS File Specifics

- There is a scss partial file for each element in a component - the block and it's sub-elements.

- All partials should contain a 'base' mixin for main styles for that element.

- This allows the styles to be repeated in modified versions of that element.

- Modifiers for an element should be included within the element's selector.

- Sub-elements have their own partials and those are imported inside the main component selector in the index partial

```scss
// component-one/_component-one.scss
    @mixin base() {
        background-color: white;
        color: black;
    }

    .component-one {
        @include base;

        // this element has a modified version
        &--modifier {
            @include base;
            color: blue;
        }

        // import component's sub-element partials here
        @import "element-name-one";
        @import "element-name-two";
    }
```

- Main styles for sub-elements go in a 'base' mixin

- Sub-Element modifiers are also in the element partial

```scss
// component-one/_element-one.scss
    @mixin base() {
        color: blue;
        text-decoration: none;
    }

    &__element-one {
        @include base;

        &--modifier {
            @include base;
            color: green;
        }
    }
```

- If modifying the main component affects the styling of a contained sub-element use the following syntax in the element partial

```scss
// component-one/_element-one.scss
    &__element-one {
        color: white;

        // when __element-one is inside of component-one--modified
        // it should be yellow because of its parent's modified state.
        .component-one--modified & {
            color: yellow;
        }
    }
```

- If modifying the main component affects styling of a modified contained element use the following syntax in the element partial

```scss
// component-one/_element-one.scss
    &__element-one {
        color: white;

        &--modified {
            color: blue;

            .component-one--modified & {
                color: red;
            }
        }
    }
```