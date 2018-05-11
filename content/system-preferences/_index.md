+++
title="System Preferences"
date=2018-04-20T14:38:21-07:00
draft=true
type="page"
weight=10
+++


# System Preferences
First thing you should do is update the system. To do that go: **Apple menu () > About This Mac > Software Update.**

Also upgrade your OS in case you want to work on the latest OS. macOS upgrades are usually free so you might as well keep your machine up to date.

If this is a new computer, there are a couple tweaks you could make to the System Preferences. **These settings are all optional, consider them suggestions.**

## Users & Groups
- Login Options -> Change fast switching user menu to Icon
- Set up Password, Apple ID, Picture, etc.

## Trackpad
- Point & Click
    - Enable Tap to click with one finger
    - Change Secondary click to right corner
    - Uncheck three finger drag
- Scroll & Zoom
    - Uncheck all apart from Zoom in and out

## Dock
- Visual settings
    - Change position to left and make the size of Icons small
- Other settings
    - Remove workspace auto-switching by running the following command:

```
$ defaults write com.apple.dock workspaces-auto-swoosh -bool NO
$ killall Dock
```

## Finder
- Preferences
    - Change 'New Finder windows show:' to something other than 'All My Files' (which is a memory hog)
- Toolbar
    - Update to add path, new folder and delete
- Sidebar
    - Add home and code directory
    - Remove shared and tags
    - New finder window to open in the home directory

## Menubar
- Remove the display and Bluetooth icons
- Change battery to show percentage symbols

## Spotlight
- Uncheck fonts, images, files etc.
- Uncheck the keyboard shortcuts as we'll be replacing them with Alfred

## User Defaults
- Enable repeating keys by pressing and holding down keys: `defaults write NSGlobalDomain ApplePressAndHoldEnabled -bool false` (and restart any app that you need to repeat keys in)
- Change the default folder for screenshots
    - Open the terminal and create the folder where you would like to store your screenshots: 
    
            mkdir /path/to/screenshots/
    
    - Then run the following command: 
    
            defaults write com.apple.screencapture location /path/to/screenshots/ && killall SystemUIServer

