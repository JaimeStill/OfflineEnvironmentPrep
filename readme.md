# Environment Setup

**External Documents**  
* [Resources](./resources.md)

**Table of Contents**  
* [Overview](#overview)
  * [Directory Contents](#directory-contents)
* [Apps](#apps)
* [Fonts](#fonts)
* [Code Extensions](#code-extensions)
* [Platform](#platform)
* [Stack](#stack)
  * [Test Environment Configuration](#test-environment-configuration)
* [Settings.json](#settingsjson)

## Overview
[Back to Top](#environment-setup)

This guide provides instructions for how to setup a local development environment on a disconnected network using the resources described in the [resources](./resources.md) document.

### Directory Contents
[Back to Top](#environment-setup)

Directory | Purpose
----------|--------
`apps` | The primary and supplemental applications necessray for development in the app stack
`code-extensions` | A set of optimal Visual Studio Code extensions
`examples` | Projects that contain code that will be helpful in future projects
`fonts` | Additional fonts to aid development setup
`platform` | Infrastructure that is required to build / work with the app stack
`stack` | The app stack template along with all of the latest **Patterns and Practices** documentation / examples

## Apps
[Back to Top](#environment-setup)

This section will provide an install order and set of instructions for installing the various applications contained in the `apps` directory.

1. Install **7-Zip**
2. Install **Chrome**
3. Install **Firefox**
4. Install the **.NET Core SDK** (latest version*
5. Install **Node.js** (latest version)
6. Install **PowerShell Core**
7. Install **Python**
  * Install launcher for all users, Add Python 3.7 to PATH, then click *Customize installation*
  * Click *Next*
  * Install for all users, Precompile standard library, then click *Install*
  * When install is complete, be sure to click the **Disable Max Path Length** option
8. Install **SqlLocalDb**
  * Database server is `(localdb)\MSSQLLocalDB`
  * The first time you setup access to this database in SQL Server Management Studio, the database will be created. Be patient if it seems to be taking a moment.
9. Install **SQL Server Management Studio**
  * Open and setup a connection to `(localdb)\MSSQLLocalDB` before attempting to interact with the database via Entity Framework
10. Install **Visual Studio Code**
11. Install **Yarn**
12. Install **Git**
  * Select to **Use TTF in each console**
  * Use **Visual Studio Code** as the default editor
13. In `apps\vs-build-tools\certificates`, select each certificate, right-click, and click *Install*. For each certificate:
  * Select **Local Machine** and click *Next*
  * Click *Next*
  * Click *Finish*
14. Once each certificate is installed, restart your computer
15. Install `apps\vs-build-tools\vs_buildtools.exe`

## Fonts
[Back to Top](#environment-setup)

This directory contains sub-directories of fonts broken down by font-type (Monospace, Sans Serif, Serif).

To install fonts, use the **TTF** version for each font that has more than one file type. Select all of the **TTF** files, right-click, and click *Install*.

## Code Extensions
[Back to Top](#environment-setup)

All of the core Visual Studio Code extensions are contained in the root of the `code-extensions` directory. Theme and icon extensions are contained in the `theming` sub-directory.

To install extensions, open Visual Studio Code, click the **Extensions** icon in the Application Bar. Click the menu in the top-right of the **Extensions** Side Bar, and click **Install from VSIX...**

> You do not need to wait for an extension to install before selecting another extension to install. They will install concurrently.

## Platform
[Back to Top](#environment-setup)

The following sub-directories exist in the `platform` directory:

Directory | Purpose
----------|--------
`iis` | Contains the necessary executables for hosting an <span>ASP.NET</span> Core application in IIS
`node-sass` | Contains all of the compiled binary versions for the `node-sass` client dependency
`user-profile` | Contains cached resources necessary for configuring the environment on a user's machine profile
`yarn` | Contains a template for the `.yarnrc` configuration file

> The rest of this section will be focused on configuring the dev environment with the resources available in the `user-profile` sub-directory.

1. Copy the `.node-gyp` directory to the *%USERPROFILE%* directory.
2. Copy the `.nuget` directory to *%USERPROFILE%*, then extract the `packages.zip` file. The files contained in `packages.zip` should be inside of a `packages` folder where `packages.zip` is located. When extracted, `packages.zip` can be deleted.
3. Extract the contents of `.vscode\extensions\ms-vscode.csharp-{version}`. Copy the extracted contents and paste them into `%USERPROFILE%\.vscode\extensions\ms-vscode.csharp-{version}`.
4. Extract the contents of `.dotnet\tools`. Copy the extracted **tools** folder and paste it into the `%USERPROFILE%\.dotnet` directory.
    * This is necessary because the `dotnet` CLI no longer includes the `dotnet-ef` command line tools by default. Because the NuGet cache does not capture NuGet packaged tools that are installed via commands such as `dotnet tools install --global dotnet-ef`, the installed tool configuration needs to be replicated in the `.dotnet` directory.

> Nothing needs to be done with the `.node-sass` directory. I've placed it in the Share drive at `Dev\Resources` and configured the `sass-binary-path` variable in `.yarnrc` to point to the compiled binaries stored at this location.

## Stack
[Back to Top](#environment-setup)

1. Copy the contents of the `stack` directory to `%USERPROFILE%\Documents`.
2. Open a command prompt and execute the following:

```
dotnet new -i %USERPROFILE%\Documents\stack\template
```

This will point the app stack template to the `dotnet` CLI tool.

### Test Environment Configuration
[Back to Top](#environment-setup)

To ensure that the environment was successfully setup:

1. Navigate to any directory that you want to create a test project in
2. Execute `dotnet new stack -o {ProjectName}` where *{ProjectName}* is what you want the test project to be named.
3. When the project has been created, change directory into the project directory.
4. Execute `dotnet build` at the project root.
5. If the project builds successfully, change directory into the `{ProjectName}.Web` directory.
6. Execute `dotnet run` and test the application at http://localhost:5000

## Settings.json
[Back to Top](#environment-setup)

The `settings.json` file contained in the root of this directory contains a set of useful default settings in VS Code.

To apply the settings, copy the contents of the file, press <kbd>F1</kbd>, type **Preferences: Open Settings (JSON)**, click the associated option, and paste the contents of the file over the contents of your local settings.

> There is also a searchable GUI for managing settings by pressing <kbd>F1</kbd> and selecting **Preferences: Open User Settings**

The provided defaults are explained here:

Settings | Value | Description
---------|-------|------------
`editor.fontLigatures` | true | Enable font ligatures for fonts that support them. Font ligatures turn multiple characters into a single character to enhance readability. For instance, =>, >=, ===. These characters will appear as one character with this setting as true and a font that supports ligatures.
`editor.minimap.enabled` | false | The minimap shows a condensed version of the current code file in the top-right of the editor tab. To me, it is a distraction and not worth the real estate that it takes up.
`editor.smoothScrolling` | true | Controls whether the editor will scroll using an animation.
`git.confirmSync` | false | This prevents a Git-enabled project from asking you to sync every time it is opened. I prefer to just sync whenever I know that I need to.
`material-icon-theme.folders.theme` | classic | The default folder theme for the Material Icon Theme extension. Possible values are `specific`, `classic`, and `none`. Note that you can also modify the color of folders by setting the `material-icon-theme.folders.color` setting with a hexadecimal value, i.e. `#ff1e1f` will make the folders a bright red color.
`typescript.preferences.quoteStyle` | single | This setting actually reflects the specified setting the app stack's `tslint.json`. When specifying a string value in TypeScript, you should use singular quotes, `'string'`, as opposed to quotation marks, `"string"`.
`typescript.updateImportsOnFileMove.enabled` | always | Specifies that if a TypeScript file's physical location changes, any `import` statements affected by the location change will automatically be updated to reflect the new location.
`explorer.confirmDragAndDrop` | false | Prevents Visual Studio Code from asking you to confirm file directory changes when using drag and drop in the File Explorer.
`markdown.preview.fontSize` | 16 | Sets the base font size of text in Markdown preview tabs
`extensions.showRecommendationsOnlyOnDemand` | true | Recommendations are not fetched or shown unless specificaly requested by the user
`extensions.ignoreRecommendations` | true | Notifications for extension recommendations are not shown
`workbench.settings.editor` | ui | Opens user settings in the GUI by default as opposed to the JSON file
`markdown.preview.fontFamily` | Source Sans Pro | The base font to use in Markdown preview tabs
`material-icon-theme.activeIconPack` | angular | Sets the default icon schema to Angular
`html.format.wrapAttributes` | force-aligned | When formatting an HTML document (<kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>F</kbd>), the opening tag and first attribute share the same line, and each subsequent attribute is aligned underneath the previous attribute. This drastically improves the readability of HTML templates in Angular.
`editor.fontFamily` | Cascadia Code | The default font for the editor. Cascadia Code is a new Monospace font by Microsoft for programmers built with font ligatures.
`terminal.integrated.fontFamily` | Cascadia Code | The default font for the integrated terminal.
`breadcrumbs.enabled` | true | Enables navigational breadcrumbs directly underneath editor tabs for each opened document.
`window.zoomLevel` | 0 | No zoom applied to the application.
`terminal.integrated.shell.windows` | `C:\\Windows\\System32\\cmd.exe` | Specifies the default shell for the integrated terminal.
`workbench.colorTheme` | Default Light+ | The current active color theme. Note that color themes can be selected by clicking the Settings gear at the bottom left of Visual studio Code, then clicking *Color Theme*.
`powershell.powerShellDefaultVersion` | PowerShell Core 6 (x64) | Specifies PowerShell Core as the default version.
`powershell.powerShellExePath` | `C:\\Program Files\\PowerShell\\6\\pwsh.exe` | Specifies the executable path for PowerShell.
`editor.acceptSuggestionOncommitCharacter` | false | Prevents highlighted intellisense items from being selected when anything other than <kdb>Tab</kbd> is pressed. Often, you will press Enter after typing an attribute or property / argument name, and when this setting is set to `true`, the highlighted intellisense item overwites what you intentionally typed.
`editor.fontSize` | 15 | The fint size for the code editor.
`debug.console.fontFamily` | Cascadia Code | The default font to use for the Debug console.

The following settings are also included to prevent Visual Studio Code from trying to reach the internet:

Setting | Value
--------|------
`workbench.enableExperiments` | false
`workbench.settings.enableNaturalLanguageSearch` | false
`update.mode` | none
`update.showReleaseNotes` | false
`extensions.autoCheckUpdates` | false
`extensions.autoUpdate` | false
`telemetry.enableCrashReporter` | false
`telemetry.enableTelemetry` | false
`npm.fetchOnlinePackageInfo` | false

> You can verify these settings by pressing <kbd>F1</kbd>, opening **Preferences: Open User Settings**, and search `@tag:usesOnlineServices`.