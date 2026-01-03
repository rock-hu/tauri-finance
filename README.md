# Tauri + React

This template should help get you started developing with Tauri and React in Vite.  




|                 |     |                                                      |
| --------------- | --- | ---------------------------------------------------- |
| @refinedev/core |     | ![npm](https://img.shields.io/npm/v/@refinedev/core) |
| @refinedev/antd |     | ![npm](https://img.shields.io/npm/v/@refinedev/antd) |
| antd            |     | ![npm](https://img.shields.io/npm/v/antd)            |
| i18next         |     | ![npm](https://img.shields.io/npm/v/i18next)         |
| react-i18next   |     | ![npm](https://img.shields.io/npm/v/react-i18next)   |
| @tauri-apps/api |     | ![npm](https://img.shields.io/npm/v/@tauri-apps/api) |
| @tauri-apps/cli |     | ![npm](https://img.shields.io/npm/v/@tauri-apps/cli) |
| react           |     | ![npm](https://img.shields.io/npm/v/react)           |
| react-dom       |     | ![npm](https://img.shields.io/npm/v/react-dom)       |

## commands 
```bash
npx sort-package-json
npx npm-check-updates
```

## architecture 

![](./docs/images/architecture.svg) 

| Aspect           | Tauri's Approach                                                          | Result                                                            |
| ---------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Binary Size**  | Uses OS native webview instead of bundling Chromium/browser engine        | Applications are 3-5 MB vs 100+ MB for Electron apps              |
| **Performance**  | Rust-compiled native binary with direct OS API access                     | No JavaScript runtime overhead in backend; native execution speed |
| **Security**     | Compiled binaries, custom protocol handlers, capability-based permissions | No exposed source code; harder to reverse engineer                |
| **Development**  | Any web framework + TypeScript API + Rust backend                         | Use familiar web tools while accessing full native capabilities   |
| **Distribution** | Native platform packages (DMG, MSI, DEB, AppImage, IPA, APK)              | Standard OS installation and updates; no special runtime required |


## core components  

| Component               | Crate/Package                   | Key Types/Functions                                   | Purpose                                                       |
| ----------------------- | ------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------- |
| **Core Framework**      | `tauri`                         | `App`, `AppHandle`, `Manager`, `Builder`              | Main crate coordinating all components, application lifecycle |
| **JavaScript API**      | `@tauri-apps/api`               | `invoke()`, `emit()`, `listen()`, `Window`, `Webview` | TypeScript bindings for frontend-backend communication        |
| **Runtime Abstraction** | `tauri-runtime`                 | `Runtime` trait, `Dispatcher`, `EventLoop`            | Platform-agnostic runtime interface definitions               |
| **WRY Runtime**         | `tauri-runtime-wry`             | `WryRuntime`, `WryWindowDispatcher`                   | Concrete implementation using WRY and TAO                     |
| **Configuration**       | `tauri-utils`                   | `Config`, `parse::`, `assets::`                       | Config parsing, validation, asset handling                    |
| **Build System**        | `tauri-build`                   | `build()`, `setup_codegen()`                          | Build-time code generation invoked from build.rs              |
| **Code Generation**     | `tauri-codegen`                 | `context::`, `embedded_assets::`                      | Compile-time asset embedding, context generation              |
| **Macros**              | `tauri-macros`                  | `#[tauri::command]`, `generate_handler!`              | Procedural macros for command registration                    |
| **Bundler**             | `tauri-bundler`                 | `PackageSettings`, `SettingsBuilder`                  | Platform-specific package creation (DMG, MSI, etc.)           |
| **CLI**                 | `tauri-cli` / `@tauri-apps/cli` | `dev`, `build`, `init` commands                       | Development server, build orchestration                       |

## [License](https://tauri.app/concept/architecture/#license) 

> Tauri itself is licensed under MIT or Apache-2.0. If you repackage it and modify any source code, it is your responsibility to verify that you are complying with all upstream licenses. Tauri is provided AS-IS with no explicit claim for suitability for any purpose. 

## init 
```bash
sh <(curl https://create.tauri.app/sh)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 16121  100 16121    0     0   8463      0  0:00:01  0:00:01 --:--:--  8462
info: downloading create-tauri-app
✔ Project name · tauri-finance
✔ Identifier · com.tauri.finance
✔ Choose which language to use for your frontend · TypeScript / JavaScript - (pnpm, yarn, npm, deno, bun)
✔ Choose your package manager · npm
✔ Choose your UI template · React - (https://react.dev/)
✔ Choose your UI flavor · JavaScript

Template created!

Your system is missing dependencies (or they do not exist in $PATH):
╭────────────────────┬───────────────────────────────────────────────────────────────────╮
│ Rust               │ Visit https://www.rust-lang.org/learn/get-started#installing-rust │
├────────────────────┼───────────────────────────────────────────────────────────────────┤
│ webkit2gtk & rsvg2 │ Visit https://tauri.app/guides/prerequisites/#linux               │
╰────────────────────┴───────────────────────────────────────────────────────────────────╯

Make sure you have installed the prerequisites for your OS: https://tauri.app/start/prerequisites/, then run:
  cd tauri-finance
  npm install
  npm run tauri android init

For Desktop development, run:
  npm run tauri dev

For Android development, run:
  npm run tauri android dev
```


## build  

`npm run tauri build`

```
vite v6.4.1 building for production...
✓ 30 modules transformed.
dist/index.html                   0.46 kB │ gzip:  0.30 kB
dist/assets/react-CHdo91hT.svg    4.13 kB │ gzip:  2.05 kB
dist/assets/index-ZCvx-mwu.css    1.37 kB │ gzip:  0.65 kB
dist/assets/index-BPguhl1m.js   144.85 kB │ gzip: 46.58 kB
✓ built in 476ms
   Compiling tauri-finance v0.1.0 (/home/rock/workspace/tauri-finance/src-tauri)
    Finished `release` profile [optimized] target(s) in 19.43s
       Built application at: /home/rock/workspace/tauri-finance/src-tauri/target/release/tauri-finance
        Info Patching binary "/home/rock/workspace/tauri-finance/src-tauri/target/release/tauri-finance" for type deb
    Bundling tauri-finance_0.1.0_amd64.deb (/home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/deb/tauri-finance_0.1.0_amd64.deb)
        Info Patching binary "/home/rock/workspace/tauri-finance/src-tauri/target/release/tauri-finance" for type rpm
    Bundling tauri-finance-0.1.0-1.x86_64.rpm (/home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/rpm/tauri-finance-0.1.0-1.x86_64.rpm)
        Info Patching binary "/home/rock/workspace/tauri-finance/src-tauri/target/release/tauri-finance" for type appimage
 Downloading https://github.com/tauri-apps/binary-releases/releases/download/apprun-old/AppRun-x86_64
 Downloading https://github.com/tauri-apps/binary-releases/releases/download/linuxdeploy/linuxdeploy-x86_64.AppImage
 Downloading https://github.com/linuxdeploy/linuxdeploy-plugin-appimage/releases/download/continuous/linuxdeploy-plugin-appimage-x86_64.AppImage
    Bundling tauri-finance_0.1.0_amd64.AppImage (/home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/appimage/tauri-finance_0.1.0_amd64.AppImage)
    Finished 3 bundles at:
        /home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/deb/tauri-finance_0.1.0_amd64.deb
        /home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/rpm/tauri-finance-0.1.0-1.x86_64.rpm
        /home/rock/workspace/tauri-finance/src-tauri/target/release/bundle/appimage/tauri-finance_0.1.0_amd64.AppImage
```

```
-rw-rw-r-- 1 rock rock 6.1M  1月  3 10:24 tauri-finance_0.1.0_amd64.deb
-rw-rw-r-- 1 rock rock 6.1M  1月  3 10:24 tauri-finance-0.1.0-1.x86_64.rpm
-rwxr-xr-x 1 rock rock  77M  1月  3 10:26 tauri-finance_0.1.0_amd64.AppImage
```

## test 

## package

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Tauri](https://marketplace.visualstudio.com/items?itemName=tauri-apps.tauri-vscode) + [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)


## references   
| item                                                                    | link(s)                           |
| ----------------------------------------------------------------------- | --------------------------------- |
| The TAO of cross-platform windowing. A library in Rust built for Tauri. | https://github.com/tauri-apps/tao |
| Cross-platform WebView library in Rust for Tauri.                       | https://github.com/tauri-apps/wry |


