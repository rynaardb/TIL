# Common Tasks

Common tasks

## Check user interface idiom

`UIDevice.current.userInterfaceIdiom == .pad //iPad`
`UIDevice.current.userInterfaceIdiom == .phone //iPhone`
`UIDevice.current.userInterfaceIdiom == .tv //Apple TV`
`UIDevice.current.userInterfaceIdiom == .carPlay //Car Play`
`UIDevice.current.userInterfaceIdiom == .unspecified //Unspecified`

## Adjust the screen brightness

`UIScreen.main.brightness = 0.1 //(0-1)`

## Show version number on launch screen

1. Add the following script as a build phase:

```bash
# Output version & build number to the APP_VERSION label on LaunchScreen.storyboard
versionNumber=$(/usr/libexec/PlistBuddy -c "Print CFBundleShortVersionString" "${INFOPLIST_FILE}")
buildNumber=$(/usr/libexec/PlistBuddy -c "Print CFBundleVersion" "${INFOPLIST_FILE}")

sed -i "" -e "/userLabel=\"APP_VERSION\"/s/text=\"[^\"]*\"/text=\"Version: $versionNumber ($buildNumber)\"/" "$PROJECT_DIR/$PROJECT_NAME/Storyboards/Base.lproj/LaunchScreen.storyboard"
```

Make sure the script is added **after*** the `Copy Bundle Resources` build phase.

2. Create a label on the launch screen and set Document > Label to `APP_VERSION`
