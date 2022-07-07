<p align="center">
    <img src="Art/logo.png" width="500" max-width="90%" alt="Swift Linters" />
</p>

<p align="center">
    <img src="https://img.shields.io/badge/Swift-5.6-orange.svg" />
    <a href="https://swift.org/package-manager">
        <img src="https://img.shields.io/badge/swiftpm-compatible-brightgreen.svg?style=flat" alt="Swift Package Manager" />
    </a>
     <a href="https://github.com/lordcodes/swift-linters/releases/latest">
         <img src="https://img.shields.io/github/release/lordcodes/swift-linters.svg?style=flat" alt="Latest release" />
     </a>
    <a href="https://twitter.com/lordcodes">
        <img src="https://img.shields.io/badge/twitter-@lordcodes-blue.svg?style=flat" alt="Twitter: @lordcodes" />
    </a>
</p>

---

This is **Swift Linters** - a tool and Tuist plugin to run SwiftLint and SwiftFormat in code formatting and linting modes.

&nbsp;

<p align="center">
    <a href="#features">Features</a> • <a href="#install">Install</a> • <a href="#usage">Usage</a> • <a href="#contributing-or-help">Contributing</a>
</p>

## Features

&nbsp;

## Install

The primary intention was to use Swift Linters as a [Tuist](https://github.com/tuist/tuist) plugin, however, it can also be used as a standard CLI tool as well.

### ▶︎ 🖥 As a Tuist Plugin

To set up as a Tuist plugin in your project simply follow the [Tuist plugin install instructions](https://docs.tuist.io/plugins/using-plugins/) using the [latest version](https://github.com/lordcodes/swift-linters/releases/latest).

Add the plugin to `Config.swift`.

```swift
import ProjectDescription

let config = Config(
    plugins: [
        .git(url: "https://github.com/lordcodes/swift-linters.git", tag: "v0.1.0")
    ]
)
```

### ▶︎ 🖥 Standalone via Swift Package Manager

Swift Linters can be easily installed globally using Swift Package Manager.

```terminal
 git clone https://github.com/lordcodes/swift-linters
 cd swift-linters
 make install
```

This will install swiftlinters into `/usr/local/bin`. If you get a permission error it may be that you don't have permission to write there in which case you just need to adjust permissions using `sudo chown -R $(whoami) /usr/local/bin`.

You can uninstall it again using `make uninstall` which simply deletes it from `/usr/local/bin`.

### ▶︎ 🍺 Homebrew

Support for Homebrew may be planned in the future.

### ▶︎ 📦 As a Swift package

To install Swift Linters for use in your own Swift code, add it is a Swift Package Manager dependency within your `Package.swift` file. For help in doing this, please check out the Swift Package Manager documentation.

```swift
.package(url: "https://github.com/lordcodes/swift-linters", exact: "0.1.0")
```

&nbsp;

## Usage

### Set up configuration

### 🖥 Via the Tuist Plugin

Run Swift Linters's tasks via Tuist.

```terminal
USAGE: tuist linters <subcommand> [-q|--quiet]

SUBCOMMANDS:
  version    Print version.

OPTIONS:
  -q, --quiet             Silence any output except errors 
```

You can obtain help using `tuist linters --help` and also obtain help for each subcommand using `tuist linters <subcommand> --help`.

### 🖥 Via the Standalone CLI

Run Swift Linters's tasks via a standalone executable.

```terminal
USAGE: swiftlinters <subcommand> [-q|--quiet]
```

Same usage as the Tuist plugin, except `tuist linters` is replaced with `swiftlinters`.

### 📦 As a Swift Package

To use Swift Linters within your own Swift code, import and use the public API of `LintersKit`.

```swift
import LintersKit

// Configure printing
Linters.shared.printer = ConsolePrinter(quiet: false)
```

## Contributing or Help

If you notice any bugs or have a new feature to suggest, please check out the [contributing guide](https://github.com/lordcodes/swift-linters/blob/master/CONTRIBUTING.md). If you want to make changes, please make sure to discuss anything big before putting in the effort of creating the PR.

To reach out, please contact [@lordcodes on Twitter](https://twitter.com/lordcodes).
