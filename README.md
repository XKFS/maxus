# Maxus

Open Source fork of the Bluegriffon Web Editor based on the rendering engine of Firefox

## Building from source

###
* Required:
* 1. Python 2.7
  2. Rust

* Make sure you have the necessary dependencies that can build firefox: [windows](https://firefox-source-docs.mozilla.org/setup/windows_build.html), [MacOS X](https://firefox-source-docs.mozilla.org/setup/macos_build.html), [linux](https://firefox-source-docs.mozilla.org/setup/linux_build.html)
* Clone [gecko-dev](https://github.com/mozilla/gecko-dev) from github and do the following:

  `git clone https://github.com/mozilla/gecko-dev bluegriffon-source`

  `cd bluegriffon-source`

  `git clone https://github.com/therealglazou/bluegriffon`

* update the mozilla tree

  ```git reset --hard `cat bluegriffon/config/gecko_dev_revision.txt` ```

  `patch -p 1 < bluegriffon/config/gecko_dev_content.patch`

  `patch -p 1 < bluegriffon/config/gecko_dev_idl.patch`

* create a `.mozconfig` file inside your `bluegriffon-source` directory. The  settings I am using on a daily basis on OS X (Sierra) can be found in `bluegriffon/config/mozconfig.macosx`

### Build

`./mach build`

### Run in a temporary profile

`./mach run`

### Package the build

`./mach package`
