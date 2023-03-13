# Expo and MUI

A simple app containing a bare-bones Expo app and MUI (including emotion peer dependencies).

### MUI and React Native are incompatible...

The purpose is repo is to have a tangible example of how React Native and MUI are incompatible. Or, more accurately, React Native and MUI's use of emotion as its styling engine are incompatible.

Although Emotion offers a native solution, [`@emotion/native`](https://emotion.sh/docs/@emotion/native), MUI decided to [double down on better supporting the browser use cases](https://github.com/mui/material-ui/issues/593#issuecomment-493845263) as of May, 2019 without any sign of reprioritizing (as of March, 2023).
