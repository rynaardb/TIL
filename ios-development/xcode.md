# Xcode

Collection of useful tips, trick and customisations for Xcode.

## Useful launch arguments

### Core Data

**SQL debugging:**

`-com.apple.CoreData.SQLDebug 1`

**Migration debugging:**

`-com.apple.CoreData.MigrationDebug 1`

## General

To show build times, run the following command in terminal:

`defaults write com.apple.dt.Xcode ShowBuildOperationDuration -bool YES`

## Tips & Tricks

**⌥ + Double click** on any build setting to see what it does

**MyView:100** in Open Quickly box will open the file at a given line number

## From Terminal

Add the following to `~/.bash_profile` or `~/.zshrc` when using zsh

```bash
# Opens Xcode project in working directory
alias xcproject='open -a "/Applications/Xcode.app" *.xcodeproj'

# Opens Xcode project in working directory
alias xcworkspace='open -a "/Applications/Xcode.app" *.xcworkspace'
```

## Online Resources

[Xcode in 20 Seconds Video Series by Paul Hudson](https://www.youtube.com/watch?v=CvVkR5z65XU&list=PLuoeXyslFTuYQ9Hoh42Bw8sPYMlTOV0V7)