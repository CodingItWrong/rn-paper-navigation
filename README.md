# RN Paper Navigation

Demonstrates that with `@react-navigation/native-stack` 6.x the `previous` prop is not passed to a custom header, so it can't be used to detect if a back button should be shown. Instead, a `back` prop is passed.

## Requirements

- Expo CLI
- Yarn

## Installation

```bash
$ yarn install
```

## Usage

```bash
$ yarn start
```

Then open the app on any platform.

## The Issue

Run the app on the latest commit. Click "GO TO DETAILS". The Details screen should appear and the header should have a back button in it. Note that in `App.js` in `CustomNavigationBar()`, the `back` prop is used to detect if a back button should be shown.

Next, check out commit `b599873` and reload the app. Click "GO TO DETAILS". The Details screen should appear, but the header should NOT have a back button in it. Note that in `App.js` in `CustomNavigationBar()`, the `previous` prop is used to detect if a back button should be shown. If you check the console, you'll see that the `previous` prop is `undefined` even when on the Details screen.
