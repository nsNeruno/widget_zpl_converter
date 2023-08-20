# Widget ZPL Converter

The `widget_zpl_converter` package helps convert any Flutter widget to a ZPL/ZPL2 command. This is mainly targeted towards developers who need to print **labels** using thermal printers.

## Features

- Convert any Flutter widget to a ZPL/ZPL2 command.
- ZPL/ZPL2 command can be sent to a thermal printer using [esc_pos_utils](https://pub.dev/packages/esc_pos_utils)'s [Generator.rawBytes()](https://pub.dev/documentation/esc_pos_utils/latest/esc_pos_utils/Generator/rawBytes.html) method, or any other packages with similar functionality.
- Supports variable widget sizes (while maintaining aspect ratio).

## Usage

To use this package, simply add `widget_zpl_converter` as a dependency in your `pubspec.yaml` file:

```
dependencies:
  widget_zpl_converter: ^1.0.0
```

Then, import the package in your Dart code:
```
import 'package:widget_zpl_converter/widget_zpl_converter.dart';
```

Create a widget that you want to convert to a ZPL/ZPL2 command:
```
final myWidget = Container(
  width: 100,
  height: 100,
  color: Colors.blue,
);
```

Create a `ZplConverter` object and pass the widget to the constructor:
```
final zplConverter = ZplConverter(myWidget);
```

You can then use the toZpl() method to convert any Flutter widget to a ZPL/ZPL2 command:
```
final zplCommand = zplConverter.toZpl();
```