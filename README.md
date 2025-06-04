````markdown
# 🚀 Flutter GetX + Stack UI Example

This Flutter project demonstrates how to use **GetX** for state management, routing, and dependency injection, along with Flutter’s **Stack** widget for layered UI.

---

## 📌 Project Overview

- ✅ Navigation handled using `GetMaterialApp`
- ✅ Routes defined in `AppPages`
- ✅ UI layered using `Stack` and `Positioned`
- ✅ Organized using clean folder structure (`bindings`, `routes`, `features`, etc.)

---

## 🔧 How GetX is Used

### 1. **Main Entry Point**

In `main.dart`, we initialize the app with `GetMaterialApp`:

```dart
void main() {
  runApp(
    GetMaterialApp(
      title: "Stroll Bonfire",
      initialRoute: AppPages.INITIAL,
      getPages: AppPages.routes,
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primarySwatch: Colors.orange,
      ),
    ),
  );
}
````

---

### 2. **Routing**

Routes are defined in `lib/app/routes/app_pages.dart`:

```dart
class AppPages {
  static const INITIAL = Routes.HOME;

  static final routes = [
    GetPage(
      name: Routes.HOME,
      page: () => HomeView(),
      binding: HomeBinding(),
    ),
  ];
}
```

Navigate using:

```dart
Get.toNamed(Routes.HOME);
```

---

### 3. **Bindings**

Bindings are created in `lib/app/bindings/` to inject controllers:

```dart
class HomeBinding extends Bindings {
  @override
  void dependencies() {
    Get.lazyPut<HomeController>(() => HomeController());
  }
}
```

---

### 4. **Controller + View**

Use `Obx()` to rebuild UI when data changes:

```dart
Obx(() => Text(controller.count.toString()));
```

---

### 5. **Stack UI Example**

Basic usage of `Stack` to position UI elements:

```dart
Stack(
  children: [
    Container(
      color: Colors.blue,
      width: double.infinity,
      height: 300,
    ),
    Positioned(
      bottom: 20,
      left: 20,
      child: Text(
        "Overlay Text",
        style: TextStyle(color: Colors.white),
      ),
    ),
  ],
)
```

---

## 📁 Folder Structure (Simplified)

```
lib/
├── app/
│   ├── bindings/
│   ├── routes/
│   ├── features/
│   └── shared/
├── main.dart
```

---

## ✅ How to Run

```bash
flutter pub get
flutter run
```

---

## 👨‍💻 Author

Made with 💙 using Flutter + GetX.

name: untitled
description: "A new Flutter project."
# The following line prevents the package from being accidentally published to
# pub.dev using `flutter pub publish`. This is preferred for private packages.
publish_to: 'none' # Remove this line if you wish to publish to pub.dev

# The following defines the version and build number for your application.
# A version number is three numbers separated by dots, like 1.2.43
# followed by an optional build number separated by a +.
# Both the version and the builder number may be overridden in flutter
# build by specifying --build-name and --build-number, respectively.
# In Android, build-name is used as versionName while build-number used as versionCode.
# Read more about Android versioning at https://developer.android.com/studio/publish/versioning
# In iOS, build-name is used as CFBundleShortVersionString while build-number is used as CFBundleVersion.
# Read more about iOS versioning at
# https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CoreFoundationKeys.html
# In Windows, build-name is used as the major, minor, and patch parts
# of the product and file versions while build-number is used as the build suffix.
version: 1.0.0+1

environment:
  sdk: ^3.4.3

# Dependencies specify other packages that your package needs in order to work.
# To automatically upgrade your package dependencies to the latest versions
# consider running `flutter pub upgrade --major-versions`. Alternatively,
# dependencies can be manually updated by changing the version numbers below to
# the latest version available on pub.dev. To see which dependencies have newer
# versions available, run `flutter pub outdated`.
dependencies:
  flutter:
    sdk: flutter
  get: ^4.6.5
  google_fonts: ^6.2.1 # Optional for better fonts

  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.8
  flutter_svg: ^2.0.9

dev_dependencies:
  flutter_test:
    sdk: flutter

  # The "flutter_lints" package below contains a set of recommended lints to
  # encourage good coding practices. The lint set provided by the package is
  # activated in the `analysis_options.yaml` file located at the root of your
  # package. See that file for information about deactivating specific lint
  # rules and activating additional ones.
  flutter_lints: 

# For information on the generic Dart part of this file, see the
# following page: https://dart.dev/tools/pub/pubspec

# The following section is specific to Flutter packages.
flutter:

  # The following line ensures that the Material Icons font is
  # included with your application, so that you can use the icons in
  # the material Icons class.
  uses-material-design: true

  # To add assets to your application, add an assets section, like this:
  assets:
    - assets/

  # An image asset can refer to one or more resolution-specific "variants", see
  # https://flutter.dev/to/resolution-aware-images

  # For details regarding adding assets from package dependencies, see
  # https://flutter.dev/to/asset-from-package

  # To add custom fonts to your application, add a fonts section here,
  # in this "flutter" section. Each entry in this list should have a
  # "family" key with the font family name, and a "fonts" key with a
  # list giving the asset and other descriptors for the font. For
  # example:
#   fonts:
#     - family: Schyler
#       fonts:
#         - asset: fonts/Schyler-Regular.ttf
#         - asset: fonts/Schyler-Italic.ttf
#           style: italic
  #   - family: Trajan Pro
  #     fonts:
  #       - asset: fonts/TrajanPro.ttf
  #       - asset: fonts/TrajanPro_Bold.ttf
  #         weight: 700
  #
  # For details regarding fonts from package dependencies,
  # see https://flutter.dev/to/font-from-package



