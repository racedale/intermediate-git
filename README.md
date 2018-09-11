# intermediate-git
This is the base for doing a live demo presentation for a couple practical Git topics.  It tries to keep everything basic so there is as little prereqs as possible.

### Prereqs
1. Git basics (commit, pull, push, branches, pull requests)
1. Basic HTML, CSS, and JS knowledge
1. Package.json is used to manage dependencies, scripts, and other metadata about the app
1. Firebase is a service used for hosting
   - Configuration is done in `.firebaserc` and through commands in CircleCI config
1. CircleCI is used for Continuous Deployments (auto deploying the new version of the application to Firebase after each commit)
    - Configuration is done in `.circleci/config.yml`
1. Gulp is used as a build tool
    - Configuration is done in `gulpfile.js`

### How to run
1. Make sure Node is installed on your computer
1. Run `npm install` in the projects directory to install dependencies
1. Run `npm run build` to manually create build artifacts, which will be stored in `/dist` (*this is local only, it will not do a deployment*)
1. Open `/dist/index.html` in your web browser!

### Wait you want to deploy your own??
1. Fork this repo to your account, and clone it to your computer
1. Setup a CircleCI account and your forked repo as a project
1. Setup a firebase account
1. Run `npm install -g firebase-cli` then `firebase login:ci` to get an authentication token
1. In CircleCI add an environment variable named  `FIREBASE_DEPLOY_TOKEN` with the authentication token from the previous step to your project
1. Edit `.firebaserc` to the name of your firebase app