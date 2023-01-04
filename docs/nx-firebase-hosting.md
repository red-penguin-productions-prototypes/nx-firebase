# Firebase Hosting

If you have one or more other web apps (Angular/React/HTML) that are deployed to a hosting site on your Firebase project, simply add them to your workspace as usual using the standard `nx g` app generators.

Then just update your `firebase.json` or `firebase.appname.json` [hosting configuration](https://firebase.google.com/docs/hosting/full-config) to point to the `dist/apps/<webapp>` where your web app build output is.

You can then run the Firebase CLI as usual to deploy the site:

**`firebase deploy --only hosting --config firebase.appname.json`**

Or

**`nx deploy appname --only hosting`**

## Static Sites

If you deploy static websites to Firebase Hosting (that do not need to get built by Nx), just create a folder in your `apps` directory (rather than generate an Nx web app) and put your content in that folder. Then update the `hosting` section of your `firebase.json` or `firebase.appname.json` to simply point directly to this folder.

The firebase CLI hosting deploy command above will just upload the static content as required.

An application generated by Nx-Firebase is by default configured to host content in the `apps/appname/public` directory.