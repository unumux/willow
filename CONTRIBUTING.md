# Contributing and Maintaining

Willow is an NPM package made up of SCSS code. So to work on Willow you may need to put component HTML in another project, import your copy of Willow as a package and compile that project to see how the component looks. In the following instructions we assume you will need an example project for testing, so we walk you through how to use the one we made for you.  

There are times when you may not need to make changes to the example projcect or use it for testing, in those cases just skip the instructions related to the example project.

Ok here we go...

## Global dependencies you need to work on Willow

To work on Willow install these global packages:

- [Commitizen CLI](https://github.com/commitizen/cz-cli) : `npm install -g commitizen`

## Working on Willow

1. Get the latest version of Willow:
    - Pull the latest version of Willow from Github
        - From the Willow directory in terminal
        - Run `git pull`
    - Make a new branch from the Develop branch
        - From the Willow directory in terminal
            - Run `git checkout develop`
            - Run `git checkout -b [branch-name]` - replace [branch-name] with something that describes the work you're going
    - On your new branch run `npm install`

2. Get the latest version of the [example project](https://github.com/unumux/willow-testing-site) (used for testing):
    - Clone or get the latest version of the example project from Github
        - From the example project directory in terminal
        - Run `git clone` or `git pull`
    - Make a new branch from the Master branch
        - From the example project directory in terminal
            - Run `git checkout -b [branch-name]` - replace [branch-name] with something that describes the work you're going
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
    - Do your work: Work in Willow should consist of `SCSS` code and/or documentation
    - Stage your work using `git add`
    - Commit your work using `git cz`
        - Wait, what's `git cz` you say?
        - `git cz` runs commitizen which is used in Willow to standardize our commit messages
        - Willow uses [AngularJS's commit message convention](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)
        - This command will prompt you with a number of questions you need to answer
            - Type of change you've made - Choose from a list of pre-defined types
            - Scope of the work - One-word to define where the work was done, use `*` if there are multiple scopes
            - Short Description - Limited to 72 characters. No capital letters. [Imperative tense](https://en.wikipedia.org/wiki/Imperative_mood). Example: update banner text styles
            - Long Description
            - Are there any breaking changes?
            - Does this commit close an issue on Github?
    - After answering the commit questions your answers will be reviewed to make sure they pass. If that fails read the error provided and run `git cz` again. If the commit passes move on to pushing
    - Push your work with `git push -u origin <branch-name>`
    - Create a pull request in Github to merge your branch into the Develop branch
        - Consider assigning a reviewer from the Unum UX team
    - Wait for review

5. Commit and push your Example Site work
    - Make sure you are on the new branch you created as a part of step 1 above
    - Do your work: The work in the example site will consist of `html` for the components you make or edit
    - Stage your work using `git add`
    - Commit your work using `git commit -m "<Insert your message here>"`
        - Wait, where's commitizen?
        - The example project does not use commitizen to standardize commits...yet
        - So you don't have to answer all those questions for this one
    - Push your work with `git push -u origin <branch-name>`
    - Create a pull request in Github to merge your branch into the Master branch
        - Consider assigning a reviewer from the Unum UX team
    - Wait for review

## Maintainers: Reviewing pull requests

1. Review the pull request in Github first as their tools for comparing changes are pretty great
    - For Willow: compare incoming feature branches to the Develop branch
    - For the example project: compare incoming updates to the Master branch

2. Get the latest version of Willow
    - From the Willow directory in terminal
    - Run `git pull`
    - Checkout the branch you need to review with `git checkout [the-branch-you-are-reviewing]`
    - At this point you can merge the contents from the Develop branch into this new branch with `git merge develop`
        - If the contributor started from the Develop branch you won't need to do this. Or there may be times that you want to test the new branch first and then merge in Develop later.  So play this part by ear but keep it in mind.
    - Run `npm install`

3. Get the latest version of the [example project](https://github.com/unumux/willow-testing-site) (used for testing):
    - Clone or get the latest version of the example project from Github
        - From the example project directory in terminal
        - Run `git clone` or `git pull`
    - Make a new branch from the Master branch
        - From the example project directory in terminal
            - Run `git checkout -b [branch-name]` - Replace [branch-name] with something that describes the work you're goin
    - On your new branch run `npm install`

4. Link the local Willow and [example project](https://github.com/unumux/willow-testing-site) with [npm link](https://docs.npmjs.com/cli/link)
    - From the Willow directory in terminal run `npm link`
    - From the example project directory in terminal run `npm link @unumux/willow` then start the build with `ux` or `npm start`
    - Keep in mind: If the contributor did not create a pull request for the example project, you may need to add code to that project to test the work in Willow
    - Test the work on multiple devices and browsers and at multiple widths
    - Post comments or requests for changes in the pull request on Github
    - After the code is tested and ready to be merged approve the review in Github
    - Merge the pull request and then delete the new branch that was created

5. Continue through the Build and Pushing to Master sections below

## Maintainers: Builds

Willow uses [Travis CI](https://travis-ci.org/) to run a build, run [semantic-release](https://github.com/semantic-release/semantic-release) and publish new versions of Willow to NPM if necessary.

This build is triggered every time pull request is merged. However, only merges to the Master branch will cause a new package release to be pushed to NPM.

On Github, in a Willow pull request, there will be a section that shows the checks (build) taking place. There are indicators here that will start yellow and then turn green or red depending on if the build passes or fails. If you have access to the UnumUX Travis CI group you can use the details link here to view the full build log on the Travis site. This log is helpful when the build fails.

## Maintainers: Pushing to Master

After work from a new/feature branch is merged into the Develop branch, it's time to merge Develop into Master.
You do this by opening a pull request like you did in the above steps, but this time you set the branch to pull the work on the Develop branch into the work on the Master branch.

After opening the pull request for Develop to Master you will see the checks running, watch those to make sure the build does not fail.

Now another maintainer is needed to complete this pull request with a review and merger of the branches. Once that is complete the builds will fully run and a new version of Willow will be released to NPM*.

*Willow uses Semantic-Release to analyze the commit messages and determine what the new version number for Willow should be. So there is no need to update that pesky number in the package.json file ever! 

## Stylelint info

- Willow will install stylelint from npm when you run `npm install`
- Willow comes with a `.stylelintrc` config file. This file extends the stylelinting standards of the Unum UX team found in the [stylelint-config-unumux package](https://www.npmjs.com/package/@unumux/stylelint-config-unumux)
