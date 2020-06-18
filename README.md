# Default .gitignore repository template - NativeScript Vue Blank Template
[![CodeFactor](https://www.codefactor.io/repository/github/verdantsparks/nativescript-vue-base-template/badge)](https://www.codefactor.io/repository/github/verdantsparks/nativescript-vue-base-template)

Using this repo to save time from editing .gitignore to ignore MacOS and JetBrains file on top of Visual Studio setting. 

This templates help you jump start your native cross-platform apps with built-in UI elements and best practices. Save time writing boilerplate code over and over again when you create new apps.

It also avoid committing user secrets into git repository. Please have your user secrets (e.g. API keys) placed in `.env.json` / `.env.{mode}.json` with key value pairs like:
```
{
    "FOO": "BAR"
}
```

For details please refer to `webpack.config.js` and `app/components/Home.vue` for how to access the environment variables.

This template repo created by default setting of NativeScript CLI `tns create <name>`, using ***npm*** as package manager, and does not have any plugin installed (e.g. Vuex, etc). You have to install them by your own.

The `npm run release-ios`,`npm run release-android`,`npm run preview-ios`,`npm run preview-android` commands were added in package.json to provide some typing shortcuts.

Please remove the `LICENSE` file when creating private repositories or change to other [LICENSE](https://choosealicense.com/) file to suit your needs.

## For Android build
Android requires release build to be signed. Thus you need to change the Android build command in package.json before build. Otherwise the following error will appear:

`When producing a release build, you need to specify all --key-store-* options.`

Please replace `_PATH_`, `_PW_`, `_ALIAS_`, `_ALIAS_PW_` with your own setup.

`--key-store-path _PATH_ --key-store-password _PW_ --key-store-alias _ALIAS_ --key-store-alias-password _ALIAS_PW_`

To generate key for code signing, you can refer the command below:

`keytool -genkey -v -keystore <key_store_path> -alias <alias_name> -keyalg RSA -keysize 2048 -validity 10000`

You should change the `keyalg`, `keysize` and `validity` according to your own need.

## Quick Start
Execute the following command to create an app from this template:

```
tns create my-blank-vue --template tns-template-blank-vue
```

> Note: This command will create a new NativeScript app that uses the latest version of this template published to [npm](https://www.npmjs.com/package/tns-template-blank-vue).

If you want to create a new app that uses the source of the template from the `master` branch, you can execute the following:

```
# clone nativescript-app-templates monorepo locally
git clone git@github.com:NativeScript/nativescript-app-templates.git

# create app template from local source (all templates are in the 'packages' subfolder of the monorepo)
tns create my-blank-vue --template nativescript-app-templates/packages/template-blank-vue
```

**NB:** Please, have in mind that the master branch may refer to dependencies that are not on NPM yet!

## Walkthrough

### Architecture
There is a single blank component located in:
- `/app/components/Home.vue` - sets up an empty page layout.

**Home** page has the following components:
- `ActionBar` - It holds the title of the page.
- `GridLayout` - The main page layout that should contains all the page content.

## Get Help
The NativeScript framework has a vibrant community that can help when you run into problems.

Try [joining the NativeScript community Slack](http://developer.telerik.com/wp-login.php?action=slack-invitation). The Slack channel is a great place to get help troubleshooting problems, as well as connect with other NativeScript developers.

If you have found an issue with this template, please report the problem in the [NativeScript repository](https://github.com/NativeScript/NativeScript/issues).

## Contributing

We love PRs, and accept them gladly. Feel free to propose changes and new ideas. We will review and discuss, so that they can be accepted and better integrated.
