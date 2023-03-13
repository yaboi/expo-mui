# Expo and MUI

A simple app containing a bare-bones Expo app and MUI (including emotion peer dependencies).

### MUI and React Native are incompatible...

The purpose is repo is to have a tangible example of how React Native and MUI are incompatible. Or, more accurately, React Native and MUI's use of emotion as its styling engine are incompatible.

Although Emotion offers a native solution, [`@emotion/native`](https://emotion.sh/docs/@emotion/native), MUI decided to [double down on better supporting the browser use cases](https://github.com/mui/material-ui/issues/593#issuecomment-493845263) as of May, 2019 without any sign of reprioritizing (as of March, 2023).

### What to expect when you run this app

This app was setup using the expo cli. If you're unfamiliar with expo, please visit the [Create a new app](https://docs.expo.dev/get-started/create-a-new-app/#starting-the-development-server) tutorial to see how to easily spin this app up.

Once the app is running, take note that it crashes with the following error:

```
Invariant Violation: View config getter callback for component `style` must be a function (received `undefined`). Make sure to start component names with a capital letter.

This error is located at:
    in style (created by Insertion)
    in Insertion (created by MuiStackRoot)
    in MuiStackRoot
    in Grid (created by App)
    in RCTView (created by View)
    in View (created by App)
    in App (created by withDevTools(App))
    in withDevTools(App)
    in RCTView (created by View)
    in View (created by AppContainer)
    in RCTView (created by View)
    in View (created by AppContainer)
    in AppContainer
    in main(RootComponent), js engine: hermes
```

You can see here, `style` is the cause of the error as it is being leveraged by MUI from `@emotion/react` and not `@emotion/native`. I'm sure this is just the first of the issues caused by MUI's lack of native support, but it is the exact example proving MUI and React Native are not compatible with one another.

To prove this even further, open `App.js` and comment or remove the `Stack` component imported from MUI and you will see the app builds with no problem.
