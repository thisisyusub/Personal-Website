---
title: "Enhance your app with Firebase Dynamic Link + Riverpod + GoRouter (Part 1 — Android)"
date: 2022-11-07T15:58:24+04:00
draft: false
cover:
    image: /blogs/deeplink/cover.png
categories: ["tech"]
tags: ["flutter", "dart", "dynamic link", "deep link", "firebase", "riverpod"]
---
This is just for test

Deep link is one of the most essential functionalities in mobile apps. But, it seems difficult to developers. In this tutorial, we will build an application that supports Deep linking and easy navigation with GoRouter. As a state management, we will use Riverpod.

> Here is a link for [full source code](https://github.com/thisisyusub/Related-to-Articles/tree/master/android_deep_linking).

```dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );

  runApp(
    const ProviderScope(
      child: MyApp(),
    ),
  );
}
```