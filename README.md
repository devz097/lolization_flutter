# devicelocale

Gets the device locale data, independent of the app locale settings.

## Usage

```dart
import 'package:devicelocale/devicelocale.dart';
```

then

```dart
List languages = await Devicelocale.preferredLanguages;
String locale = await Devicelocale.currentLocale;
```

this should return a list of the preferred/current language locales setup on the device, with the current one being the first in the list or just the currently set device locale.

### Android specific implementation (no-op on other platforms)
Added per-app language preferences for Android (https://developer.android.com/about/versions/13/features/app-languages#kotlin)
You can check if your current device is supported `isLanguagePerAppSettingSupported`
And after checking if your device is supported you can set the per-app language preference with `setLanguagePerApp(Locale)` this will return true if success

### Note for Linux

Since GNU/Linux and POSIX doesn't provide a standard API for getting the preferred languages, `Devicelocale.preferredLanguages` always returns the current locale.

## Getting Started

For help getting started with Flutter, view our
[online documentation](https://flutter.io/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
