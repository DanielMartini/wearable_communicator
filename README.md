# wearableCommunicator

Communication layer between a Flutter project for Android and IOS.

This will send messages and/or data to the platform specific communication methood.

## How to use

### Sending messages

Use the static method `WearableCommunicator.sendMessage(Map<String, dynamic> message);` to send a single shot message

#### example send message

```dart
WearableCommunicator.sendMessage({
    "text": "Some text",
    "integerValue": 1
});
```

### set data item (datalayer/userConfig)

Use the static method `WearableCommunicator.setData(String path, Map<String, dynamic> message);` to set a data item with specified path

#### example set data

```dart
WearableCommunicator.setData("/actor/cage",{
    "name": "Nicolas Cage",
    "awesomeRating": 100
});
```

### notes

* currently does not support lists or nested data structures. Therefore it is recommended to send complex items as json strings to be parsed on the recieving end
* Supported types in data layer are
  * Strings
  * Integers
  * Floats
  * Double
  * Long
  * Boolean
  * Single type lists of strings, floats, ints or longs
  * [TODO] Nested Maps (will be converted to JSON on android)

## TODO

* [X] Send messages from android though the messageClient
* [ ] recieve messages from WearOS
* [ ] Send messages from IOS though the messageClient
* [ ] recieve messages from watchOS
* [X] set android data layer items
* [ ] set IOS application context
* [ ] recieve data layer events from wearOS
* [ ] recieve data/configuration changes from watchOS
* [ ] Handle complex/nested data structures

## Getting Started

This project is a starting point for a Flutter
[plug-in package](https://flutter.dev/developing-packages/),
a specialized package that includes platform-specific implementation code for
Android and/or iOS.

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.