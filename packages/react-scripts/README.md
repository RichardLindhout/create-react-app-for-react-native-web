# react-scripts-for-react-native-web

This package is a forked version the package provided by [Create React App](https://github.com/facebook/create-react-app).<br>

To create an app named `my-app` with npm (5.2+) run:

```
npx create-react-app --scripts-version=react-scripts-for-react-native-web my-app
```

or with yarn (0.25+):

```
yarn create react-app  --scripts-version=react-scripts-for-react-native-web my-app
```

This fork of react-scripts configures webpack to compile any node_modules matching the pattern `react-native-*` because react native packages are typically not distributed in compiled form. You will still need to install react-native-web and any dependencies. For example, to setup a project for react-native-paper:

```
cd my-app
npm install --save react-native-web react-art react-native-paper
```

Please refer to its [User Guide](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md) for more information about create-react-app.
