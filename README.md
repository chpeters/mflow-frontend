## Table of Contents

- [Available Scripts](#available-scripts)
  - [npm start](#npm-start)
  - [npm test](#npm-test)
  - [npm run build](#npm-run-build)
- [Deployment](#deployment)
  - [Now](#Now)

## Available Scripts

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](#running-tests) for more information.
This command will be run before each deploy, so make sure it succeeds before pushing to Github.

### `npm run build`

Builds the app for production to the `build` folder.<br>
You shouldn't ever need to run this because this is handled by `Dockerfile` on deploy.

See the section about [deployment](#deployment) for more information.

## Deployment

### [Now](https://zeit.co/now)

We use Zeit Now for deployment. Every push (on every branch) to Github will run Now on the Dockerfile in the root directory. It will do the following steps:

1. Builds the app to static assets
2. Runs the tests using `npm test` and breaks the build if the tests fail.
3. Copies the assets to the public folder, so users can view them.
4. Creates a URL for the deploy (i.e. blahblahbblah.now.sh)
5. If the push was to master, it will alias that deploy to `mflow.tech`
