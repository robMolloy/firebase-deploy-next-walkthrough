# firebase-deploy-next-test

## Summary

The quickest way to use the benefits discussed in this article is to copy and paste the commands from the `package.json` and run them in order

## Create app

Create a new NextJS project with `npx create-next-app@latest`

Create a new project in console.firebase.google.com

## package.json commands

The commands added to package.json are explained here;

- "firebase:install" => Install `firebase-tools` as a dev dependency with `npm i -D firebase-tools`
- "firebase:init-hosting" => Initialise hosting `node_modules/.bin/firebase init hosting` and follow the wizard
  - Select yes to detected NextJS app
  - Select the appropriate location for the server
  - Set up automatic builds on deploy
  - Add the github repo using format `robMolloy/firebase-deploy-next-test`
  - No additional build script required on each deploy
  - Set up automatic deployment when a PR is merged
  - Set up the live github branch
- "firebase:enable-webframeworks" => Add the enable webframeworks flag with the following command
<pre>echo \"        env:\n          FIREBASE_CLI_EXPERIMENTS: webframeworks\" >> .github/workflows/firebase-hosting-merge.yml && echo \"        env:\n          FIREBASE_CLI_EXPERIMENTS: webframeworks\" >> .github/workflows/firebase-hosting-pull-request.yml</pre>
