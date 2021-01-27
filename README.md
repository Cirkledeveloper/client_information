# client_information

A plugin to get the basic client information.

## Features

- Get unique device ID
- Get the OS name. e.g. iOS, Android, Mac OS (on web project)...
- Get the OS version. (The web project will return the user-agent if the plugin can't identify the version)
- Get software name.

  - The app project will return the application name.
  - The web project will return the browser's name. e.g. Chrome, Safari...

- Get software version

  - The app project will return the application version.
  - The web project will return the browser's version.

- Get application type. (only two types: app / web)

- Return application name.

- Return application version.

- Return application build number.

## Getting Started

In the pubspec.yaml of your flutter project, add the following dependency:

```yaml
dependencies:
  ...
  client_information: ^1.0.0
```

In your project add the following import:

```dart
import 'package:client_information/client_information.dart';
```

Then, you can use it like this:

`iOS`

```dart
ClientInformation info = await ClientInformation.fetch();

print(info.deviceId); // EA625164-4XXX-XXXX-XXXXXXXXXXXX
print(info.osName); // iOS
print(info.osVersion); // iOS 14.0
print(info.softwareName); // client_information_example
print(info.softwareVersion); // 1.0.0
print(info.applicationType); // app
print(info.applicationName); // client_information_example
print(info.applicationVersion); // 1.0.0
print(info.applicationBuildCode); // 1
```

`Android`

```dart
ClientInformation info = await ClientInformation.fetch();

print(info.deviceId); // fa3b44b92411184d
print(info.osName); // Android
print(info.osVersion); // 8.1.0
print(info.softwareName); // client_information_example
print(info.softwareVersion); // 1.0
print(info.applicationType); // app
print(info.applicationName); // client_information_example
print(info.applicationVersion); // 1.0
print(info.applicationBuildCode); // 1
```

`web`

```dart
ClientInformation info = await ClientInformation.fetch();

print(info.deviceId); // 0010tmmxxxxxxxxxxxxxxxx
print(info.osName); // Mac OS
print(info.osVersion); // 11.1.0
print(info.softwareName); // Chrome
print(info.softwareVersion); // 88.0.4324.96
print(info.applicationType); // web
print(info.applicationName); // client_information_example
print(info.applicationVersion); // unknown_version
print(info.applicationBuildCode); // 0
```