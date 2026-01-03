# tauri-commands    


| Command                                                 | Description                                                                                                                                 |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| [`init`](#init)                                         | Initialize a Tauri project in an existing directory                                                                                         |
| [`dev`](#dev)                                           | Run your app in development mode                                                                                                            |
| [`build`](#build)                                       | Build your app in release mode and generate bundles and installers                                                                          |
| [`bundle`](#bundle)                                     | Generate bundles and installers for your app (already built by `tauri build`)                                                               |
| [`android`](#android)                                   | Android commands                                                                                                                            |
| [`android init`](#android-init)                         | Initialize Android target in the project                                                                                                    |
| [`android dev`](#android-dev)                           | Run your app in development mode on Android                                                                                                 |
| [`android build`](#android-build)                       | Build your app in release mode for Android and generate APKs and AABs                                                                       |
| [`android run`](#android-run)                           | Run your app in production mode on Android                                                                                                  |
| [`ios`](#ios)                                           | iOS commands                                                                                                                                |
| [`ios init`](#ios-init)                                 | Initialize iOS target in the project                                                                                                        |
| [`ios dev`](#ios-dev)                                   | Run your app in development mode on iOS                                                                                                     |
| [`ios build`](#ios-build)                               | Build your app in release mode for iOS and generate IPAs                                                                                    |
| [`ios run`](#ios-run)                                   | Run your app in production mode on iOS                                                                                                      |
| [`migrate`](#migrate)                                   | Migrate from v1 to v2                                                                                                                       |
| [`info`](#info)                                         | Show a concise list of information about the environment, Rust, Node.js and their versions as well as a few relevant project configurations |
| [`add`](#add)                                           | Add a tauri plugin to the project                                                                                                           |
| [`remove`](#remove)                                     | Remove a tauri plugin from the project                                                                                                      |
| [`plugin`](#plugin)                                     | Manage or create Tauri plugins                                                                                                              |
| [`plugin new`](#plugin-new)                             | Initializes a new Tauri plugin project                                                                                                      |
| [`plugin init`](#plugin-init)                           | Initialize a Tauri plugin project on an existing directory                                                                                  |
| [`plugin android`](#plugin-android)                     | Manage the Android project for a Tauri plugin                                                                                               |
| [`plugin ios`](#plugin-ios)                             | Manage the iOS project for a Tauri plugin                                                                                                   |
| [`plugin android init`](#plugin-android-init)           | Initializes the Android project for an existing Tauri plugin                                                                                |
| [`plugin ios init`](#plugin-ios-init)                   | Initializes the iOS project for an existing Tauri plugin                                                                                    |
| [`icon`](#icon)                                         | Generate various icons for all major platforms                                                                                              |
| [`signer`](#signer)                                     | Generate signing keys for Tauri updater or sign files                                                                                       |
| [`signer sign`](#signer-sign)                           | Sign a file                                                                                                                                 |
| [`signer generate`](#signer-generate)                   | Generate a new signing key to sign files                                                                                                    |
| [`completions`](#completions)                           | Generate Tauri CLI shell completions for Bash, Zsh, PowerShell or Fish                                                                      |
| [`permission`](#permission)                             | Manage or create permissions for your app or plugin                                                                                         |
| [`permission new`](#permission-new)                     | Create a new permission file                                                                                                                |
| [`permission add`](#permission-add)                     | Add a permission to capabilities                                                                                                            |
| [`permission rm`](#permission-rm)                       | Remove a permission file, and its reference from any capability                                                                             |
| [`permission ls`](#permission-ls)                       | List permissions available to your application                                                                                              |
| [`capability`](#capability)                             | Manage or create capabilities for your app                                                                                                  |
| [`capability new`](#capability-new)                     | Create a new permission file                                                                                                                |
| [`inspect`](#inspect)                                   | Manage or create permissions for your app or plugin                                                                                         |
| [`inspect wix-upgrade-code`](#inspect-wix-upgrade-code) | Print the default Upgrade Code used by MSI installer derived from productName                                                               |