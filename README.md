# PortableSettingsProvider

**PortableSettingsProvider** is a C# implementation of `SettingsProvider` for portable applications. 

## Usage

1. Add `src/PortableSettingsProvider.cs` to your project.

2. For each setting that should be portable, set the `Provider` property to the `PortableSettingsProvider` class, with a namespace qualifier if required. (By default this would be `crdx.Settings.PortableSettingsProvider`, but feel free to change the namespace and/or class name if you want.)

   ![The Properties Dialog](https://raw.github.com/crdx/PortableSettingsProvider/master/static/setting-properties.png)

3. Optionally, set the `Roaming` property to `True` for global settings, or `False` for local settings. (See **Types** below for an explanation.) 

   Visual Studio currently defaults this to `False`.

4. Read and write your application settings as you normally would.

## Types

Two types of settings are supported: global (roaming) and local.

### Global (aka "Roaming")

Global settings are not tied to the current machine and are available to all running instances of the application, regardless of where it's running from.

### Local

Local settings are tied to the computer on which the application is running. The computer name is used as the unique identifier.

## File format

The application settings are stored in an XML file in the same directory as the application. The filename is the same as the application's executable, with the file extension `settings`.

Global settings are stored in the `/Settings/GlobalSettings` node.

Local settings are stored in the `/Settings/LocalSettings/[ComputerName]` node.

## Bugs or contributions

Open an [issue](http://github.com/crdx/PortableSettingsProvider/issues) or send a [pull request](http://github.com/crdx/PortableSettingsProvider/pulls).

## Licence

[MIT](https://github.com/crdx/PortableSettingsProvider/blob/master/LICENCE.md).
