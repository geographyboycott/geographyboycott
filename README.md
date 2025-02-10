# GEOGRAPHERS FOR JUSTICE IN PALESTINE

this is the repository for **geographers for justice in palestine**. it's built in [Hugo](https://gohugo.io/documentation/) and forked from the [Dot Org theme](https://github.com/cncf/dot-org-hugo-theme) (see here for an [example site of features in the Dot Org theme](https://dot-org-hugo-theme-demo.netlify.app/faq/)).

## MAKE EDITS THROUGH THE GITHUB REPOSITORY

changes to site content can be made directly through the github repository. note that in order to do this, you must 1) have a github account and 2) accept the invitation to edit the repository.

to make edits through the repository:

1. make sure you switch to the `staging` branch, rather than the `main` branch, of the `geographyboycott` repository
2. click into the `content/en` directory
3. click into a directory that corresponds with the page that you'd like to edit (e.g., `preconference`)
4. click the `_index.md` file in that directory
5. click the 'edit' button at the top-right hand corner of the window
6. make your changes, adhering to [Markdown syntax](https://www.markdownguide.org/cheat-sheet/)
7. save by clicking the green "Commit changes..." button, including a description of what you edited

NOTE: if you are making edits to the `aag/sessions` page:
1. instead of clicking into `content/en`, you should click into `data`
2. then open `aag2025.yaml`
3. you can edit the content for this page from the YAML file
4. refer to [this page](https://yaml.org/) for an explainer on the YAML markup language (which is short for "**Y**et **A**nother **M**arkup **L**anguage" 🫠)

## DEVELOP LOCALLY FOR MORE COMPLEX EDITS

to develop locally:

1. ensure you have installed the latest version of [Hugo](https://gohugo.io/)
2. clone the repository
3. via your terminal, `cd` into it
4. from inside the repo, `npm install`
5. get on the staging branch with `git checkout staging`---this is important! never work on the `main` branch! only merge into the `main` branch after staged edits have been approved :)
6. to serve a hot reload, `hugo server`

IMPORTANT: every time you run `hugo server`, a new CSS file is created in the `public` directory. i'm not sure why this is happening, but to make sure the site stays tidy, always delete the contents of the public CSS folder and then run `hugo build` before you push any changes up to the source

## BUILD CHAIN

the site builds from the `main` branch, via a custom GitHub action, and deploys at http://geog4pal.org. every time you push a commit to the `main` branch, the site will automatically rebuild. as is standard in Hugo sites, the site deploys from the `public` directory. see below for instructions on:

- [how to stage edits for the site](#staging-updates-to-the-site)
- [reviewing and approving staged edits](#reviewing-and-approving-staged-edits)

## STAGING UPDATES TO THE SITE

when we need to make changes to the site, we will always use the `staging` branch to stage any edits. NEVER commit directly to `main`

to stage edits:

1. `cd` into your copy of the site repo
2. ensure you are on the `staging` branch with `git checkout staging`
3. ensure you're up to date with the latest site changes with `git pull`
4. make your changes
5. when you're ready to commit, exit the hot reload with `ctrl+c`
6. clean the `public` directory by deleting all the CSS
7. run `hugo build`
8. if you're ready for your changes to be reviewed, you can commit & push changes to the `staging` branch

## REVIEWING AND APPROVING STAGED EDITS

we will follow a standard [pull request-merge](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request) workflow where we get approval from one another before pushing any changes to the site. here's how it will work.

when you are ready to make an edit:

1. follow instructions for [staging updates to the site](#staging-updates-to-the-site) and ensure you've pushed your changes to the `staging` branch
2. on the GitHub source code repository, in the `geographyboycott` repo, toggle to the [staging branch](https://github.com/geographyboycott/geographyboycott/tree/staging)
3. open a pull request by clicking the "Pull Request" tab => "New Pull Request"
4. tag somebody to review it
5. the other person will approve its merge into the `main` branch, which triggers the GitHub action that redeploys the site to production at geog4pal.org

#### TODO

[] fix `npm run build` and `npm run dev`---these are supposed to work! but they don't! and it's got something to do with `css.html`
