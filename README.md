# react-scripts

This package includes scripts and configuration used by [Create React App](https://github.com/facebook/create-react-app).<br>
Please refer to its documentation:

- [Getting Started](https://facebook.github.io/create-react-app/docs/getting-started) – How to create a new app.
- [User Guide](https://facebook.github.io/create-react-app/) – How to develop apps bootstrapped with Create React App.

Edited for react-native-web

Disable scope:
https://stackoverflow.com/questions/44114436/the-create-react-app-imports-restriction-outside-of-src-directory

Replace

```javascript
new ModuleScopePlugin(paths.appSrc, [paths.appPackageJson]),
```

with:

```javascript
 new ModuleScopePlugin(
          [paths.appSrc, paths.appImagesPath],
          [paths.appPackageJson]
        ),
```

add some includes

```javascript
// Process application JS with Babel.
// The preset includes JSX, Flow, TypeScript, and some ESnext features.
{
    test: /\.(js|mjs|jsx|ts|tsx)$/,
    // include: paths.appSrc,
    include: function(path) {
    return (
        path.includes(paths.appSrc) ||
        path.includes("react-native-web-tab-view") ||
        (path.includes("react-native-") &&
        !path.includes("react-native-web") &&
        !path.includes("react-native-tab-view") &&
        !path.includes("react-native-navigation"))
    );
    },
```

Support vector font's

```javascript
{
  test: /\.ttf$/,
  loader: "url-loader", // or directly file-loader
  include: path.resolve(
    __dirname,
    "node_modules/react-native-vector-icons"
  )
},
```

Support index.web replace all

`appIndexJs: resolveModule(resolveApp, "src/index"),`  
with
`appIndexJs: resolveModule(resolveApp, "index.web"),`
