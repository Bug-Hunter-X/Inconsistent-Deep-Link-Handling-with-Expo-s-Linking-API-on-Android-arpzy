# Inconsistent Deep Link Handling with Expo's Linking API on Android

This repository demonstrates an uncommon bug encountered when using Expo's `Linking` API to handle deep links on Android. The `Linking.addEventListener` method exhibits inconsistent behaviour, leading to unreliable deep link opening.

## Problem
The core issue lies in the unreliability of `Linking.addEventListener` on certain Android devices and versions.  Deep links may not register consistently, resulting in a failure to launch the intended activity within the app.

## Solution
The proposed solution involves implementing a more robust approach using a combination of `Linking.getInitialURL` and `Linking.addEventListener`.  By checking `getInitialURL` on app startup, we handle any deep links opened while the app was closed. The event listener ensures the handling of links opened while the app is running. Additional error handling and logging further enhances the reliability of deep link processing.

## Reproduction
1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app on an Android device or emulator.
4. Attempt to open a deep link. Observe the inconsistent behaviour.
5. Review the improved solution and compare its behavior.