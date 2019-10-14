# Common Tasks

Common tasks

**Check user interface idiom**

`UIDevice.current.userInterfaceIdiom == .pad //iPad`
`UIDevice.current.userInterfaceIdiom == .phone //iPhone`
`UIDevice.current.userInterfaceIdiom == .tv //Apple TV`
`UIDevice.current.userInterfaceIdiom == .carPlay //Car Play`
`UIDevice.current.userInterfaceIdiom == .unspecified //Unspecified`

**Adjust the screen brightness***

`UIScreen.main.brightness = 0.1 //(0-1)`