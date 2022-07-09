# Elements Pre-alpha Dev Environment

This template should help get you started developing with Elements pre-alpha, Vue, TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out t he [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Prequisites

### Required

Install the following correctly (available in your `PATH`. We recommend a package manager such as Homebrew for the task.

- [Node.js™️](https://nodejs.org/en/)
- [Yarn](https://yarnpkg.com)
- `yarn global add @vue/cli`

### Strongly Recommended

- [Visual Studio Code](https://code.visualstudio.com) - Only supported IDE at them moment. Builds and debugging are not guaranteed to work out of the box without VSCode.

## Getting Started

- Install Rust globally by following Rust installation instructions at [Tauri.app](https://tauri.app/v1/guides/getting-started/prerequisites)
- Skip other "Getting Started" steps at the link above. We've done those for you. Simply clone this repository.
- Follow the *Yarn* version of the Development Cycle instructions at [Tauri.app](https://tauri.app/v1/guides/development/development-cycle)

## Updating Dependencies

### Updating the Tauri CLI

This command requires that you followed the instruction above correctly and did **not** install Tauri globally on your system. If not use your package manager to get updates. You are required to keep up to date with the latest version we are using in the Elements repository.

```shell
yarn upgrade @tauri-apps/cli @tauri-apps/api --latestnpm install @tauri-apps/cli@latest @tauri-apps/api@latest
```

To check the version of the Tauri CLI, use the following:

```shell
yarn outdated @tauri-apps/cli
```

Alternatively, if you are using the `vue-cli-plugin-tauri` approach:

```shell
yarn upgrade vue-cli-plugin-tauri --latestnpm install vue-cli-plugin-tauri@latest
```

## Update Cargo Packages[​](https://tauri.app/v1/guides/development/updating-dependencies#update-cargo-packages "Direct link to heading")

You can check for outdated packages with [`cargo outdated`](https://github.com/kbknapp/cargo-outdated) or on the crates.io pages: [tauri](https://crates.io/crates/tauri/versions) / [tauri-build](https://crates.io/crates/tauri-build/versions).

Go to `src-tauri/Cargo.toml` and change `tauri` and `tauri-build` to

```toml
[build-dependencies]tauri-build = "%version%"[dependencies]tauri = { version = "%version%" }
```

where `%version%` is the corresponding version number from above.

Then do the following:

```shell
cd src-tauricargo update
```

Alternatively you can run the `cargo upgrade` command provided by [cargo-edit](https://github.com/killercup/cargo-edit) which does all of this automatically.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

## Type Support For `.vue` Imports in TS

Since TypeScript cannot handle type information for `.vue` imports, they are shimmed to be a generic Vue component type by default. In most cases this is fine if you don't really care about component prop types outside of templates. However, if you wish to get actual prop types in `.vue` imports (for example to get props validation when using manual `h(...)` calls), you can enable Volar's Take Over mode by following these steps:

1. Run `Extensions: Show Built-in Extensions` from VS Code's command palette, look for `TypeScript and JavaScript Language Features`, then right click and select `Disable (Workspace)`. By default, Take Over mode will enable itself if the default TypeScript extension is disabled.
2. Reload the VS Code window by running `Developer: Reload Window` from the command palette.

You can learn more about Take Over mode [here](https://github.com/johnsoncodehk/volar/discussions/471).

## Debugging in VSCode

See [Debugging in VS Code](https://tauri.app/v1/guides/debugging/vs-code). We provide the  `.vscode/launch.json` in this distribution, but you'll need to install the [vscode-lldb](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb) extension yourself.
