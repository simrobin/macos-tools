> a selected list of mac os tools

## Missing features

- [Caffeine](https://itunes.apple.com/us/app/caffeine/id411246225) : Prevent from sleep feature
- [Spectacle](https://github.com/eczarny/spectacle) : Easily organize windows without using a mouse
- [TimeMachineScheduler](http://www.klieme.com/TimeMachineScheduler.html) : Backup scheduler for Time Machine
- [Homebrew](http://brew.sh/) : Package Manager

## Applications

- [KeePassX](https://www.keepassx.org/) : Password Manager
- [iTerm2](https://www.iterm2.com/) : Terminal emulator with amazing (linux) [features](https://www.iterm2.com/features.html)
- [Calibre](http://calibre-ebook.com/) : Ebooks library manager

## Configuration

- Install command line tools (xcode package - but without having to install xcode)
```bash
xcode-select --install
```

- GNU utils for Mac (Implementations of sed, readlink, zcat, etc. are different on OS X and Linux)
  - Use homebrew to install : `brew install coreutils gnu-sed`
  - add `/usr/local/opt/coreutils/libexec/gnubin` to your `PATH` (before `/usr/bin`)

- Disable .DS_Store automatic creation in network shares (run in terminal) ([source](https://support.apple.com/en-us/HT1629)) :
```bash
defaults write com.apple.desktopservices DSDontWriteNetworkStores -boolean true
```

- Enable NTFS writing for a disk
  - Check the "DRIVE_NAME" in Finder
  - Run `sudo echo "LABEL=DRIVE_NAME none ntfs rw,auto,nobrowse" >> /etc/fstab` (replace DRIVE_NAME with previous step value - replace space by \040)
  - Volume can be found in `/Volumes/DRIVE_NAME`, you can create a symlink on desktop with `sudo ln -s /Volumes/DRIVE_NAME ~/Desktop/DRIVE_NAME`
  - When you're done, you can (optionally) remove /etc/fstab entry and symlink
