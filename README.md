# EAS Build Issue when adding `@segment-analytics-react-native`

**Minimal, reproducable example**

In this repo I bootstrapped a new Expo project using

`npx create-expo-app freshy`

Next I configured the project for EAS using

`eas init`
`eas build:configure`

Then I wanted to confirm that EAS build was working properly:

`eas build --platform ios --local`

No errors occured and the expected build artifact was built.

Now I install **@segment/analytics-react-native**

`npx expo install @segment/analytics-react-native`

Next I ran `eas build` command again but this time I experinced some errors during the POD installation phase.

```sh
[INSTALL_PODS] [!] Unable to find a specification for `sovran-react-native` depended upon by `segment-analytics-react-native`
[INSTALL_PODS]
[INSTALL_PODS] You have either:
[INSTALL_PODS]  * out-of-date source repos which you can update with `pod repo update` or with `pod install --repo-update`.
[INSTALL_PODS]  * mistyped the name or version.
[INSTALL_PODS]  * not added the source repo that hosts the Podspec to your Podfile.
[INSTALL_PODS]
Error: pod exited with non-zero code: 1
    at ChildProcess.completionListener (/Users/mattsell/.npm/_npx/b6b81adc32d91f4e/node_modules/@expo/spawn-async/build/spawnAsync.js:41:23)
    at Object.onceWrapper (node:events:646:26)
    at ChildProcess.emit (node:events:526:28)
    at maybeClose (node:internal/child_process:1090:16)
    at Socket.<anonymous> (node:internal/child_process:449:11)
    at Socket.emit (node:events:526:28)
    at Pipe.<anonymous> (node:net:687:12)
    ...
```

The full `eas build` log can be found [here](https://gist.github.com/msell/f8057d5853e027971d10ddf5c48d46c4#file-eas-build-log-txt)