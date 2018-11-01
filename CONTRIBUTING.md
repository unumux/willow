# Contributing

## Global dependencies you need to work on Willow

To work on Willow install these global packages:

- [Commitizen CLI](https://github.com/commitizen/cz-cli) : `npm install -g commitizen`

## Working on Willow

1. Get the latest version of Willow:
    - Pull the latest version of Willow from Github
        - From the Willow directory in terminal
        - Run `git pull`
    - Make a new branch from the develop branch
        - From the Willow directory in terminal
            - Run `git checkout develop`
            - Run `git checkout -b [branch-name]` - replace [branch-name] with something that describes the work you're going.
    - On your new branch run `npm install`

2. Get the latest version of the [example project](https://github.com/unumux/willow-testing-site) (used for testing):
    - Clone or get the latest version of the example project from Github
        - From the example project directory in terminal
        - Run `git clone` or `git pull`
    - Make a new branch from the master branch
        - From the example project directory in terminal
            - Run `git checkout -b [branch-name]` - replace [branch-name] with something that describes the work you're going.
    - On your new branch run `npm install`

3. Linking the local Willow and [example project](https://github.com/unumux/willow-testing-site) with [npm link](https://docs.npmjs.com/cli/link)
    - From the Willow directory in terminal run `npm link`
    - From the example project directory in terminal run `npm link @unumux/willow`
    - To check that `npm link` worked
        - Open the local copy of Willow in a code editor
            - Edit the root style file (`willow/styles/styles.scss`). We suggest an obvious change like:
            ```SCSS
                * {
                    color: red;
                }
            ```
        - Open the example project in a code editor
            - Navigate through the node_modules to the `<example-project>/node_modules/@unumux/willow/styles` folder
            - Look at the style file (`node_modules/@unumux/Willow/styles/styles.scss`) and you should see the new styles you added.
        - Or if you're running the build process on the example project (and it compiled) you should see the changes in your browser after you refresh.
            - Pro Tip: if you don't want to refresh the browser after every Willow change try adding the Willow files you're changing to the watch list of your example project's build.

4. Commit and push your Willow work
    - Do your work: Work in Willow should consist of `SCSS` code and/or documentation.
    - Stage your work using `git add`
    - Commit your work using `git cz`
        - Wait, what's `git cz` you say?
        - `git cz` runs commitizen which is used in Willow to standardize our commit messages.
        - Willow uses [AngularJS's commit message convention](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)
        - This command will prompt you with a number of questions you need to answer
            - Type of change you've made - Choose from a list of pre-defined types
            - Scope of the work - One-word to define where the work was done, use `*` if there are multiple scopes
            - Short Description - Limited to 72 characters. No capital letters. [Impreative tense](https://en.wikipedia.org/wiki/Imperative_mood). Example: Update banner text styles
            - Long Description
            - Are there any breaking changes?
            - Does this commit close an issue on Github?
    - After answering the commit questions your answers will be reviewed to make sure they pass. If that fails read the error provided and run `git cz` again. If the commit passes move on to pushing.
    - Push your work with `git push -u origin <branch-name>`
    - Create a pull request in Github to merge your branch into the develop branch
        - Consider assigning a reviewer from the Unum UX team
    - Wait for review

5. Commit and push your Example Site work
    - Make sure you are on the new branch you created as a part of step 1 above
    - Do your work: The work in the example site will consist of `html` for the components you make or edit.
    - Stage your work using `git add`
    - Commit your work using `git commit -m "<Insert your message here>"`
        - Wait, where's commitizen?
        - The example project does not use commitizen to standardize commits...yet.
        - So you don't have to answer all those questions for this one
    - Push your work with `git push -u origin <branch-name>`
    - Create a pull request in Github to merge your branch into the master branch
        - Consider assigning a reviewer from the Unum UX team
    - Wait for review

## Reviewing Pull Requests

1. Review the pull request in Github first as their tools for comparing changes are pretty great.
    - For Willow: compare incoming feature branches to the develop branch.
    - For the example project: compare incoming updates to master

2. Get the latest version of Willow
    - From the Willow directory in terminal
    - Run `git pull`
    - Checkout the branch you need to review with `git checkout [the-branch-you-are-reviewing]`
    - Merge the contents from the develop branch into this with `git merge develop`
    - Run `npm install`

3. Get the latest version of the [example project](https://github.com/unumux/willow-testing-site) (used for testing):
    - Clone or get the latest version of the example project from Github
        - From the example project directory in terminal
        - Run `git clone` or `git pull`
    - Make a new branch from the master branch
        - From the example project directory in terminal
            - Run `git checkout -b [branch-name]` - replace [branch-name] with something that describes the work you're going.
    - On your new branch run `npm install`

4. Link the local Willow and [example project](https://github.com/unumux/willow-testing-site) with [npm link](https://docs.npmjs.com/cli/link)
    - From the Willow directory in terminal run `npm link`
    - From the example project directory in terminal run `npm link @unumux/willow` then start the build with `ux` or `npm start`
        - This shows you the example project with the willow code from the develop branch and the 

    - You may need to add code to the example project if the contrivu

    - Other tips about testing:
      - If you're making a new component, the `html` for the component should go in the example project and the styles will go in the local copy of Willow.
      - If you're editing a component, same thing above applies. Make your `html` changes in the exapmple project, make style edits in the local copy of Willow.


- Test it on the willow-testing-site project
- Create a Pull Request to Master
- Get someone to merge that
- Pull the latest version of the Master branch
- In terminal run `npm publish`

## Stylelint info

- Willow will install stylelint from npm when you run `npm install`
- Willow comes with a `.stylelintrc` config file. This file extends the stylelinting standards of the Unum UX team found in the [stylelint-config-unumux package](https://www.npmjs.com/package/@unumux/stylelint-config-unumux)

## Random notes

- run semantic-release-cli on willow repo
- install sem-release
- update package.json text and exit line
- add commitizen config to package.json
- update travis.yml to node 9