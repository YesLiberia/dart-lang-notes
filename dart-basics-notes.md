# Dart Basics

## Installing Dart:

- The Dart SDK, or Dart Software Development Kit, contains libraries and command-line tools that you need to develop Dart command-line, server, and non-Flutter web apps.
- If you’re developing Flutter apps, then you don’t need to separately download the [Dart SDK](https://dart.dev/get-dart); just [install Flutter.](https://flutter.dev/docs/get-started/install) The Flutter SDK includes the Dart SDK. 

## Android Studio Plugins:

- [How to install Dart and Flutter plugins.](https://docs.flutter.dev/get-started/editor?tab=androidstudio)
- [Dart - Dart support for IntelliJ IDEA and Android Studio.](https://plugins.jetbrains.com/plugin/6351-dart/)
- [Flutter - Flutter support for IntelliJ IDEA and Android Studio.](https://plugins.jetbrains.com/plugin/9212-flutter)

## VS Code Extensions:

- [Dart - Official Dart language support and debugger for Visual Studio Code.](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code)
- [Flutter - Flutter support and debugger for Visual Studio Code.](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter)
- [Pubspec Assist - Add and updates dependencies to your Dart and Flutter projects without leaving your editor.](https://marketplace.visualstudio.com/items?itemName=jeroen-meijer.pubspec-assist)
- [Live Share Extension Pack - Collection of extensions that enable real-time collaborative development.](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)

## Dart CLI commands:

- `dart`, is the main Dart command used to run other commands
- `dart commandName -h` : displays help manual for a command

```markdown
Usage: dart [<vm-flags>] <command|dart-file> [<arguments>]

Global options:
-h, --help                 Print this usage information.
-v, --verbose              Show additional command output.

Available commands:
  analyze   Analyze Dart code in a directory.
  compile   Compile Dart to various formats.
  create    Create a new Dart project.
  fix       Apply automated fixes to Dart source code.
  format    Idiomatically format Dart source code.
  migrate   Perform null safety migration on a project.
  pub       Work with packages.
  run       Run a Dart program.
  test      Run tests for a project
```

## Create Dart Project

- ### With CLI:

  - `dart create -t console-full myProjectName` // create console log Dart project

- ###  With VS Code:

  - Ctrl + Shift + P > `dart` >  Create 

## Run Dart Project

- By default, Dart projects are located in the `/bin` folder. The run command looks for projects to run from that predefined location.
- `dart run projectName` // runs a dart project in console

## Debug Dart Project

- ### VS Code:

  - Ctrl + F5  runs debugger 

- ### Debug w/ Dart Dev Tools 

  - Active Devtool:
    - Note Devtools require the Pub bin to be added in the System PATH
      - Append the Pub bin directory `/home/plv-src/.pub-cache/bin` to $PATH via `/etc/environment`
    - Activate Devtools package via terminal : `dart pub global activate devtool`
    - Restart VS Code for changes to take affect
  - Run app in debug mode and pause it on start: `dart run --observe --pause-isolates-on-start`
    - Copy URL link outputted in terminal
  - Paste Devtools URL in browser to access Devtools service page
    - Open terminal and type `devtools` in the console. The devtools web service will in a browser
    - Paste the URL you copied from the previous terminal into the 'Connect to a Running App' text box in  the devtools web service.

## Packages

- Dart applications containers are called packages not projects.

- A Dart package is the main component of the Dart ecosystem.

- Pub.dev is a package manager/repo that contains a large collection of Dart packages submitted and shared by Dart developers. It is similar to the Node Package Manager(NPM).

  - application package - packages that won't be uploaded to pub.dev
  - library package - packages that will be uploaded to pub.dev

- Package Files:

  - pubspec.yaml - a file that lists the specs(dependencies, version, name, etc) of your package. Similar to package.json in Angular/Node.

  - package_config.json - lists all package dependencies
  - .packages - deprecated version of package_config.json
  - pubspec.lock - links a package to its dependencies

## Dart Pub CLI Commands

- `dart pub`, is the command to run package managing commands
- `dart pub commandName -h` : displays help manual for a command

```markdown
Usage: dart pub [arguments...]
-h, --help          Print this usage information.
-v, --verbose       Shortcut for "--verbosity=all".

'Common' subcommands:
  add         Add a dependency to pubspec.yaml.
  cache       Work with the system cache.
  deps        Print package dependencies.
  get         Get the current package's dependencies.
  publish     Publish the current package to pub.dartlang.org.
  remove      Removes a dependency from the current package.
  upgrade     Upgrade the current package's dependencies to latest versions.

```

## Libraries

- Libraries are the only part of a package that is publicly accessible to everyone. That is, users of export packages only have access to the contents of the packages `/lib` folder.

- Packages communicate amongst each other via the implementation written inside of the `/lib` folder.

- A package can contain multiple libraries.

- Library file structure:

  -- lib

    -- src

  ​	-- some_action.dart

    -- my_package.dart

  

- ### Lint Rules

  - Lint rules are guidelines for writing code based on best practices of a framework.
  - The rules used by the Static Analyzer to check for warnings and error in written code.
  - The `pedantic` package documents how Dart static analysis is used internally at Google, including best practices for Dart code. It also contains snippets of Dart code that are used in implementing best practices.
  - The `analysis_options.yaml` file defines the lint rules for a given package. It is included in the `pendantic` package.
  - The Very Good Analysis package contained at Pub.dev provides Dart lint rules used by Very Good Ventures.

- ### Testing

  - Tests are written in the `/test` folder .

  - `dart test`, runs tests for a project/package in the terminal