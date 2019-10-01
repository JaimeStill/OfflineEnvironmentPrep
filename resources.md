# Resources

* [Overview](#overview)
    * [Directory Structure](#directory-structure)
* [Apps](#apps)
    * [SQL Server Express](#sql-server-express)
    * [Visual Studio Build Tools](#visual-studio-build-tools)
* [Code Extensions](#code-extensions)
    * [Theming](#theming)
* [Fonts](#fonts)
    * [Monospace](#monospace)
    * [Sans](#sans)
    * [Serif](#serif)
* [Platform](#platform)
    * [IIS](#iis)
    * [Sass](#sass)
    * [Program Files](#program-files)
    * [User Profile](#user-profile)
        * [.dotnet](#dotnet)
        * [.node-gyp](#node-gyp)
        * [.node-sass](#node-sass)
        * [.nuget](#nuget)
        * [.vscode](#vscode)
    * [Yarn](#yarn)
* [Stack](#stack)

## Overview
[Back to Top](#resources)

The intent of this file is to explain how to gather resources for building an offline environment for an <span>ASP.NET</span> Core 3 / Angular app. Instructions for configuring the environment once the resources are acquired are provided in the [readme](./readme.md).

### Directory Structure
[Back to Top](#resources)

The offline environment directory structure, as specified in the [readme](./readme), is as follows:

* Environment
    * apps
        * sql-2017-express
        * vs-build-tools
    * code-extensions
    * examples
    * fonts
        * Monospace
        * Sans
        * Serif
    * platform
        * IIS
        * node-sass
        * Program Files
            * dotnet
                * sdk
        * user-profile
            * .dotnet
            * .node-gyp
            * .node-sass
            * .nuget
            * .vscode
        * yarn
    * stack
    * <span>readme.md</span>
    * <span>resources.md</span>
    * settings.json

## Apps
[Back to Top](#resources)

* [7-Zip](https://www.7-zip.org/)
    * Because the built-in Windows 10 file compression utility is rough
* [Chrome Offline Installer](https://www.google.com/intl/en/chrome/?standalone=1)
* [Firefox Offline Installer](https://www.mozilla.org/en-US/firefox/all/#product-desktop-release)
* [.NET Core SDK](https://dotnet.microsoft.com/download)
    * Select **Download .NET Core SDK** under .NET Core
* [Git](https://git-scm.com/)
* [Node](https://nodejs.org/en/)
    * Current, not LTS
* [PowerShell Core](https://github.com/PowerShell/PowerShell#get-powershell)
* [Python 2](https://www.python.org/downloads/)
    * Latest Python 2 version
* [Python 3](https://www.python.org/downloads/)
    * Latest Python 3 version
* [SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017)
* [Visual Studio Code](https://code.visualstudio.com/#alt-downloads)
* [Yarn](https://yarnpkg.com/lang/en/)

### SQL Server Express
[Back to Top](#resources)

* [SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-editions-express)

1. Click **Download now** and run the installer
2. Click the **Download Media** option
3. Select **Express Advanced**
4. After the client downloads, run the client to generate the install directory (in this case, I built it in a folder named `sql-2017-express`)

### Visual Studio Build Tools
[Back to Top](#resources)

* [vs_buildtools.exe](https://visualstudio.microsoft.com/downloads)
    * Expand Tools for Visual Studio 2019, and download **Build Tools for Visual Studio 2019**

Before you can install this in an offline environment, you must create an offline installer. This can be done with the following steps:

1. Save **vs_buildtools.exe** to `Environment\apps\vs-build-tools`
2. Run the following command from a CLI opened at `Environment\apps\vs-build-tools`

```
vs_buildtools.exe --layout offline --add Microsoft.VisualStudio.Workload.MSBuildTools --add Microsoft.VisualStudio.Workload.VCTools --add Microsoft.VisualStudio.Workload.NetCoreBuildTools --lang en-us
```

> I save this script as `Environment\apps\vs-build-tools\vs-build-offline.cmd`

## Code Extensions
[Back to Top](#resources)

> These extensions can be downloaded by navigating to the link, then clicking the **Download Extension** link under **Resources** on the right side of the extension home page.

* [Angular Language Service](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template)
* [C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
* [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
* [Debugger for Firefox](https://marketplace.visualstudio.com/items?itemName=firefox-devtools.vscode-firefox-debug)
* [.NET Core / Angular Snippets](https://marketplace.visualstudio.com/items?itemName=JaimeStill.dna-snippets)
* [Editorconfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
* [MSBuild Project Tools](https://marketplace.visualstudio.com/items?itemName=tintoy.msbuild-project-tools)
* [Node Modules Intellisense](https://marketplace.visualstudio.com/items?itemName=leizongmin.node-module-intellisense)
* [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
* [Polacode](https://marketplace.visualstudio.com/items?itemName=pnp.polacode)
* [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
* [SCSS Formatter](https://marketplace.visualstudio.com/items?itemName=sibiraj-s.vscode-scss-formatter)
* [SVG](https://marketplace.visualstudio.com/items?itemName=jock.svg)
* [TSLint](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin)

### Theming

* [Andromeda](https://marketplace.visualstudio.com/items?itemName=EliverLara.andromeda)
* [Atom Material](https://marketplace.visualstudio.com/items?itemName=tobiasalthoff.atom-material-theme)
* [Atom One Dark](https://marketplace.visualstudio.com/items?itemName=akamud.vscode-theme-onedark)
* [Ayu](https://marketplace.visualstudio.com/items?itemName=teabyii.ayu)
* [Cold Horizon](https://marketplace.visualstudio.com/items?itemName=vincentfiestada.cold-horizon-vscode)
* [Flat UI](https://marketplace.visualstudio.com/items?itemName=lkytal.FlatUI)
* [Flat UI Theme](https://marketplace.visualstudio.com/items?itemName=muhammadsammy.flat-ui-dark)
* [Forest Night](https://marketplace.visualstudio.com/items?itemName=sainnhe.forest-theme)
* [Gatito](https://marketplace.visualstudio.com/items?itemName=pawelgrzybek.gatito-theme)
* [Gruvbox Material](https://marketplace.visualstudio.com/items?itemName=sainnhe.gruvbox-material)
* [Horizon](https://marketplace.visualstudio.com/items?itemName=jolaleye.horizon-theme-vscode)
* [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
* [Night Owl](https://marketplace.visualstudio.com/items?itemName=sdras.night-owl)
* [Noctis](https://marketplace.visualstudio.com/items?itemName=liviuschera.noctis)
* [Rainglow](https://marketplace.visualstudio.com/items?itemName=daylerees.rainglow)
* [Winter is Coming](https://marketplace.visualstudio.com/items?itemName=johnpapa.winteriscoming)

## Fonts
[Back to Top](#resources)

### Monospace
[Back to Top](#resources)

* [Cascadia Code](https://github.com/microsoft/cascadia-code/releases)
* [Cousine](https://fonts.google.com/specimen/Cousine)
* [Fira Code](https://github.com/tonsky/FiraCode/releases)
* [Hasklig](https://github.com/i-tu/Hasklig/releases)
* [Inconsolata](https://fonts.google.com/specimen/Inconsolata)
* [Liberation Mono](https://www.fontsquirrel.com/fonts/liberation-mono)
* [PT Mono](https://fonts.google.com/specimen/PT+Mono)
* [Roboto Mono](https://fonts.google.com/specimen/Roboto+Mono)
* [Source Code Pro](https://fonts.google.com/specimen/Source+Code+Pro)
* [Space Mono](https://fonts.google.com/specimen/Space+Mono)
* [Ubuntu Mono](https://fonts.google.com/specimen/Ubuntu+Mono)

### Sans
[Back to Top](#resources)

* [Lato](https://fonts.google.com/specimen/Lato)
* [Montserrat](https://fonts.google.com/specimen/Montserrat)
* [Open Sans](https://fonts.google.com/specimen/Open+Sans)
* [Oswald](https://fonts.google.com/specimen/Oswald)
* [PT Sans](https://fonts.google.com/specimen/PT+Sans)
* [Raleway](https://fonts.google.com/specimen/Raleway)
* [Roboto](https://fonts.google.com/specimen/Roboto)
* [San Francisco](https://github.com/blaisck/sfwin)
* [Source Sans Pro](https://fonts.google.com/specimen/Source+Sans+Pro)
* [Ubuntu](https://fonts.google.com/specimen/Ubuntu)

### Serif
[Back to Top](#resources)

* [Crimson Text](https://fonts.google.com/specimen/Crimson+Text)
* [Lora](https://fonts.google.com/specimen/Lora)
* [Merriweather](https://fonts.google.com/specimen/Merriweather)
* [Playfair Display](https://fonts.google.com/specimen/Playfair+Display)
* [PT Serif](https://fonts.google.com/specimen/PT+Serif)
* [Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab)
* [Slabo](https://fonts.google.com/specimen/Slabo+27px)
* [Source Serif Pro](https://fonts.google.com/specimen/Source+Serif+Pro)

## Platform
[Back to Top](#resources)

The sections that follow deal with acquiring resources necessary to build, develop, debug, and host an <span>ASP.NET</span> Core / Angular application.

### IIS
[Back to Top](#resources)

This directory contains all of the resources necessary for [Hosting an ASP.NET Core app on Windows Server with IIS](https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/?view=aspnetcore-3.0).

* [.NET Core 3.0 Downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0)
    * Under **Run apps - Runtime** download the **Runtime & Hosting Bundle**.
* [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=53840)
    * Required when hosting an <span>ASP.NET</span> Core app on an IIS server that is not connected to the internet.

### Sass
[Back to Top](#resources)

> The heading for this section was named **Sass** to prevent a linking collision with the **.node-sass** header under the **User Profile** section.

The `Environment\platform\node-sass` directory contains all of the compiled **node-sass** versions for the target system. In this case, `win32-x64`.

These are acquired from [node-sass/releases](https://github.com/sass/node-sass/releases).

### Program Files
[Back to Top](#resources)

Certain required pre-built packages are cached at `C:\Program Files\dotnet\sdk\NuGetFallbackFolder`. Whenever you need to capture the NuGet cache for your offline environment, you will need to backup this directory.

### User Profile
[Back to Top](#resources)

The sections that follow outline how to capture data that is cached as a result of being installed from the internet, but does not have an explicit installation process. For instance, when a project is built with specific versions of NuGet dependencies, the packages for those versions that are retrieved on the initial build are stored on your machine so that they do not need to be retrieved again.

Before attempting to access these items, it is recommended that you build out a project with the same NuGet and Yarn dependencies as your internal project will have. Then, build the project so that all of the latest dependencies are cached on your system and made available for the sections that follow.

#### .dotnet
[Back to Top](#resources)

The EF Core command-line too, `dotnet-ef`, [is no longer part of the .NET Core SDK](https://docs.microsoft.com/en-us/ef/core/what-is-new/ef-core-3.0/breaking-changes#dotnet-ef).

Instead, it is hosted as a NuGet package. However, globally installing the tool does not cause the package to be cached in the way that NuGet dependencies are typically cached.

Once you install `dotnet-ef` by running the following command:

```
dotnet tool install --global dotnet-ef
```

the tool will be installed to `%USERPROFILE%\.dotnet\tools`. If you copy the contents of this file to your user profile on the disconnected network, you can use the `dotnet-ef` tool.

#### .node-gyp
[Back to Top](#resources)

The `%USERPROFILE%\.node-gyp` directory contains the compiled Node headers required to build `node-sass`. If these are not present, `node-sass` will attempt to download them before building when running `yarn install`.

#### .node-sass
[Back to Top](#resources)

This directory contains the `{platform}-{version}_binding.node` and `{platform}-{version}_binding.pdb` compiled versions of `node-sass` for the current version of `node-sass` that your project depends on. 

> You will need this directory hosted somewhere accessible by your machine on your internal domain so that `node-sass` can build when you run `yarn install`. See the [Yarn](#yarn) section below for details.

#### .nuget
[Back to Top](#resources)

When a .NET Core project is built, the external packages that it depends on are cached at `%USERPROFILE%\.nuget\packages`. You need to place the contents of this directory on the user profile of your internal machine so that .NET Core projects can build without an internet connection.

You can verify that `%USERPROFILE%\.nuget\packages` is the global local install source for NuGet by running the following:

```
dotnet nuget locals global-packages --list
```

The output should look like this:

```
info : global-packages: %USERPROFILE%\.nuget\packages\
```

#### .vscode
[Back to Top](#resources)

The **C#** extension for Visual Studio Code retrieves data to enable features like debugging, omnisharp, and razor interpretation. To enable these features on an isolated network, you need to copy the contents of `%USERPROFILE%\.vscode\extensions\ms-vscode.csharp-{version}` to your user profile on your internal machine.

### Yarn

The `Environment/platform/yarn` directory contains a template for a Yarn configuration file, `.yarnrc`, that enables an offline mirror and specifies the `sass-binary-path` variable.

Before examining what this means, it is helpful to see the configuration template:

```
yarn-offline-mirror "./offline-cache"
yarn-offline-mirror-pruning true
sass-binary-path "path-to-binary"
```

The `yarn-offline-mirror` configuration specifies that when you run `yarn install` on a machine that is connected to the internet, the dependency tree of your `yarn.lock` file are cached in g-zipped format in the specified directory. In this case, `Environment\stack\template\Qxyz.Web\ClientApp\offline-cache`.

`yarn-offline-mirror-pruning` ensures that stale packages are removed from the directory specified by `yarn-offline-mirror`.

`sass-binary-path` specifies where the `node-sass` binaries are located. In this case, it will be where the [.node-sass](#node-sass) directory is placed on your domain.

## Stack
[Back to Top](#resources)

The `Environment\stack` directory contains a pre-prepared `dotnet new` application stack template. In my case, I maintain a [Patterns and Practices](https://github.com/JaimeStill/PatternsAndPractices) repository that contains not only the `dotnet new` template, but patterns and practices for building .NET Core / Angular apps within this template.

> See [Custom Template for `dotnet new`](https://docs.microsoft.com/en-us/dotnet/core/tools/custom-templates) for details on how to build your own templates.

In order to prepare the template for a disconnected network, the following steps need to be taken:

* Ensure all of the necessary **NuGet** packages are specified as dependencies in all of the projects within the template.
* Ensure all of the necessary **npm** dependencies are specified in the `package.json` for the Angular app.
* Add a `.yarnrc` with the settings specified in the [Yarn](#yarn) section to the Angular app's root folder (ClientApp).
* Build your project to ensure that all of your dependencies are appropriately cached.
* Delete `node_modules` from the Angular app.
* Delete any `obj` and `bin` directories out of your .NET Core projects.

With these actions taken, the template is ready to be used on a disconnected network.
