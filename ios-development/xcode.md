# Xcode

Collection of useful tips, trick and customisations for Xcode.

## Useful launch arguments

### Core Data

**SQL debugging:**

`-com.apple.CoreData.SQLDebug 1`

**Migration debugging:**

`-com.apple.CoreData.MigrationDebug 1`

## General

**Show build times** 

Run the following command in terminal: `defaults write com.apple.dt.Xcode ShowBuildOperationDuration -bool YES`

**Empty Xcode project template**

See [instructions](https://github.com/sleeve/ios-empty-application-xcode-template) - will need to create a two folders (Templates/Application) under ~/Library/Developer/Xcode/

## Handy Shortcuts

**⌘ + ⌥ + /** - Generates documentation

**control + i** correct indentation

**shift + ⌥ + clicking on file** opens the file with assistant editor layout

**shift + control + click** for multi-cursor editing

## Tips & Tricks

**⌥ + Double click** on any build setting to see what it does

**MyView:100** in Open Quickly box will open the file at a given line number

## Warnings & Errors

`#warning("refactor this!")` adds a warning in Xcode when building\
`#error("do not ship this!")` shows an error in Xcode when building

## From Terminal

Add the following to `~/.bash_profile` or `~/.zshrc` when using zsh

```bash
# Opens Xcode project in working directory
alias xcproject='open -a "/Applications/Xcode.app" *.xcodeproj'

# Opens Xcode project in working directory
alias xcworkspace='open -a "/Applications/Xcode.app" *.xcworkspace'
```

## Simulator

**⌘ + T** to slow down animations

## Online Resources

* [Xcode in 20 Seconds Video Series by Paul Hudson](https://www.youtube.com/watch?v=CvVkR5z65XU&list=PLuoeXyslFTuYQ9Hoh42Bw8sPYMlTOV0V7)
* [30 Xcode tips in 45 minutes](https://skillsmatter.com/skillscasts/13299-30-xcode-tips-in-45-minutes)
