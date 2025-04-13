# Flutter Complete Learning Path - From Zero to Hero

> Last updated for Flutter 3.29.2 • Dart 3.7.2

A comprehensive 56-day learning journey to master Flutter development. This repository provides a structured path for learning Flutter from basics to advanced topics.

## Table of Contents

- [Week 1: Fundamentals](#week-1-fundamentals)
- [Week 2: UI Components & User Input](#week-2-ui-components--user-input)
- [Week 3: State Management](#week-3-state-management)
- [Week 4: Data Management & Backend](#week-4-data-management--backend)
- [Week 5: Advanced Flutter](#week-5-advanced-flutter)
- [Week 6: Performance & Deployment](#week-6-performance--deployment)
- [Week 7: Specialized Topics](#week-7-specialized-topics)
- [Week 8: Advanced Architectures and Mastery](#week-8-advanced-architectures-and-mastery)

## Week 1: Fundamentals

### Day 1: Setting Up Flutter Environment

#### Objectives:
- Install Flutter SDK and set up your development environment
- Run your first Flutter application
- Understand the Flutter project structure

#### Key Tasks:
1. Install Flutter SDK from [flutter.dev](https://flutter.dev)
2. Set up Android Studio/VS Code with Flutter and Dart plugins
3. Configure Android emulator/iOS simulator
4. Run `flutter doctor` to verify installation
5. Create and run a basic Flutter app with `flutter create my_app`

#### Sample Code - Basic Flutter App:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Set up an Editor](https://flutter.dev/docs/get-started/editor)
- [Test Drive](https://flutter.dev/docs/get-started/test-drive)

### Day 2: Dart Language Basics

#### Objectives:
- Learn fundamental Dart programming concepts
- Understand variables, data types, and control flow
- Practice basic Dart syntax

#### Key Topics:
1. Variables and data types
   - `int`, `double`, `String`, `bool`
   - `var`, `final`, and `const`
   - Type inference

2. Control flow
   - `if`/`else` statements
   - `for` and `while` loops
   - `switch`/`case` statements

3. Collections
   - Lists, Sets, and Maps
   - Collection manipulation

4. Null safety basics
   - Nullable vs non-nullable types
   - The `?` and `!` operators
   - Late initialization

#### Sample Code - Dart Basics:
```dart
void main() {
  // Variables and types
  String name = 'Flutter';
  int version = 3;
  double value = 3.29;
  bool isAwesome = true;
  
  // Null safety
  String? nullableName = null;
  String nonNullableName = 'Must have a value';
  
  // Control flow
  if (isAwesome) {
    print('Flutter is awesome!');
  } else {
    print('Hmm, something is wrong.');
  }
  
  // Loops
  for (int i = 0; i < 5; i++) {
    print('Count: $i');
  }
  
  // Collections
  List<String> frameworks = ['Flutter', 'React Native', 'SwiftUI'];
  Map<String, String> properties = {
    'language': 'Dart',
    'platform': 'Cross-platform',
  };
  
  // Collection operations
  frameworks.add('Xamarin');
  frameworks.forEach((framework) => print(framework));
}
```

#### Resources:
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [DartPad - Try Dart Online](https://dartpad.dev)
- [Dart Null Safety](https://dart.dev/null-safety)

### Day 3: Object-Oriented Programming in Dart

#### Objectives:
- Learn OOP concepts in Dart
- Understand classes, inheritance, and mixins
- Practice creating reusable code structures

#### Key Topics:
1. Classes and Objects
   - Defining classes
   - Properties and methods
   - Instance and static members

2. Constructors
   - Default constructors
   - Named constructors
   - Factory constructors
   - Initializer lists

3. Inheritance and Interfaces
   - Extending classes
   - Implementing interfaces
   - Method overriding

4. Mixins and Extensions
   - Creating and using mixins
   - Extension methods
   - When to use each

#### Sample Code - OOP in Dart:
```dart
// Basic class
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.guest() : name = 'Guest', age = 18;
  
  // Method
  void introduce() {
    print('Hello, I am $name and I am $age years old.');
  }
  
  // Static method
  static Person createAdult(String name) {
    return Person(name, 30);
  }
}

// Inheritance
class Student extends Person {
  String school;
  
  Student(String name, int age, this.school) : super(name, age);
  
  @override
  void introduce() {
    super.introduce();
    print('I study at $school.');
  }
}

// Mixin
mixin Musical {
  void playInstrument() {
    print('Playing music');
  }
}

// Using a mixin
class MusicStudent extends Student with Musical {
  MusicStudent(String name, int age, String school) 
      : super(name, age, school);
}

// Extension
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${this.substring(1)}";
  }
}

void main() {
  var person = Person('John', 25);
  person.introduce();
  
  var student = Student('Mary', 20, 'Harvard');
  student.introduce();
  
  var musician = MusicStudent('Bob', 22, 'Juilliard');
  musician.introduce();
  musician.playInstrument();
  
  print('flutter'.capitalize()); // Extension method
}
```

#### Resources:
- [Dart Classes](https://dart.dev/guides/language/language-tour#classes)
- [Mixins in Dart](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Extension Methods](https://dart.dev/guides/language/extension-methods)

### Day 4: Flutter Widgets Basics

#### Objectives:
- Understand the Flutter widget concept
- Learn the difference between StatelessWidget and StatefulWidget
- Build simple Flutter UI layouts

#### Key Topics:
1. Understanding Widgets
   - Widget tree and composition
   - Flutter's rendering pipeline
   - Widget lifecycle

2. StatelessWidget vs StatefulWidget
   - When to use each type
   - Converting between the two
   - State management basics

3. Basic Layout Widgets
   - Container widget
   - Row and Column
   - Text widgets
   - Button variants

#### Sample Code - Basic Flutter Widgets:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Widget Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            Container(
              margin: EdgeInsets.all(20),
              padding: EdgeInsets.all(15),
              decoration: BoxDecoration(
                color: Colors.lightBlue[100],
                borderRadius: BorderRadius.circular(10),
              ),
              child: Text('This is a Container widget'),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Text('Text Button'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated Button'),
                ),
              ],
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Introduction to widgets](https://flutter.dev/docs/development/ui/widgets-intro)
- [Building layouts](https://flutter.dev/docs/development/ui/layout)

### Day 5: Layout Building

#### Objectives:
- Master Flutter's layout system
- Learn how to use various layout widgets
- Build complex layouts using multiple widgets

#### Key Topics:
1. Row and Column alignment
   - MainAxisAlignment and CrossAxisAlignment
   - MainAxisSize properties
   - Nesting for complex layouts

2. Container customization
   - Margin and padding
   - Decoration and styling
   - Constraints

3. Working with Stack
   - Positioning widgets
   - Alignment and overlays
   - Z-index equivalent

4. Flexible and Expanded
   - Dynamic space allocation
   - Flex factor
   - When to use each

#### Sample Code - Flutter Layouts:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Layout Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

# Flutter Complete Learning Path - From Zero to Hero

> Last updated for Flutter 3.29.2 • Dart 3.7.2

A comprehensive 56-day learning journey to master Flutter development. This repository provides a structured path for learning Flutter from basics to advanced topics.

## Table of Contents

- [Week 1: Fundamentals](#week-1-fundamentals)
- [Week 2: UI Components & User Input](#week-2-ui-components--user-input)
- [Week 3: State Management](#week-3-state-management)
- [Week 4: Data Management & Backend](#week-4-data-management--backend)
- [Week 5: Advanced Flutter](#week-5-advanced-flutter)
- [Week 6: Performance & Deployment](#week-6-performance--deployment)
- [Week 7: Specialized Topics](#week-7-specialized-topics)
- [Week 8: Advanced Architectures and Mastery](#week-8-advanced-architectures-and-mastery)

## Week 1: Fundamentals

### Day 1: Setting Up Flutter Environment

#### Objectives:
- Install Flutter SDK and set up your development environment
- Run your first Flutter application
- Understand the Flutter project structure

#### Key Tasks:
1. Install Flutter SDK from [flutter.dev](https://flutter.dev)
2. Set up Android Studio/VS Code with Flutter and Dart plugins
3. Configure Android emulator/iOS simulator
4. Run `flutter doctor` to verify installation
5. Create and run a basic Flutter app with `flutter create my_app`

#### Sample Code - Basic Flutter App:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Set up an Editor](https://flutter.dev/docs/get-started/editor)
- [Test Drive](https://flutter.dev/docs/get-started/test-drive)

### Day 2: Dart Language Basics

#### Objectives:
- Learn fundamental Dart programming concepts
- Understand variables, data types, and control flow
- Practice basic Dart syntax

#### Key Topics:
1. Variables and data types
   - `int`, `double`, `String`, `bool`
   - `var`, `final`, and `const`
   - Type inference

2. Control flow
   - `if`/`else` statements
   - `for` and `while` loops
   - `switch`/`case` statements

3. Collections
   - Lists, Sets, and Maps
   - Collection manipulation

4. Null safety basics
   - Nullable vs non-nullable types
   - The `?` and `!` operators
   - Late initialization

#### Sample Code - Dart Basics:
```dart
void main() {
  // Variables and types
  String name = 'Flutter';
  int version = 3;
  double value = 3.29;
  bool isAwesome = true;
  
  // Null safety
  String? nullableName = null;
  String nonNullableName = 'Must have a value';
  
  // Control flow
  if (isAwesome) {
    print('Flutter is awesome!');
  } else {
    print('Hmm, something is wrong.');
  }
  
  // Loops
  for (int i = 0; i < 5; i++) {
    print('Count: $i');
  }
  
  // Collections
  List<String> frameworks = ['Flutter', 'React Native', 'SwiftUI'];
  Map<String, String> properties = {
    'language': 'Dart',
    'platform': 'Cross-platform',
  };
  
  // Collection operations
  frameworks.add('Xamarin');
  frameworks.forEach((framework) => print(framework));
}
```

#### Resources:
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [DartPad - Try Dart Online](https://dartpad.dev)
- [Dart Null Safety](https://dart.dev/null-safety)

### Day 3: Object-Oriented Programming in Dart

#### Objectives:
- Learn OOP concepts in Dart
- Understand classes, inheritance, and mixins
- Practice creating reusable code structures

#### Key Topics:
1. Classes and Objects
   - Defining classes
   - Properties and methods
   - Instance and static members

2. Constructors
   - Default constructors
   - Named constructors
   - Factory constructors
   - Initializer lists

3. Inheritance and Interfaces
   - Extending classes
   - Implementing interfaces
   - Method overriding

4. Mixins and Extensions
   - Creating and using mixins
   - Extension methods
   - When to use each

#### Sample Code - OOP in Dart:
```dart
// Basic class
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.guest() : name = 'Guest', age = 18;
  
  // Method
  void introduce() {
    print('Hello, I am $name and I am $age years old.');
  }
  
  // Static method
  static Person createAdult(String name) {
    return Person(name, 30);
  }
}

// Inheritance
class Student extends Person {
  String school;
  
  Student(String name, int age, this.school) : super(name, age);
  
  @override
  void introduce() {
    super.introduce();
    print('I study at $school.');
  }
}

// Mixin
mixin Musical {
  void playInstrument() {
    print('Playing music');
  }
}

// Using a mixin
class MusicStudent extends Student with Musical {
  MusicStudent(String name, int age, String school) 
      : super(name, age, school);
}

// Extension
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${this.substring(1)}";
  }
}

void main() {
  var person = Person('John', 25);
  person.introduce();
  
  var student = Student('Mary', 20, 'Harvard');
  student.introduce();
  
  var musician = MusicStudent('Bob', 22, 'Juilliard');
  musician.introduce();
  musician.playInstrument();
  
  print('flutter'.capitalize()); // Extension method
}
```

#### Resources:
- [Dart Classes](https://dart.dev/guides/language/language-tour#classes)
- [Mixins in Dart](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Extension Methods](https://dart.dev/guides/language/extension-methods)

### Day 4: Flutter Widgets Basics

#### Objectives:
- Understand the Flutter widget concept
- Learn the difference between StatelessWidget and StatefulWidget
- Build simple Flutter UI layouts

#### Key Topics:
1. Understanding Widgets
   - Widget tree and composition
   - Flutter's rendering pipeline
   - Widget lifecycle

2. StatelessWidget vs StatefulWidget
   - When to use each type
   - Converting between the two
   - State management basics

3. Basic Layout Widgets
   - Container widget
   - Row and Column
   - Text widgets
   - Button variants

#### Sample Code - Basic Flutter Widgets:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Widget Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            Container(
              margin: EdgeInsets.all(20),
              padding: EdgeInsets.all(15),
              decoration: BoxDecoration(
                color: Colors.lightBlue[100],
                borderRadius: BorderRadius.circular(10),
              ),
              child: Text('This is a Container widget'),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Text('Text Button'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated Button'),
                ),
              ],
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Introduction to widgets](https://flutter.dev/docs/development/ui/widgets-intro)
- [Building layouts](https://flutter.dev/docs/development/ui/layout)

### Day 5: Layout Building

#### Objectives:
- Master Flutter's layout system
- Learn how to use various layout widgets
- Build complex layouts using multiple widgets

#### Key Topics:
1. Row and Column alignment
   - MainAxisAlignment and CrossAxisAlignment
   - MainAxisSize properties
   - Nesting for complex layouts

2. Container customization
   - Margin and padding
   - Decoration and styling
   - Constraints

3. Working with Stack
   - Positioning widgets
   - Alignment and overlays
   - Z-index equivalent

4. Flexible and Expanded
   - Dynamic space allocation
   - Flex factor
   - When to use each

#### Sample Code - Flutter Layouts:
# Flutter Complete Learning Path - From Zero to Hero

> Last updated for Flutter 3.29.2 • Dart 3.7.2

A comprehensive 56-day learning journey to master Flutter development. This repository provides a structured path for learning Flutter from basics to advanced topics.

## Table of Contents

- [Week 1: Fundamentals](#week-1-fundamentals)
- [Week 2: UI Components & User Input](#week-2-ui-components--user-input)
- [Week 3: State Management](#week-3-state-management)
- [Week 4: Data Management & Backend](#week-4-data-management--backend)
- [Week 5: Advanced Flutter](#week-5-advanced-flutter)
- [Week 6: Performance & Deployment](#week-6-performance--deployment)
- [Week 7: Specialized Topics](#week-7-specialized-topics)
- [Week 8: Advanced Architectures and Mastery](#week-8-advanced-architectures-and-mastery)

## Week 1: Fundamentals

### Day 1: Setting Up Flutter Environment

#### Objectives:
- Install Flutter SDK and set up your development environment
- Run your first Flutter application
- Understand the Flutter project structure

#### Key Tasks:
1. Install Flutter SDK from [flutter.dev](https://flutter.dev)
2. Set up Android Studio/VS Code with Flutter and Dart plugins
3. Configure Android emulator/iOS simulator
4. Run `flutter doctor` to verify installation
5. Create and run a basic Flutter app with `flutter create my_app`

#### Sample Code - Basic Flutter App:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Set up an Editor](https://flutter.dev/docs/get-started/editor)
- [Test Drive](https://flutter.dev/docs/get-started/test-drive)

### Day 2: Dart Language Basics

#### Objectives:
- Learn fundamental Dart programming concepts
- Understand variables, data types, and control flow
- Practice basic Dart syntax

#### Key Topics:
1. Variables and data types
   - `int`, `double`, `String`, `bool`
   - `var`, `final`, and `const`
   - Type inference

2. Control flow
   - `if`/`else` statements
   - `for` and `while` loops
   - `switch`/`case` statements

3. Collections
   - Lists, Sets, and Maps
   - Collection manipulation

4. Null safety basics
   - Nullable vs non-nullable types
   - The `?` and `!` operators
   - Late initialization

#### Sample Code - Dart Basics:
```dart
void main() {
  // Variables and types
  String name = 'Flutter';
  int version = 3;
  double value = 3.29;
  bool isAwesome = true;
  
  // Null safety
  String? nullableName = null;
  String nonNullableName = 'Must have a value';
  
  // Control flow
  if (isAwesome) {
    print('Flutter is awesome!');
  } else {
    print('Hmm, something is wrong.');
  }
  
  // Loops
  for (int i = 0; i < 5; i++) {
    print('Count: $i');
  }
  
  // Collections
  List<String> frameworks = ['Flutter', 'React Native', 'SwiftUI'];
  Map<String, String> properties = {
    'language': 'Dart',
    'platform': 'Cross-platform',
  };
  
  // Collection operations
  frameworks.add('Xamarin');
  frameworks.forEach((framework) => print(framework));
}
```

#### Resources:
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [DartPad - Try Dart Online](https://dartpad.dev)
- [Dart Null Safety](https://dart.dev/null-safety)

### Day 3: Object-Oriented Programming in Dart

#### Objectives:
- Learn OOP concepts in Dart
- Understand classes, inheritance, and mixins
- Practice creating reusable code structures

#### Key Topics:
1. Classes and Objects
   - Defining classes
   - Properties and methods
   - Instance and static members

2. Constructors
   - Default constructors
   - Named constructors
   - Factory constructors
   - Initializer lists

3. Inheritance and Interfaces
   - Extending classes
   - Implementing interfaces
   - Method overriding

4. Mixins and Extensions
   - Creating and using mixins
   - Extension methods
   - When to use each

#### Sample Code - OOP in Dart:
```dart
// Basic class
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.guest() : name = 'Guest', age = 18;
  
  // Method
  void introduce() {
    print('Hello, I am $name and I am $age years old.');
  }
  
  // Static method
  static Person createAdult(String name) {
    return Person(name, 30);
  }
}

// Inheritance
class Student extends Person {
  String school;
  
  Student(String name, int age, this.school) : super(name, age);
  
  @override
  void introduce() {
    super.introduce();
    print('I study at $school.');
  }
}

// Mixin
mixin Musical {
  void playInstrument() {
    print('Playing music');
  }
}

// Using a mixin
class MusicStudent extends Student with Musical {
  MusicStudent(String name, int age, String school) 
      : super(name, age, school);
}

// Extension
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${this.substring(1)}";
  }
}

void main() {
  var person = Person('John', 25);
  person.introduce();
  
  var student = Student('Mary', 20, 'Harvard');
  student.introduce();
  
  var musician = MusicStudent('Bob', 22, 'Juilliard');
  musician.introduce();
  musician.playInstrument();
  
  print('flutter'.capitalize()); // Extension method
}
```

#### Resources:
- [Dart Classes](https://dart.dev/guides/language/language-tour#classes)
- [Mixins in Dart](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Extension Methods](https://dart.dev/guides/language/extension-methods)

### Day 4: Flutter Widgets Basics

#### Objectives:
- Understand the Flutter widget concept
- Learn the difference between StatelessWidget and StatefulWidget
- Build simple Flutter UI layouts

#### Key Topics:
1. Understanding Widgets
   - Widget tree and composition
   - Flutter's rendering pipeline
   - Widget lifecycle

2. StatelessWidget vs StatefulWidget
   - When to use each type
   - Converting between the two
   - State management basics

3. Basic Layout Widgets
   - Container widget
   - Row and Column
   - Text widgets
   - Button variants

#### Sample Code - Basic Flutter Widgets:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Widget Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            Container(
              margin: EdgeInsets.all(20),
              padding: EdgeInsets.all(15),
              decoration: BoxDecoration(
                color: Colors.lightBlue[100],
                borderRadius: BorderRadius.circular(10),
              ),
              child: Text('This is a Container widget'),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Text('Text Button'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated Button'),
                ),
              ],
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Introduction to widgets](https://flutter.dev/docs/development/ui/widgets-intro)
- [Building layouts](https://flutter.dev/docs/development/ui/layout)

### Day 5: Layout Building

#### Objectives:
- Master Flutter's layout system
- Learn how to use various layout widgets
- Build complex layouts using multiple widgets

#### Key Topics:
1. Row and Column alignment
   - MainAxisAlignment and CrossAxisAlignment
   - MainAxisSize properties
   - Nesting for complex layouts

2. Container customization
   - Margin and padding
   - Decoration and styling
   - Constraints

3. Working with Stack
   - Positioning widgets
   - Alignment and overlays
   - Z-index equivalent

4. Flexible and Expanded
   - Dynamic space allocation
   - Flex factor
   - When to use each

#### Sample Code - Flutter Layouts:
```dart
import 'package:flutter/material.dart';

class LayoutDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Layout Examples')),
      body: SingleChildScrollView(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Row example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Row with MainAxisAlignment.spaceEvenly:'),
            ),
            Container(
              height: 50,
              color: Colors.amber[100],
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: [
                  Icon(Icons.star),
                  Icon(Icons.star),
                  Icon(Icons.star),
                ],
              ),
            ),
            
            // Column with alignment
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Column with different alignments:'),
            ),
            Container(
              height: 100,
              color: Colors.blue[100],
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                crossAxisAlignment: CrossAxisAlignment.end,
                children: [
                  Text('Right aligned'),
                  Text('Center aligned vertically'),
                ],
              ),
            ),
            
            // Stack example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Stack with positioned elements:'),
            ),
            Container(
              height: 150,
              color: Colors.green[100],
              child: Stack(
                children: [
                  Positioned(
                    left: 20,
                    top: 20,
                    child: Container(
                      color: Colors.red,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    left: 40,
                    top: 40,
                    child: Container(
                      color: Colors.blue,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    right: 40,
                    bottom: 20,
                    child: Container(
                      color: Colors.green,
                      height: 50,
                      width: 50,
                    ),
                  ),
                ],
              ),
            ),
            
            // Expanded and Flexible
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Expanded and Flexible:'),
            ),
            Container(
              height: 50,
              color: Colors.purple[100],
              child: Row(
                children: [
                  Expanded(
                    flex: 2,
                    child: Container(color: Colors.purple[200]),
                  ),
                  Flexible(
                    flex: 1,
                    child: Container(color: Colors.purple[300]),
                  ),
                  Expanded(
                    flex: 1,
                    child: Container(color: Colors.purple[400]),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Layout Cheat Sheet](https://medium.com/flutter-community/flutter-layout-cheat-sheet-5363348d037e)
- [Understanding constraints](https://flutter.dev/docs/development/ui/layout/constraints)
- [Row and Column Classes](https://api.flutter.dev/flutter/widgets/Row-class.html)

### Day 6: Advanced Layout Techniques

#### Objectives:
- Master scrollable widgets in Flutter
- Learn about responsive layouts
- Implement complex layouts using CustomScrollView

#### Key Topics:
1. ListView and GridView
   - Basic usage
   - Builder patterns for efficiency
   - Custom item builders

2. ScrollView variants
   - SingleChildScrollView
   - PageView
   - TabBarView

3. CustomScrollView and Slivers
   - SliverAppBar
   - SliverList and SliverGrid
   - Custom sliver widgets

4. LayoutBuilder for responsive design
   - Adapting to available space
   - Media queries
   - Orientation-based layouts

#### Sample Code - Advanced Layouts:
```dart
import 'package:flutter/material.dart';

class AdvancedLayoutDemo extends StatelessWidget {
  final List<String> items = List.generate(50, (index) => 'Item ${index + 1}');
  
  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 4,
      child: Scaffold(
        appBar: AppBar(
          title: Text('Advanced Layouts'),
          bottom: TabBar(
            tabs: [
              Tab(text: 'ListView'),
              Tab(text: 'GridView'),
              Tab(text: 'CustomScroll'),
              Tab(text: 'Responsive'),
            ],
          ),
        ),
        body: TabBarView(
          children: [
            // ListView example
            ListView.builder(
              itemCount: items.length,
              itemBuilder: (context, index) {
                return ListTile(
                  leading: CircleAvatar(child: Text('${index + 1}')),
                  title: Text(items[index]),
                  subtitle: Text('Tap for details'),
                  trailing: Icon(Icons.arrow_forward_ios),
                  onTap: () {},
                );
              },
            ),
            
            // GridView example
            GridView.builder(
              gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                crossAxisCount: 3,
                childAspectRatio: 1.0,
                crossAxisSpacing: 10,
                mainAxisSpacing: 10,
              ),
              padding: EdgeInsets.all(10),
              itemCount: items.length,
              itemBuilder: (context, index) {
                return Card(
                  color: Colors.primaries[index % Colors.primaries.length],
                  child: Center(
                    child: Text(
                      '${index + 1}',
                      style: TextStyle(color: Colors.white, fontSize: 24),
                    ),
                  ),
                );
              },
            ),
            
            // CustomScrollView example
            CustomScrollView(
              slivers: <Widget>[
                SliverAppBar(
                  expandedHeight: 200.0,
                  floating: false,
                  pinned: true,
                  flexibleSpace: FlexibleSpaceBar(
                    title: Text('Sliver Example'),
                    background: Image.network(
                      'https://picsum.photos/800/600',
                      fit: BoxFit.cover,
                    ),
                  ),
                ),
                SliverPadding(
                  padding: EdgeInsets.all(8.0),
                  sliver: SliverList(
                    delegate: SliverChildBuilderDelegate(
                      (context, index) {
                        return Card(
                          margin: EdgeInsets.symmetric(
                            vertical: 8.0,
                            horizontal: 4.0,
                          ),
                          child: ListTile(
                            title: Text(items[index]),
                          ),
                        );
                      },
                      childCount: 10,
                    ),
                  ),
                ),
                SliverToBoxAdapter(
                  child: Container(
                    padding: EdgeInsets.all(16.0),
                    color: Colors.amber,
                    child: Text(
                      'SliverGrid Section',
                      style: TextStyle(fontSize: 18),
                    ),
                  ),
                ),
                SliverGrid(
                  gridDelegate: SliverGridDelegateWithMaxCrossAxisExtent(
                    maxCrossAxisExtent: 200.0,
                    mainAxisSpacing: 10.0,
                    crossAxisSpacing: 10.0,
                    childAspectRatio: 1.0,
                  ),
                  delegate: SliverChildBuilderDelegate(
                    (BuildContext context, int index) {
                      return Container(
                        color: Colors.primaries[index % Colors.primaries.length],
                        child: Center(
                          child: Text(
                            'Grid Item ${index + 1}',
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      );
                    },
                    childCount: 20,
                  ),
                ),
              ],
            ),
            
            // Responsive layout with LayoutBuilder
            LayoutBuilder(
              builder: (context, constraints) {
                if (constraints.maxWidth > 600) {
                  // Wide layout (tablet/desktop)
                  return GridView.builder(
                    gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                      crossAxisCount: 3,
                      childAspectRatio: 2.0,
                    ),
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: Column(
                          mainAxisAlignment: MainAxisAlignment.center,
                          children: [
                            Icon(Icons.aspect_ratio, size: 30),
                            Text('Width: ${constraints.maxWidth.toInt()}'),
                            Text('Item $index (Wide Layout)'),
                          ],
                        ),
                      );
                    },
                  );
                } else {
                  // Narrow layout (phone)
                  return ListView.builder(
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: ListTile(
                          leading: Icon(Icons.aspect_ratio),
                          title: Text('Item $index (Narrow Layout)'),
                          subtitle: Text(
                            'Width: ${constraints.maxWidth.toInt()}',
                          ),
                        ),
                      );
                    },
                  );
                }
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [ListView Class](https://api.flutter.dev/flutter/widgets/ListView-class.html)
- [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)
- [Responsive UI in Flutter](https://flutter.dev/docs/development/ui/layout/responsive)

### Day 7: Navigation and Routing

#### Objectives:
- Implement navigation between screens
- Learn different routing approaches
- Pass data between screens

#### Key Topics:
1. Basic Navigation
   - Navigator.push and Navigator.pop
   - MaterialPageRoute
   - CupertinoPageRoute

2. Named Routes
   - Defining routes
   - Navigator.pushNamed
   - Passing arguments

3. Advanced Navigation
   - Deep linking
   - Navigation history manipulation
   - WillPopScope usage

4. Route Transitions
   - Custom transitions
   - Hero animations with navigation
   - Page route builders

#### Sample Code - Navigation:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(NavigationApp());
}

class NavigationApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Navigation Demo',
      // Named routes approach
      initialRoute: '/',
      routes: {
        '/': (context) => HomeScreen(),
        '/details': (context) => DetailScreen(),
        '/settings': (context) => SettingsScreen(),
      },
      // Optional: Custom route handling for dynamic routes or unknown routes
      onGenerateRoute: (settings) {
        if (settings.name!.startsWith('/product/')) {
          final productId = settings.name!.split('/')[2];
          return MaterialPageRoute(
            builder: (context) => ProductScreen(productId: productId),
          );
        }
        return null; // Let onUnknownRoute handle null cases
      },
      onUnknownRoute: (settings) {
        return MaterialPageRoute(
          builder: (context) => NotFoundScreen(),
        );
      },
    );
  }
}
```

## Week 2: UI Components & User Input

### Day 8: Input Widgets

#### Objectives:
- Learn various input widgets in Flutter
- Implement text input, selection, and editing
- Handle user input validation
- Create custom input widgets

#### Key Topics:
1. TextField and TextFormField
   - Basic usage
   - Input decoration
   - Text input types
   - Input controllers

2. Form validation
   - Form widget
   - Validator functions
   - Error messages
   - Form state management

3. Checkboxes and Radio buttons
   - Grouping and selection
   - Custom styling
   - State management

4. Switches and Sliders
   - Toggle and selection
   - Custom styling
   - State management

5. Date and time pickers
   - DatePicker and TimePicker
   - Customization and styling
   - State management

#### Sample Code - Input Widgets:
```dart
import 'package:flutter/material.dart';

class InputWidgetsDemo extends StatefulWidget {
  @override
  _InputWidgetsDemoState createState() => _InputWidgetsDemoState();
}

class _InputWidgetsDemoState extends State<InputWidgetsDemo> {
  final _formKey = GlobalKey<FormState>();
  final _textController = TextEditingController();
  bool _isChecked = false;
  double _sliderValue = 50.0;
  DateTime _selectedDate = DateTime.now();
  TimeOfDay _selectedTime = TimeOfDay.now();
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Input Widgets Demo')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16.0),
        child: Form(
          key: _formKey,
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              TextFormField(
                controller: _textController,
                decoration: InputDecoration(
                  labelText: 'Enter your name',
                  border: OutlineInputBorder(),
                ),
                validator: (value) {
                  if (value!.isEmpty) {
                    return 'Please enter your name';
                  }
                  return null;
                },
              ),
              SizedBox(height: 20),
              Text('Selected date: ${_selectedDate.toString().split(' ')[0]}'),
              ElevatedButton(
                onPressed: () async {
                  final pickedDate = await showDatePicker(
                    context: context,
                    initialDate: _selectedDate,
                    firstDate: DateTime(2000),
                    lastDate: DateTime(2100),
                  );
                  if (pickedDate != null && pickedDate != _selectedDate) {
                    setState(() {
                      _selectedDate = pickedDate;
                    });
                  }
                },
                child: Text('Pick a date'),
              ),
              SizedBox(height: 20),
              Text('Selected time: ${_selectedTime.format(context)}'),
              ElevatedButton(
                onPressed: () async {
                  final pickedTime = await showTimePicker(
                    context: context,
                    initialTime: _selectedTime,
                  );
                  if (pickedTime != null && pickedTime != _selectedTime) {
                    setState(() {
                      _selectedTime = pickedTime;
                    });
                  }
                },
                child: Text('Pick a time'),
              ),
              SizedBox(height: 20),
              CheckboxListTile(
                title: Text('Checkbox example'),
                value: _isChecked,
                onChanged: (value) {
                  setState(() {
                    _isChecked = value!;
                  });
                },
              ),
              SizedBox(height: 20),
              Slider(
                value: _sliderValue,
                min: 0,
                max: 100,
                divisions: 10,
                label: _sliderValue.round().toString(),
                onChanged: (value) {
                  setState(() {
                    _sliderValue = value;
                  });
                },
              ),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () {
                  if (_formKey.currentState!.validate()) {
                    ScaffoldMessenger.of(context).showSnackBar(
                      SnackBar(content: Text('Form submitted')),
                    );
                  }
                },
                child: Text('Submit'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Text Fields](https://flutter.dev/docs/cookbook/forms/text-field-changes)
- [Form Validation](https://flutter.dev/docs/cookbook/forms/validation)
- [Checkboxes](https://flutter.dev/docs/cookbook/forms/checkbox)
- [Sliders](https://flutter.dev/docs/cookbook/forms/slider)
- [Date and Time Pickers](https://flutter.dev/docs/cookbook/forms/date-and-time-pickers)

### Day 9: Dialogs and Alerts

#### Objectives:
- Learn how to display dialogs and alerts
- Implement various types of dialogs
- Handle user interactions in dialogs
- Create custom dialog widgets

#### Key Topics:
1. AlertDialog
   - Basic usage
   - Title, content, and actions
   - Custom styling

2. SimpleDialog
   - Basic usage
   - Title and options
   - Custom styling

3. BottomSheet
   - Persistent and modal bottom sheets
   - Custom styling
   - State management

4. SnackBar and Toast messages
   - Displaying temporary messages
   - Custom styling
   - Action handling

5. Modal progress indicators
   - Circular and linear progress indicators
   - Custom styling
   - State management

#### Sample Code - Dialogs and Alerts:
```dart
import 'package:flutter/material.dart';

class DialogsAndAlertsDemo extends StatefulWidget {
  @override
  _DialogsAndAlertsDemoState createState() => _DialogsAndAlertsDemoState();
}

class _DialogsAndAlertsDemoState extends State<DialogsAndAlertsDemo> {
  bool _isLoading = false;
  
  void _showAlertDialog() {
    showDialog(
      context: context,
      builder: (context) {
        return AlertDialog(
          title: Text('Alert Dialog'),
          content: Text('This is an alert dialog.'),
          actions: [
            TextButton(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('OK'),
            ),
          ],
        );
      },
    );
  }
  
  void _showSimpleDialog() {
    showDialog(
      context: context,
      builder: (context) {
        return SimpleDialog(
          title: Text('Simple Dialog'),
          children: [
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('Option 1'),
            ),
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('Option 2'),
            ),
          ],
        );
      },
    );
  }
  
  void _showBottomSheet() {
    showModalBottomSheet(
      context: context,
      builder: (context) {
        return Container(
          padding: EdgeInsets.all(16.0),
          child: Column(
            mainAxisSize: MainAxisSize.min,
            children: [
              Text('Bottom Sheet'),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () {
                  Navigator.of(context).pop();
                },
                child: Text('Close'),
              ),
            ],
          ),
        );
      },
    );
  }
  
  void _showSnackBar() {
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(
        content: Text('This is a snackbar message'),
        action: SnackBarAction(
          label: 'Undo',
          onPressed: () {
            // Handle undo action
          },
        ),
      ),
    );
  }
  
  void _showProgressIndicator() {
    setState(() {
      _isLoading = true;
    });
    Future.delayed(Duration(seconds: 2), () {
      setState(() {
        _isLoading = false;
      });
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Dialogs and Alerts Demo')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: _showAlertDialog,
              child: Text('Show Alert Dialog'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _showSimpleDialog,
              child: Text('Show Simple Dialog'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _showBottomSheet,
              child: Text('Show Bottom Sheet'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _showSnackBar,
              child: Text('Show SnackBar'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _showProgressIndicator,
              child: Text('Show Progress Indicator'),
            ),
            SizedBox(height: 20),
            if (_isLoading) CircularProgressIndicator(),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Alert Dialog](https://flutter.dev/docs/cookbook/dialogs/alert-dialog)
- [Simple Dialog](https://flutter.dev/docs/cookbook/dialogs/simple-dialog)
- [Bottom Sheet](https://flutter.dev/docs/cookbook/design/bottom-sheet)
- [SnackBar](https://flutter.dev/docs/cookbook/design/snackbars)
- [Progress Indicators](https://flutter.dev/docs/cookbook/effects/progress-indicator)

### Day 10: Custom Widgets

#### Objectives:
- Learn how to create reusable widgets
- Understand the composition vs inheritance approach
- Implement custom widgets with state
- Handle widget lifecycle events

#### Key Topics:
1. Creating reusable components
   - Extracting common UI patterns
   - Composition over inheritance
   - Widget composition

2. Composition vs inheritance
   - When to use each approach
   - Pros and cons of each
   - Best practices

3. Widget lifecycle
   - Widget creation
   - Widget updates
   - Widget destruction
   - Lifecycle methods

4. Keys in Flutter
   - Understanding keys
   - Keyed vs unkeyed widgets
   - When to use keys

5. InheritedWidget basics
   - Creating and using InheritedWidget
   - Updating InheritedWidget
   - Performance considerations

#### Sample Code - Custom Widgets:
```dart
import 'package:flutter/material.dart';

class CustomWidgetsDemo extends StatefulWidget {
  @override
  _CustomWidgetsDemoState createState() => _CustomWidgetsDemoState();
}

class _CustomWidgetsDemoState extends State<CustomWidgetsDemo> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Custom Widgets Demo')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            SizedBox(height: 20),
            CustomButton(
              onPressed: _incrementCounter,
              child: Text('Increment Counter'),
            ),
          ],
        ),
      ),
    );
  }
}

class CustomButton extends StatelessWidget {
  final VoidCallback onPressed;
  final Widget child;
  
  const CustomButton({
    Key? key,
    required this.onPressed,
    required this.child,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: onPressed,
      child: child,
    );
  }
}
```

#### Resources:
- [Creating Custom Widgets](https://flutter.dev/docs/development/ui/widgets/composition)
- [Composition vs Inheritance](https://flutter.dev/docs/development/ui/widgets/composition#composition-vs-inheritance)
- [Widget Lifecycle](https://flutter.dev/docs/development/ui/widgets/lifecycle)
# Flutter Complete Learning Path - From Zero to Hero

> Last updated for Flutter 3.29.2 • Dart 3.7.2

A comprehensive 56-day learning journey to master Flutter development. This repository provides a structured path for learning Flutter from basics to advanced topics.

## Table of Contents

- [Week 1: Fundamentals](#week-1-fundamentals)
- [Week 2: UI Components & User Input](#week-2-ui-components--user-input)
- [Week 3: State Management](#week-3-state-management)
- [Week 4: Data Management & Backend](#week-4-data-management--backend)
- [Week 5: Advanced Flutter](#week-5-advanced-flutter)
- [Week 6: Performance & Deployment](#week-6-performance--deployment)
- [Week 7: Specialized Topics](#week-7-specialized-topics)
- [Week 8: Advanced Architectures and Mastery](#week-8-advanced-architectures-and-mastery)

## Week 1: Fundamentals

### Day 1: Setting Up Flutter Environment

#### Objectives:
- Install Flutter SDK and set up your development environment
- Run your first Flutter application
- Understand the Flutter project structure

#### Key Tasks:
1. Install Flutter SDK from [flutter.dev](https://flutter.dev)
2. Set up Android Studio/VS Code with Flutter and Dart plugins
3. Configure Android emulator/iOS simulator
4. Run `flutter doctor` to verify installation
5. Create and run a basic Flutter app with `flutter create my_app`

#### Sample Code - Basic Flutter App:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Set up an Editor](https://flutter.dev/docs/get-started/editor)
- [Test Drive](https://flutter.dev/docs/get-started/test-drive)

### Day 2: Dart Language Basics

#### Objectives:
- Learn fundamental Dart programming concepts
- Understand variables, data types, and control flow
- Practice basic Dart syntax

#### Key Topics:
1. Variables and data types
   - `int`, `double`, `String`, `bool`
   - `var`, `final`, and `const`
   - Type inference

2. Control flow
   - `if`/`else` statements
   - `for` and `while` loops
   - `switch`/`case` statements

3. Collections
   - Lists, Sets, and Maps
   - Collection manipulation

4. Null safety basics
   - Nullable vs non-nullable types
   - The `?` and `!` operators
   - Late initialization

#### Sample Code - Dart Basics:
```dart
void main() {
  // Variables and types
  String name = 'Flutter';
  int version = 3;
  double value = 3.29;
  bool isAwesome = true;
  
  // Null safety
  String? nullableName = null;
  String nonNullableName = 'Must have a value';
  
  // Control flow
  if (isAwesome) {
    print('Flutter is awesome!');
  } else {
    print('Hmm, something is wrong.');
  }
  
  // Loops
  for (int i = 0; i < 5; i++) {
    print('Count: $i');
  }
  
  // Collections
  List<String> frameworks = ['Flutter', 'React Native', 'SwiftUI'];
  Map<String, String> properties = {
    'language': 'Dart',
    'platform': 'Cross-platform',
  };
  
  // Collection operations
  frameworks.add('Xamarin');
  frameworks.forEach((framework) => print(framework));
}
```

#### Resources:
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [DartPad - Try Dart Online](https://dartpad.dev)
- [Dart Null Safety](https://dart.dev/null-safety)

### Day 3: Object-Oriented Programming in Dart

#### Objectives:
- Learn OOP concepts in Dart
- Understand classes, inheritance, and mixins
- Practice creating reusable code structures

#### Key Topics:
1. Classes and Objects
   - Defining classes
   - Properties and methods
   - Instance and static members

2. Constructors
   - Default constructors
   - Named constructors
   - Factory constructors
   - Initializer lists

3. Inheritance and Interfaces
   - Extending classes
   - Implementing interfaces
   - Method overriding

4. Mixins and Extensions
   - Creating and using mixins
   - Extension methods
   - When to use each

#### Sample Code - OOP in Dart:
```dart
// Basic class
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.guest() : name = 'Guest', age = 18;
  
  // Method
  void introduce() {
    print('Hello, I am $name and I am $age years old.');
  }
  
  // Static method
  static Person createAdult(String name) {
    return Person(name, 30);
  }
}

// Inheritance
class Student extends Person {
  String school;
  
  Student(String name, int age, this.school) : super(name, age);
  
  @override
  void introduce() {
    super.introduce();
    print('I study at $school.');
  }
}

// Mixin
mixin Musical {
  void playInstrument() {
    print('Playing music');
  }
}

// Using a mixin
class MusicStudent extends Student with Musical {
  MusicStudent(String name, int age, String school) 
      : super(name, age, school);
}

// Extension
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${this.substring(1)}";
  }
}

void main() {
  var person = Person('John', 25);
  person.introduce();
  
  var student = Student('Mary', 20, 'Harvard');
  student.introduce();
  
  var musician = MusicStudent('Bob', 22, 'Juilliard');
  musician.introduce();
  musician.playInstrument();
  
  print('flutter'.capitalize()); // Extension method
}
```

#### Resources:
- [Dart Classes](https://dart.dev/guides/language/language-tour#classes)
- [Mixins in Dart](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Extension Methods](https://dart.dev/guides/language/extension-methods)

### Day 4: Flutter Widgets Basics

#### Objectives:
- Understand the Flutter widget concept
- Learn the difference between StatelessWidget and StatefulWidget
- Build simple Flutter UI layouts

#### Key Topics:
1. Understanding Widgets
   - Widget tree and composition
   - Flutter's rendering pipeline
   - Widget lifecycle

2. StatelessWidget vs StatefulWidget
   - When to use each type
   - Converting between the two
   - State management basics

3. Basic Layout Widgets
   - Container widget
   - Row and Column
   - Text widgets
   - Button variants

#### Sample Code - Basic Flutter Widgets:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Widget Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            Container(
              margin: EdgeInsets.all(20),
              padding: EdgeInsets.all(15),
              decoration: BoxDecoration(
                color: Colors.lightBlue[100],
                borderRadius: BorderRadius.circular(10),
              ),
              child: Text('This is a Container widget'),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Text('Text Button'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated Button'),
                ),
              ],
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Introduction to widgets](https://flutter.dev/docs/development/ui/widgets-intro)
- [Building layouts](https://flutter.dev/docs/development/ui/layout)

### Day 5: Layout Building

#### Objectives:
- Master Flutter's layout system
- Learn how to use various layout widgets
- Build complex layouts using multiple widgets

#### Key Topics:
1. Row and Column alignment
   - MainAxisAlignment and CrossAxisAlignment
   - MainAxisSize properties
   - Nesting for complex layouts

2. Container customization
   - Margin and padding
   - Decoration and styling
   - Constraints

3. Working with Stack
   - Positioning widgets
   - Alignment and overlays
   - Z-index equivalent

4. Flexible and Expanded
   - Dynamic space allocation
   - Flex factor
   - When to use each

#### Sample Code - Flutter Layouts:
```dart
import 'package:flutter/material.dart';

class LayoutDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Layout Examples')),
      body: SingleChildScrollView(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Row example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Row with MainAxisAlignment.spaceEvenly:'),
            ),
            Container(
              height: 50,
              color: Colors.amber[100],
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: [
                  Icon(Icons.star),
                  Icon(Icons.star),
                  Icon(Icons.star),
                ],
              ),
            ),
            
            // Column with alignment
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Column with different alignments:'),
            ),
            Container(
              height: 100,
              color: Colors.blue[100],
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                crossAxisAlignment: CrossAxisAlignment.end,
                children: [
                  Text('Right aligned'),
                  Text('Center aligned vertically'),
                ],
              ),
            ),
            
            // Stack example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Stack with positioned elements:'),
            ),
            Container(
              height: 150,
              color: Colors.green[100],
              child: Stack(
                children: [
                  Positioned(
                    left: 20,
                    top: 20,
                    child: Container(
                      color: Colors.red,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    left: 40,
                    top: 40,
                    child: Container(
                      color: Colors.blue,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    right: 40,
                    bottom: 20,
                    child: Container(
                      color: Colors.green,
                      height: 50,
                      width: 50,
                    ),
                  ),
                ],
              ),
            ),
            
            // Expanded and Flexible
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Expanded and Flexible:'),
            ),
            Container(
              height: 50,
              color: Colors.purple[100],
              child: Row(
                children: [
                  Expanded(
                    flex: 2,
                    child: Container(color: Colors.purple[200]),
                  ),
                  Flexible(
                    flex: 1,
                    child: Container(color: Colors.purple[300]),
                  ),
                  Expanded(
                    flex: 1,
                    child: Container(color: Colors.purple[400]),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Layout Cheat Sheet](https://medium.com/flutter-community/flutter-layout-cheat-sheet-5363348d037e)
- [Understanding constraints](https://flutter.dev/docs/development/ui/layout/constraints)
- [Row and Column Classes](https://api.flutter.dev/flutter/widgets/Row-class.html)

### Day 6: Advanced Layout Techniques

#### Objectives:
- Master scrollable widgets in Flutter
- Learn about responsive layouts
- Implement complex layouts using CustomScrollView

#### Key Topics:
1. ListView and GridView
   - Basic usage
   - Builder patterns for efficiency
   - Custom item builders

2. ScrollView variants
   - SingleChildScrollView
   - PageView
   - TabBarView

3. CustomScrollView and Slivers
   - SliverAppBar
   - SliverList and SliverGrid
   - Custom sliver widgets

4. LayoutBuilder for responsive design
   - Adapting to available space
   - Media queries
   - Orientation-based layouts

#### Sample Code - Advanced Layouts:
```dart
import 'package:flutter/material.dart';

class AdvancedLayoutDemo extends StatelessWidget {
  final List<String> items = List.generate(50, (index) => 'Item ${index + 1}');
  
  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 4,
      child: Scaffold(
        appBar: AppBar(
          title: Text('Advanced Layouts'),
          bottom: TabBar(
            tabs: [
              Tab(text: 'ListView'),
              Tab(text: 'GridView'),
              Tab(text: 'CustomScroll'),
              Tab(text: 'Responsive'),
            ],
          ),
        ),
        body: TabBarView(
          children: [
            // ListView example
            ListView.builder(
              itemCount: items.length,
              itemBuilder: (context, index) {
                return ListTile(
                  leading: CircleAvatar(child: Text('${index + 1}')),
                  title: Text(items[index]),
                  subtitle: Text('Tap for details'),
                  trailing: Icon(Icons.arrow_forward_ios),
                  onTap: () {},
                );
              },
            ),
            
            // GridView example
            GridView.builder(
              gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                crossAxisCount: 3,
                childAspectRatio: 1.0,
                crossAxisSpacing: 10,
                mainAxisSpacing: 10,
              ),
              padding: EdgeInsets.all(10),
              itemCount: items.length,
              itemBuilder: (context, index) {
                return Card(
                  color: Colors.primaries[index % Colors.primaries.length],
                  child: Center(
                    child: Text(
                      '${index + 1}',
                      style: TextStyle(color: Colors.white, fontSize: 24),
                    ),
                  ),
                );
              },
            ),
            
            // CustomScrollView example
            CustomScrollView(
              slivers: <Widget>[
                SliverAppBar(
                  expandedHeight: 200.0,
                  floating: false,
                  pinned: true,
                  flexibleSpace: FlexibleSpaceBar(
                    title: Text('Sliver Example'),
                    background: Image.network(
                      'https://picsum.photos/800/600',
                      fit: BoxFit.cover,
                    ),
                  ),
                ),
                SliverPadding(
                  padding: EdgeInsets.all(8.0),
                  sliver: SliverList(
                    delegate: SliverChildBuilderDelegate(
                      (context, index) {
                        return Card(
                          margin: EdgeInsets.symmetric(
                            vertical: 8.0,
                            horizontal: 4.0,
                          ),
                          child: ListTile(
                            title: Text(items[index]),
                          ),
                        );
                      },
                      childCount: 10,
                    ),
                  ),
                ),
                SliverToBoxAdapter(
                  child: Container(
                    padding: EdgeInsets.all(16.0),
                    color: Colors.amber,
                    child: Text(
                      'SliverGrid Section',
                      style: TextStyle(fontSize: 18),
                    ),
                  ),
                ),
                SliverGrid(
                  gridDelegate: SliverGridDelegateWithMaxCrossAxisExtent(
                    maxCrossAxisExtent: 200.0,
                    mainAxisSpacing: 10.0,
                    crossAxisSpacing: 10.0,
                    childAspectRatio: 1.0,
                  ),
                  delegate: SliverChildBuilderDelegate(
                    (BuildContext context, int index) {
                      return Container(
                        color: Colors.primaries[index % Colors.primaries.length],
                        child: Center(
                          child: Text(
                            'Grid Item ${index + 1}',
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      );
                    },
                    childCount: 20,
                  ),
                ),
              ],
            ),
            
            // Responsive layout with LayoutBuilder
            LayoutBuilder(
              builder: (context, constraints) {
                if (constraints.maxWidth > 600) {
                  // Wide layout (tablet/desktop)
                  return GridView.builder(
                    gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                      crossAxisCount: 3,
                      childAspectRatio: 2.0,
                    ),
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: Column(
                          mainAxisAlignment: MainAxisAlignment.center,
                          children: [
                            Icon(Icons.aspect_ratio, size: 30),
                            Text('Width: ${constraints.maxWidth.toInt()}'),
                            Text('Item $index (Wide Layout)'),
                          ],
                        ),
                      );
                    },
                  );
                } else {
                  // Narrow layout (phone)
                  return ListView.builder(
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: ListTile(
                          leading: Icon(Icons.aspect_ratio),
                          title: Text('Item $index (Narrow Layout)'),
                          subtitle: Text(
                            'Width: ${constraints.maxWidth.toInt()}',
                          ),
                        ),
                      );
                    },
                  );
                }
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [ListView Class](https://api.flutter.dev/flutter/widgets/ListView-class.html)
- [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)
- [Responsive UI in Flutter](https://flutter.dev/docs/development/ui/layout/responsive)

### Day 7: Navigation and Routing

#### Objectives:
- Implement navigation between screens
- Learn different routing approaches
- Pass data between screens

#### Key Topics:
1. Basic Navigation
   - Navigator.push and Navigator.pop
   - MaterialPageRoute
   - CupertinoPageRoute

2. Named Routes
   - Defining routes
   - Navigator.pushNamed
   - Passing arguments

3. Advanced Navigation
   - Deep linking
   - Navigation history manipulation
   - WillPopScope usage

4. Route Transitions
   - Custom transitions
   - Hero animations with navigation
   - Page route builders

#### Sample Code - Navigation:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(NavigationApp());
}

class NavigationApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Navigation Demo',
      // Named routes approach
      initialRoute: '/',
      routes: {
        '/': (context) => HomeScreen(),
        '/details': (context) => DetailScreen(),
        '/settings': (context) => SettingsScreen(),
      },
      // Optional: Custom route handling for dynamic routes or unknown routes
      onGenerateRoute: (settings) {
        if (settings.name!.startsWith('/product/')) {
          final productId = settings.name!.split('/')[2];
          return MaterialPageRoute(
            builder: (context) => ProductScreen(productId: productId),
          );
        }
        return null; // Let onUnknownRoute handle null cases
      },
      onUnknownRoute: (settings) {
        return MaterialPageRoute(
          builder: (context) => NotFoundScreen(),
        );
      },
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            // Basic navigation
            ElevatedButton(
              child: Text('Go to Details (Push)'),
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => DetailScreen(),
                  ),
                );
              },
            ),
            SizedBox(height: 20),
            
            // Named route navigation
            ElevatedButton(
              child: Text('Go to Details (Named)'),
              onPressed: () {
                Navigator.pushNamed(
                  context,
                  '/details',
                );
              },
            ),
            SizedBox(height: 20),
            
            // Passing data with navigation
            ElevatedButton(
              child: Text('Go to Product 123'),
              onPressed: () {
                // Option 1: Generate route dynamically
                Navigator.pushNamed(
                  context,
                  '/product/123',
                );
                
                // Option 2: Pass arguments with named routes
                // Navigator.pushNamed(
                //   context,
                //   '/details',
                //   arguments: {'id': '123', 'title': 'Premium Product'},
                // );
                
                // Option 3: Direct construction with data
                // Navigator.push(
                //   context,
                //   MaterialPageRoute(
                //     builder: (context) => ProductScreen(productId: '123'),
                //   ),
                // );
              },
            ),
            SizedBox(height: 20),
            
            // Settings screen
            ElevatedButton(
              child: Text('Settings'),
              onPressed: () {
                Navigator.pushNamed(context, '/settings');
              },
            ),
          ],
        ),
      ),
    );
  }
}

class DetailScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Retrieve arguments if passed
    final args = ModalRoute.of(context)!.settings.arguments as Map<String, dynamic>?;
    
    return Scaffold(
      appBar: AppBar(title: Text('Detail Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            if (args != null) Text('Arguments: $args'),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go Back'),
              onPressed: () {
                Navigator.pop(context);
              },
            ),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go to Home (replacement)'),
              onPressed: () {
                Navigator.pushReplacementNamed(context, '/');
              },
            ),
          ],
        ),
      ),
    );
  }
}

class ProductScreen extends StatelessWidget {
  final String productId;
  
  ProductScreen({required this.productId});
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Product Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Product ID: $productId', style: TextStyle(fontSize: 24)),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go Back'),
              onPressed: () {
                Navigator.pop(context);
              },
            ),
          ],
        ),
      ),
    );
  }
}

class SettingsScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return WillPopScope(
      // Control the back button behavior
      onWillPop: () async {
        // Show confirmation dialog
        bool shouldPop = await showDialog(
          context: context,
          builder: (context) => AlertDialog(
            title: Text('Confirm'),
            content: Text('Do you want to leave settings?'),
            actions: [
              TextButton(
                onPressed: () => Navigator.of(context).pop(false),
                child: Text('No'),
              ),
              TextButton(
                onPressed: () => Navigator.of(context).pop(true),
                child: Text('Yes'),
              ),
            ],
          ),
        ) ?? false;
        
        return shouldPop;
      },
      child: Scaffold(
        appBar: AppBar(title: Text('Settings')),
        body: Center(
          child: Text('Settings Screen'),
        ),
      ),
    );
  }
}

class NotFoundScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Page Not Found')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(Icons.error_outline, size: 80, color: Colors.red),
            SizedBox(height: 20),
            Text('The requested page was not found.'),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go to Home'),
              onPressed: () {
                Navigator.pushReplacementNamed(context, '/');
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Navigation basics](https://flutter.dev/docs/cookbook/navigation/navigation-basics)
- [Named routes](https://flutter.dev/docs/cookbook/navigation/named-routes)
- [Navigate with arguments](https://flutter.dev/docs/cookbook/navigation/navigate-with-arguments)
- [Return data from a screen](https://flutter.dev/docs/cookbook/navigation/returning-data)

## Week 2: UI Components & User Input

### Day 8: Input Widgets

#### Objectives:
- Learn how to use various input widgets
- Implement form validation
- Work with user input

#### Key Topics:
1. TextField and TextFormField
   - Basic usage
   - Input decoration
   - Keyboard types
   - Focus nodes

2. Form validation
   - Form widget
   - FormState and GlobalKey
   - Validation logic
   - Error messages

3. Selection Widgets
   - Checkbox and CheckboxListTile
   - Radio and RadioListTile
   - Switch and SwitchListTile
   - DropdownButton

4. Value Pickers
   - Slider
   - Date and time pickers
   - Range selectors

#### Sample Code - Form With Validation:
```dart
import 'package:flutter/material.dart';

class FormExample extends StatefulWidget {
  @override
  _FormExampleState createState() => _FormExampleState();
}

class _FormExampleState extends State<FormExample> {
  final _formKey = GlobalKey<FormState>();
  final TextEditingController _nameController = TextEditingController();
  final TextEditingController _emailController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();
  
  String? _selectedGender;
  bool _agreeToTerms = false;
  double _ageValue = 18;
  DateTime _selectedDate = DateTime.now();
  
  Future<void> _selectDate(BuildContext context) async {
    final DateTime? picked = await showDatePicker(
      context: context,
      initialDate: _selectedDate,
      firstDate: DateTime(1900),
      lastDate: DateTime.now(),
    );
    if (picked != null && picked != _selectedDate) {
      setState(() {
        _selectedDate = picked;
      });
    }
  }
  
  @override
  void dispose() {
    _nameController.dispose();
    _emailController.dispose();
    _passwordController.dispose();
    super.dispose();
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Input Widgets')),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Form(
          key: _formKey,
          child: SingleChildScrollView(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                // Name field
                TextFormField(
                  controller: _nameController,
                  decoration: InputDecoration(
                    labelText: 'Full Name',
                    hintText: 'Enter your full name',
                    prefixIcon: Icon(Icons.person),
                    border: OutlineInputBorder(),
                  ),
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter your name';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 16),
                
                // Email field
                TextFormField(
                  controller: _emailController,
                  decoration: InputDecoration(
                    labelText: 'Email',
                    hintText: 'Enter your email',
                    prefixIcon: Icon(Icons.email),
                    border: OutlineInputBorder(),
                  ),
                  keyboardType: TextInputType.emailAddress,
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter your email';
                    }
                    if (!RegExp(r'^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$')
                        .hasMatch(value)) {
                      return 'Please enter a valid email';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 16),
                
                // Password field
                TextFormField(
                  controller: _passwordController,
                  decoration: InputDecoration(
                    labelText: 'Password',
                    hintText: 'Enter your password',
                    prefixIcon: Icon(Icons.lock),
                    border: OutlineInputBorder(),
                  ),
                  obscureText: true,
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter a password';
                    }
                    if (value.length < 6) {
                      return 'Password must be at least 6 characters';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 24),
                
                // Gender selection with Radio
                Text('Gender:', style: TextStyle(fontSize: 16)),
                RadioListTile<String>(
                  title: Text('Male'),
                  value: 'male',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                RadioListTile<String>(
                  title: Text('Female'),
                  value: 'female',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                RadioListTile<String>(
                  title: Text('Other'),
                  value: 'other',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                SizedBox(height: 16),
                
                // Age slider
                Text('Age: ${_ageValue.round()}', style: TextStyle(fontSize: 16)),
                Slider(
                  value: _ageValue,
                  min: 1,
                  max: 100,
                  divisions: 99,
                  label: _ageValue.round().toString(),
                  onChanged: (value) {
                    setState(() {
                      _ageValue = value;
                    });
                  },
                ),
                SizedBox(height: 16),
                
                // Date picker
                Row(
                  children: [
                    Text('Date of Birth: ${_selectedDate.toLocal().toString().split(' ')[0]}'),
                    Spacer(),
                    ElevatedButton(
                      onPressed: () => _selectDate(context),
                      child: Text('Select Date'),
                    ),
                  ],
                ),
                SizedBox(height: 24),
                
                // Terms and conditions checkbox
                CheckboxListTile(
                  title: Text('I agree to the terms and conditions'),
                  value: _agreeToTerms,
                  onChanged: (value) {
                    setState(() {
                      _agreeToTerms = value ?? false;
                    });
                  },
                  controlAffinity: ListTileControlAffinity.leading,
                ),
                SizedBox(height: 24),
                
                // Submit button
                Center(
                  child: ElevatedButton(
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(200, 50),
                    ),
                    onPressed: () {
                      if (_formKey.currentState!.validate() && _agreeToTerms) {
                        // Form is valid, process the data
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(content: Text('Processing Data')),
                        );
                      } else if (!_agreeToTerms) {
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(
                            content: Text('Please agree to the terms and conditions'),
                            backgroundColor: Colors.red,
                          ),
                        );
                      }
                    },
                    child: Text('Submit', style: TextStyle(fontSize: 18)),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Forms in Flutter](https://flutter.dev/docs/cookbook/forms)
- [TextFormField class](https://api.flutter.dev/flutter/material/TextFormField-class.html)
- [DateTime picker](https://flutter.dev/docs/cookbook/forms/datetime-picker)
- [Form validation](https://flutter.dev/docs/cookbook/forms/validation)

### Day 9: Dialogs and Alerts

#### Objectives:
- Learn how to display dialogs and alerts
- Implement different types of user notifications
- Get user confirmation for actions

#### Key Topics:
1. AlertDialog
   - Basic alert dialogs
   - Confirmation dialogs
   - Custom dialog content

2. SimpleDialog
   - Option selection
   - Custom content
   - Dialog results

3. BottomSheet and ModalBottomSheet
   - Persistent bottom sheets
   - Modal bottom sheets
   - Draggable bottom sheets

4. Snackbar and Toast
   - Showing temporary messages
   - Action buttons
   - Styling notifications

5. Progress Indicators
   - Linear progress
   - Circular progress
   - Indeterminate progress

#### Sample Code - Dialogs and Notifications:
```dart
import 'package:flutter/material.dart';

class DialogsExample extends StatefulWidget {
  @override
  _DialogsExampleState createState() => _DialogsExampleState();
}

class _DialogsExampleState extends State<DialogsExample> {
  String _selectedOption = 'None';
  double _progress = 0.0;
  
  // Simple Alert Dialog
  Future<void> _showAlertDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(
          title: Text('Alert Dialog'),
          content: Text('This is a simple alert dialog.'),
          actions: [
            TextButton(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('Close'),
            ),
          ],
        );
      },
    );
  }
  
  // Confirmation Dialog
  Future<void> _showConfirmationDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(
          title: Text('Confirm Action'),
          content: Text('Are you sure you want to perform this action?'),
          actions: [
            TextButton(
              onPressed: () {
                Navigator.of(context).pop('Cancel');
              },
              child: Text('Cancel'),
            ),
            TextButton(
              onPressed: () {
                Navigator.of(context).pop('Confirm');
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Action confirmed!')),
                );
              },
              child: Text('Confirm'),
            ),
          ],
        );
      },
    );
  }
  
  // Simple Dialog with options
  Future<void> _showSimpleDialog() async {
    String? result = await showDialog<String>(
      context: context,
      builder: (BuildContext context) {
        return SimpleDialog(
          title: Text('Select an option'),
          children: [
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 1');
              },
              child: Text('Option 1'),
            ),
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 2');
              },
              child: Text('Option 2'),
            ),
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 3');
              },
              child: Text('Option 3'),
            ),
          ],
        );
      },
    );
    
    if (result != null) {
      setState(() {
        _selectedOption = result;
      });
      ScaffoldMessenger.of(context).showSnackBar(
        SnackBar(content: Text('Selected: $result')),
      );
    }
  }
  
  // Custom Dialog
  Future<void> _showCustomDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return Dialog(
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(20.0),
          ),
          child: Container(
            height: 250,
            padding: EdgeInsets.all(20),
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                Icon(Icons.check_circle, color: Colors.green, size: 60),
                SizedBox(height: 20),
                Text(
                  'Success!',
                  style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Text('Your operation was completed successfully.'),
                SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    Navigator.of(context).pop();
                  },
                  child: Text('Close'),
                  style: ElevatedButton.styleFrom(
                    minimumSize: Size(150, 40),
                  ),
                ),
              ],
            ),
          ),
        );
      },
    );
  }
  
  // Modal Bottom Sheet
  void _showModalBottomSheet() {
    showModalBottomSheet(
      context: context,
      isScrollControlled: true,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.vertical(top: Radius.circular(20)),
      ),
      builder: (BuildContext context) {
        return DraggableScrollableSheet(
          initialChildSize: 0.5,
          minChildSize: 0.3,
          maxChildSize: 0.9,
          expand: false,
          builder: (context, scrollController) {
            return Container(
              padding: EdgeInsets.all(16),
              child: ListView(
                controller: scrollController,
                children: [
                  Center(
                    child: Container(
                      width: 40,
                      height: 5,
                      margin: EdgeInsets.only(bottom: 20),
                      decoration: BoxDecoration(
                        color: Colors.grey[300],
                        borderRadius: BorderRadius.circular(10),
                      ),
                    ),
                  ),
                  Text(
                    'Modal Bottom Sheet',
                    style: TextStyle(fontSize: 22, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 16),
                  Text(
                    'This is a modal bottom sheet with draggable functionality.',
                    style: TextStyle(fontSize: 16),
                  ),
                  SizedBox(height: 16),
                  for (int i = 1; i <= 20; i++)
                    ListTile(
                      leading: CircleAvatar(child: Text('$i')),
                      title: Text('Item $i'),
                      subtitle: Text('Description for item $i'),
                      onTap: () {
                        Navigator.pop(context);
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(content: Text('Selected item $i')),
                        );
                      },
                    ),
                ],
              ),
            );
          },
        );
      },
    );
  }
  
  // Show a Snackbar
  void _showSnackBar() {
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(
        content: Text('This is a snackbar message'),
        action: SnackBarAction(
          label: 'Undo',
          onPressed: () {
            // Undo action
          },
        ),
        duration: Duration(seconds: 3),
        behavior: SnackBarBehavior.floating,
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(10),
        ),
      ),
    );
  }
  
  // Show progress dialog
  void _showProgressDialog() {
    setState(() {
      _progress = 0.0;
    });
    
    showDialog(
      context: context,
      barrierDismissible: false,
      builder: (BuildContext context) {
        return StatefulBuilder(
          builder: (context, setState) {
            // Simulate progress
            Future.delayed(Duration(milliseconds: 500), () {
              if (_progress < 1.0) {
                setState(() {
                  _progress += 0.1;
                });
                
                if (_progress >= 1.0) {
                  Navigator.of(context).pop();
                  _showCustomDialog();
                }
              }
            });
            
            return AlertDialog(
              title: Text('Loading...'),
              content: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  LinearProgressIndicator(value: _progress),
                  SizedBox(height: 16),
                  Text('${(_progress * 100).toInt()}%'),
                ],
              ),
            );
          },
        );
      },
    );
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Dialogs and Alerts')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Selected Option: $_selectedOption', style: TextStyle(fontSize: 16)),
            SizedBox(height: 30),
            ElevatedButton(
              onPressed: _showAlertDialog,
              child: Text('Show Alert Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showConfirmationDialog,
              child: Text('Show Confirmation Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showSimpleDialog,
              child: Text('Show Simple Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showCustomDialog,
              child: Text('Show Custom Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showModalBottomSheet,
              child: Text('Show Modal Bottom Sheet'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showSnackBar,
              child: Text('Show Snackbar'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showProgressDialog,
              child: Text('Show Progress Dialog'),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Dialogs](https://flutter.dev/docs/cookbook/design/dialogs)
- [SnackBars](https://flutter.dev/docs/cookbook/design/snackbars)
- [Bottom Sheets](https://api.flutter.dev/flutter/material/showModalBottomSheet.html)
- [Progress Indicators](https://flutter.dev/docs/cookbook/forms/progress-indicator)

### Day 10: Custom Widgets

#### Objectives:
- Learn how to create reusable widgets
- Understand widget lifecycle
- Master widget composition

#### Key Topics:
1. Creating Custom Widgets
   - Composition patterns
   - Property passing
   - Callback functions

2. Widget Lifecycle
   - initState and dispose
   - didChangeDependencies
   - didUpdateWidget

3. Stateful Widget Internals
   - State creation and management
   - Widget rebuilding optimization
   - StatefulWidget vs StatelessWidget trade-offs

4. Keys in Flutter
   - Understanding widget identity
   - ValueKey, ObjectKey, UniqueKey
   - GlobalKey usage

#### Sample Code - Custom Widgets:
```dart
import 'package:flutter/material.dart';

// 1. Simple Custom Widget (Stateless)
class CustomCard extends StatelessWidget {
  final String title;
  final String subtitle;
  final IconData icon;
  final VoidCallback? onTap;
  
  const CustomCard({
    Key? key,
    required this.title,
    required this.subtitle,
    required this.icon,
    this.onTap,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 4,
      margin: EdgeInsets.symmetric(vertical: 8, horizontal: 16),
      child: ListTile(
        leading: Icon(icon, size: 32, color: Theme.of(context).primaryColor),
        title: Text(title, style: TextStyle(fontWeight: FontWeight.bold)),
        subtitle: Text(subtitle),
        trailing: Icon(Icons.arrow_forward_ios),
        onTap: onTap,
      ),
    );
  }
}

// 2. Advanced Custom Widget (Stateful with lifecycle methods)
class CountdownTimer extends StatefulWidget {
  final int duration; // in seconds
  final Function()? onComplete;
  
  const CountdownTimer({
    Key? key,
    required this.duration,
    this.onComplete,
  }) : super(key: key);
  
  @override
  _CountdownTimerState createState() => _CountdownTimerState();
}

class _CountdownTimerState extends State<CountdownTimer> {
  late int _secondsRemaining;
  late bool _isRunning;
  
  @override
  void initState() {
    super.initState();
    _secondsRemaining = widget.duration;
    _isRunning = false;
    print('CountdownTimer: initState called');
  }
  
  @override
  void didChangeDependencies() {
    super.didChangeDependencies();
    print('CountdownTimer: didChangeDependencies called');
    // Called when inherited dependencies change
  }
  
  @override
  void didUpdateWidget(CountdownTimer oldWidget) {
    super.didUpdateWidget(oldWidget);
    print('CountdownTimer: didUpdateWidget called');
    
    // Reset timer if duration changed
    if (oldWidget.duration != widget.duration) {
      setState(() {
        _secondsRemaining = widget.duration;
        _isRunning = false;
      });
    }
  }
  
  @override
  void dispose() {
    print('CountdownTimer: dispose called');
    super.dispose();
  }
  
  void _startTimer() {
    setState(() {
      _isRunning = true;
    });
    
    Future.doWhile(() async {
      await Future.delayed(Duration(seconds: 1));
      
      if (!mounted) return false;
      
      setState(() {
        if (_secondsRemaining > 0) {
          _secondsRemaining--;
        }
        
        if (_secondsRemaining <= 0) {
          _isRunning = false;
          if (widget.onComplete != null) {
            widget.onComplete!();
          }
        }
      });
      
      return _isRunning && _secondsRemaining > 0;
    });
  }
  
  void _resetTimer() {
    setState(() {
      _secondsRemaining = widget.duration;
      _isRunning = false;
    });
  }
  
  String _formatTime() {
    int minutes = _secondsRemaining ~/ 60;
    int seconds = _secondsRemaining % 60;
    return '$minutes:${seconds.toString().padLeft(2, '0')}';
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Text(
              'Countdown Timer',
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            Text(
              _formatTime(),
              style: TextStyle(
                fontSize: 48,
                fontWeight: FontWeight.bold,
                color: _secondsRemaining < 10 ? Colors.red : Colors.black,
              ),
            ),
            SizedBox(height: 16),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: _isRunning ? null : _startTimer,
                  child: Text(_isRunning ? 'Running' : 'Start'),
                ),
                SizedBox(width: 16),
                ElevatedButton(
                  onPressed: _resetTimer,
                  child: Text('Reset'),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// 3. Widget with custom painter
class CircularProgressWidget extends StatelessWidget {
  final double progress; // 0.0 to 1.0
  final double size;
  final Color color;
  
  const CircularProgressWidget({
    Key? key,
    required this.progress,
    this.size = 100,
    this.color = Colors.blue,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return Container(
      width: size,
      height: size,
      child: CustomPaint(
        painter: CircularProgressPainter(
          progress: progress,
          color: color,
        ),
        child: Center(
          child: Text(
            '${(progress * 100).toInt()}%',
            style: TextStyle(
              fontWeight: FontWeight.bold,
              fontSize: size / 5,
            ),
          ),
        ),
      ),
    );
  }
}

class CircularProgressPainter extends CustomPainter {
  final double progress;
  final Color color;
  
  CircularProgressPainter({
    required this.progress,
    required this.color,
  });
  
  @override
  void paint(Canvas canvas, Size size) {
    // Background circle
    final Paint backgroundPaint = Paint()
      ..color = Colors.grey.shade300
      ..style = PaintingStyle.stroke
      ..strokeWidth = size.width / 15;
    
    final Offset center = Offset(size.width / 2, size.height / 2);
    final double radius = (size.width - backgroundPaint.strokeWidth) / 2;
    
    canvas.drawCircle(center, radius, backgroundPaint);
    
    // Progress arc
    final Paint progressPaint = Paint()
      ..color = color
      ..style = PaintingStyle.stroke
      ..strokeWidth = size.width / 15
      ..strokeCap = StrokeCap.round;
    
    final double sweepAngle = 2 * 3.14159 * progress;
    
    canvas.drawArc(
      Rect.fromCircle(center: center, radius: radius),
      -3.14159 / 2, // Start at top
      sweepAngle,
      false,
      progressPaint,
    );
  }
  
  @override
  bool shouldRepaint(CircularProgressPainter oldDelegate) {
    return oldDelegate.progress != progress || oldDelegate.color != color;
  }
}

// Usage example for custom widgets
class CustomWidgetsExample extends StatefulWidget {
  @override
  _CustomWidgetsExampleState createState() => _CustomWidgetsExampleState();
}

class _CustomWidgetsExampleState extends State<CustomWidgetsExample> {
  double _progress = 0.7;
  int _timerDuration = 30;
  
  void _timerComplete() {
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(content: Text('Timer completed!')),
    );
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Custom Widgets')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('1. Custom Card Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 8),
            CustomCard(
              title: 'Weather',
              subtitle: 'Sunny, 25°C',
              icon: Icons.wb_sunny,
              onTap: () {
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Weather card tapped')),
                );
              },
            ),
            CustomCard(
              title: 'Calendar',
              subtitle: 'Meeting at 2:00 PM',
              icon: Icons.calendar_today,
              onTap: () {
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Calendar card tapped')),
                );
              },
            ),
            
            Divider(height: 32),
            
            Text('2. Stateful Countdown Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 8),
            CountdownTimer(
              key: ValueKey(_timerDuration),
              duration: _timerDuration,
              onComplete: _timerComplete,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 10;
                    });
                  },
                  child: Text('Set 10s'),
                ),
                SizedBox(width: 8),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 30;
                    });
                  },
                  child: Text('Set 30s'),
                ),
                SizedBox(width: 8),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 60;
                    });
                  },
                  child: Text('Set 60s'),
                ),
              ],
            ),
            
            Divider(height: 32),
            
            Text('3. Custom Painter Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 16),
            Center(
              child: CircularProgressWidget(progress: _progress),
            ),
            SizedBox(height: 16),
            Slider(
              value: _progress,
              min: 0.0,
              max: 1.0,
              divisions: 100,
              label: '${(_progress * 100).toInt()}%',
              onChanged: (value) {
                setState(() {
                  _progress = value;
                });
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Widget lifecycle](https://flutterbyexample.com/lesson/stateful-widget-lifecycle)
- [Custom Painters](https://flutter.dev/docs/development/ui/advanced/custom-painters)
- [Using keys](https://flutter.dev/docs/development/ui/widgets-intro#keys)
- [Flutter widget of the week videos](https://www.youtube.com/playlist?list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG)

### Day 11: Themes and Styling

#### Objectives:
- Master Flutter's theming system
- Create consistent app styling
- Implement light and dark themes

#### Key Topics:
1. ThemeData Basics
   - Using MaterialApp theme property
   - Color schemes and palettes
   - Typography and text themes

2. Creating Custom Themes
   - Light and dark themes
   - Extending existing themes
   - Theme controllers

3. Using Theme in Widgets
   - Theme.of(context)
   - Accessing theme properties
   - Theme consistency

4. Material Design Guidelines
   - Following Material Design
   - Custom theme extensions
   - Design system implementation

#### Sample Code - Theme Implementation:
```dart
import 'package:flutter/material.dart';

// Define our app theme data
class AppTheme {
  // Light theme
  static ThemeData lightTheme = ThemeData(
    brightness: Brightness.light,
    primarySwatch: Colors.blue,
    colorScheme: ColorScheme.light(
      primary: Colors.blue,
      secondary: Colors.blueAccent,
      surface: Colors.white,
      background: Color(0xFFF5F5F5),
      error: Colors.red,
    ),
    appBarTheme: AppBarTheme(
      backgroundColor: Colors.blue,
      foregroundColor: Colors.white,
      elevation: 4,
    ),
    cardTheme: CardTheme(
      elevation: 2,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(12),
      ),
    ),
    inputDecorationTheme: InputDecorationTheme(
      filled: true,
      fillColor: Colors.grey[100],
      border: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide.none,
      ),
      enabledBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.grey[300]!),
      ),
      focusedBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.blue, width: 2),
      ),
      contentPadding: EdgeInsets.symmetric(horizontal: 16, vertical: 16),
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textTheme: TextTheme(
      displayLarge: TextStyle(
        fontSize: 28,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      displayMedium: TextStyle(
        fontSize: 24,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      displaySmall: TextStyle(
        fontSize: 20,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      headlineMedium: TextStyle(
        fontSize: 18,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      bodyLarge: TextStyle(
        fontSize: 16,
        color: Colors.black87,
      ),
      bodyMedium: TextStyle(
        fontSize: 14,
        color: Colors.black87,
      ),
    ),
    dividerTheme: DividerThemeData(
      space: 24,
      thickness: 1,
      color: Colors.grey[300],
    ),
  );

  // Dark theme
  static ThemeData darkTheme = ThemeData(
    brightness: Brightness.dark,
    primarySwatch: Colors.indigo,
    colorScheme: ColorScheme.dark(
      primary: Colors.indigo,
      secondary: Colors.indigoAccent,
      surface: Color(0xFF1E1E1E),
      background: Color(0xFF121212),
      error: Colors.redAccent,
    ),
    scaffoldBackgroundColor: Color(0xFF121212),
    appBarTheme: AppBarTheme(
      backgroundColor: Color(0xFF1E1E1E),
      elevation: 0,
    ),
    cardTheme: CardTheme(
      color: Color(0xFF1E1E1E),
      elevation: 8,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(12),
      ),
    ),
    inputDecorationTheme: InputDecorationTheme(
      filled: true,
      fillColor: Color(0xFF2C2C2C),
      border: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide.none,
      ),
      enabledBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.grey[700]!),
      ),
      focusedBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.indigo, width: 2),
      ),
      contentPadding: EdgeInsets.symmetric(horizontal: 16, vertical: 16),
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        backgroundColor: Colors.indigo,
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        foregroundColor: Colors.indigo[300],
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textTheme: TextTheme(
      displayLarge: TextStyle(
        fontSize: 28,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      displayMedium: TextStyle(
        fontSize: 24,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      displaySmall: TextStyle(
        fontSize: 20,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      headlineMedium: TextStyle(
        fontSize: 18,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      bodyLarge: TextStyle(
        fontSize: 16,
        color: Colors.white70,
      ),
      bodyMedium: TextStyle(
        fontSize: 14,
        color: Colors.white70,
      ),
    ),
    dividerTheme: DividerThemeData(
      space: 24,
      thickness: 1,
      color: Colors.grey[800],
    ),
    iconTheme: IconThemeData(
      color: Colors.grey[400],
    ),
  );
}

// Theme Switcher with Provider pattern
class ThemeProvider extends ChangeNotifier {
  ThemeMode _themeMode = ThemeMode.light;
  
  ThemeMode get themeMode => _themeMode;
  
  bool get isDarkMode => _themeMode == ThemeMode.dark;
  
  void toggleTheme() {
    _themeMode = isDarkMode ? ThemeMode.light : ThemeMode.dark;
    notifyListeners();
  }
}

// Example app using themes
class ThemeExample extends StatelessWidget {
  final ThemeProvider themeProvider;
  
  ThemeExample({required this.themeProvider});
  
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Theme Example',
      theme: AppTheme.lightTheme,
      darkTheme: AppTheme.darkTheme,
      themeMode: themeProvider.themeMode,
      home: ThemeShowcaseScreen(themeProvider: themeProvider),
    );
  }
}

class ThemeShowcaseScreen extends StatelessWidget {
  final ThemeProvider themeProvider;
  
  ThemeShowcaseScreen({required this.themeProvider});
  
  @override
  Widget build(BuildContext context) {
    final theme = Theme.of(context);
    
    return Scaffold(
      appBar: AppBar(
        title: Text('Theme Showcase'),
        actions: [
          IconButton(
            icon: Icon(
              themeProvider.isDarkMode ? Icons.light_mode : Icons.dark_mode,
            ),
            onPressed: themeProvider.toggleTheme,
          ),
        ],
      ),
      body: SingleChildScrollView(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Typography',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Text(
              'Display Large',
              style: theme.textTheme.displayLarge,
            ),
            Text(
              'Display Medium',
              style: theme.textTheme.displayMedium,
            ),
            Text(
              'Display Small',
              style: theme.textTheme.displaySmall,
            ),
            Text(
              'Headline Medium',
              style: theme.textTheme.headlineMedium,
            ),
            Text(
              'Body Large',
              style: theme.textTheme.bodyLarge,
            ),
            Text(
              'Body Medium',
              style: theme.textTheme.bodyMedium,
            ),
            
            Divider(),
            
            Text(
              'Buttons',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated'),
                ),
                TextButton(
                  onPressed: () {},
                  child: Text('Text'),
                ),
                OutlinedButton(
                  onPressed: () {},
                  child: Text('Outlined'),
                ),
              ],
            ),
            
            Divider(),
            
            Text(
              'Input Fields',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            TextField(
              decoration: InputDecoration(
                labelText: 'Username',
                hintText: 'Enter your username',
                prefixIcon: Icon(Icons.person),
              ),
            ),
            SizedBox(height: 16),
            TextField(
              obscureText: true,
              decoration: InputDecoration(
                labelText: 'Password',
                hintText: 'Enter your password',
                prefixIcon: Icon(Icons.lock),
              ),
            ),
            
            Divider(),
            
            Text(
              'Cards',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Card(
              child: Padding(
                padding: const EdgeInsets.all(16.0),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Card Title',
                      style: theme.textTheme.headlineMedium,
                    ),
                    SizedBox(height: 8),
                    Text(
                      'This is a card with some content. Cards are surface components that display content and actions on a single topic.',
                      style: theme.textTheme.bodyMedium,
                    ),
                    SizedBox(height: 16),
                    Row(
                      mainAxisAlignment: MainAxisAlignment.end,
                      children: [
                        TextButton(
                          onPressed: () {},
                          child: Text('CANCEL'),
                        ),
                        SizedBox(width: 8),
                        ElevatedButton(
                          onPressed: () {},
                          child: Text('CONFIRM'),
                        ),
                      ],
                    ),
                  ],
                ),
              ),
            ),
            
            Divider(),
            
            Text(
              'Colors',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Row(
              children: [
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.primary,
                    name: 'Primary',
                  ),
                ),
                SizedBox(width: 8),
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.secondary,
                    name: 'Secondary',
                  ),
                ),
              ],
            ),
            SizedBox(height: 8),
            Row(
              children: [
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.surface,
                    name: 'Surface',
                    textColor: theme.brightness == Brightness.dark
                        ? Colors.white
                        : Colors.black,
                  ),
                ),
                SizedBox(width: 8),
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.background,
                    name: 'Background',
                    textColor: theme.brightness == Brightness.dark
                        ? Colors.white
                        : Colors.black,
                  ),
                ),
              ],
            ),
            SizedBox(height: 8),
            _ColorBox(
              color: theme.colorScheme.error,
              name: 'Error',
            ),
          ],
        ),
      ),
    );
  }
}

class _ColorBox extends StatelessWidget {
  final Color color;
  final String name;
  final Color? textColor;
  
  const _ColorBox({
    required this.color,
    required this.name,
    this.textColor = Colors.white,
  });
  
  @override
  Widget build(BuildContext context) {
    return Container(
      height: 80,
      decoration: BoxDecoration(
        color: color,
        borderRadius: BorderRadius.circular(8),
      ),
      alignment: Alignment.center,
      child: Text(
        name,
        style: TextStyle(
          color: textColor,
          fontWeight: FontWeight.bold,
        ),
      ),
    );
  }
}

### Day 12: Assets and Images

#### Objectives:
- Learn how to work with assets in Flutter
- Understand image loading and optimization
- Implement image caching and placeholders

#### Key Topics:
1. Adding Assets to Your App
   - pubspec.yaml asset declaration
   - Asset folder structure
   - Accessing assets in code

2. Image Types and Formats
   - Local vs network images
   - Image resolution and variants
   - SVG and vector graphics

3. Image Widgets
   - Image widget
   - FadeInImage for smooth loading
   - Hero animations with images

4. Image Optimization
   - Caching strategies
   - Responsive images
   - Performance considerations

#### Sample Code - Working with Assets and Images:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_svg/flutter_svg.dart';
import 'package:cached_network_image/cached_network_image.dart';

class AssetsExample extends StatelessWidget {
  // Sample image URLs for demonstration
  final List<String> networkImages = [
    'https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1600054800747-be294a6a0d26?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1567306226408-c0fe0c9662ea?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1488590528505-98d2b5aba04b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
  ];
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Assets and Images')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // 1. Local Asset Images
            Text(
              '1. Local Asset Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            Text(
              'Basic Image.asset():',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: Image.asset(
                'assets/images/flutter_logo.png',
                width: 150,
                height: 150,
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'Asset Image with BoxFit:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                _ImageWithLabel(
                  label: 'contain',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.contain,
                  ),
                ),
                _ImageWithLabel(
                  label: 'cover',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                _ImageWithLabel(
                  label: 'fill',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.fill,
                  ),
                ),
              ],
            ),
            SizedBox(height: 24),
            
            // 2. Network Images
            Text(
              '2. Network Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            
            Text(
              'Basic Image.network():',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: Image.network(
                networkImages[0],
                width: 200,
                height: 150,
                loadingBuilder: (context, child, loadingProgress) {
                  if (loadingProgress == null) return child;
                  return Center(
                    child: CircularProgressIndicator(
                      value: loadingProgress.expectedTotalBytes != null
                          ? loadingProgress.cumulativeBytesLoaded /
                              loadingProgress.expectedTotalBytes!
                          : null,
                    ),
                  );
                },
                errorBuilder: (context, error, stackTrace) {
                  return Container(
                    width: 200,
                    height: 150,
                    color: Colors.grey[300],
                    child: Center(
                      child: Icon(
                        Icons.error_outline,
                        color: Colors.red,
                        size: 40,
                      ),
                    ),
                  );
                },
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'FadeInImage with placeholder:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: FadeInImage.assetNetwork(
                placeholder: 'assets/images/image_placeholder.png',
                image: networkImages[1],
                width: 200,
                height: 150,
                fit: BoxFit.cover,
                fadeInDuration: Duration(milliseconds: 700),
                fadeInCurve: Curves.easeIn,
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'CachedNetworkImage with caching:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: CachedNetworkImage(
                imageUrl: networkImages[2],
                width: 200,
                height: 150,
                fit: BoxFit.cover,
                placeholder: (context, url) => Container(
                  color: Colors.grey[300],
                  child: Center(
                    child: CircularProgressIndicator(),
                  ),
                ),
                errorWidget: (context, url, error) => Container(
                  color: Colors.grey[300],
                  child: Center(
                    child: Icon(
                      Icons.error_outline,
                      color: Colors.red,
                      size: 40,
                    ),
                  ),
                ),
              ),
            ),
            SizedBox(height: 24),
            
            // 3. SVG Images
            Text(
              '3. SVG Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            Center(
              child: SvgPicture.asset(
                'assets/images/flutter_logo.svg',
                width: 150,
                height: 150,
              ),
            ),
            SizedBox(height: 24),
            
            // 4. Image Manipulation
            Text(
              '4. Image Manipulation',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            
            Text(
              'Circular images:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Method 1: Using ClipRRect
                ClipRRect(
                  borderRadius: BorderRadius.circular(75),
                  child: Image.network(
                    networkImages[3],
                    width: 150,
                    height: 150,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Method 2: Using Container and BoxDecoration
                Container(
                  width: 150,
                  height: 150,
                  decoration: BoxDecoration(
                    shape: BoxShape.circle,
                    image: DecorationImage(
                      image: NetworkImage(networkImages[3]),
                      fit: BoxFit.cover,
                    ),
                  ),
                ),
              ],
            ),
            SizedBox(height: 16),
            
            Text(
              'Color filters and effects:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Grayscale
                ColorFiltered(
                  colorFilter: ColorFilter.mode(
                    Colors.grey,
                    BlendMode.saturation,
                  ),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Sepia-like
                ColorFiltered(
                  colorFilter: ColorFilter.matrix([
                    0.393, 0.769, 0.189, 0, 0,
                    0.349, 0.686, 0.168, 0, 0,
                    0.272, 0.534, 0.131, 0, 0,
                    0,     0,     0,     1, 0,
                  ]),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Inverted
                ColorFiltered(
                  colorFilter: ColorFilter.matrix([
                    -1,  0,  0, 0, 255,
                     0, -1,  0, 0, 255,
                     0,  0, -1, 0, 255,
                     0,  0,  0, 1,   0,
                  ]),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// Helper widget for displaying images with labels
class _ImageWithLabel extends StatelessWidget {
  final String label;
  final Widget child;
  
  const _ImageWithLabel({
    required this.label,
    required this.child,
# Flutter Complete Learning Path - From Zero to Hero

> Last updated for Flutter 3.29.2 • Dart 3.7.2

A comprehensive 56-day learning journey to master Flutter development. This repository provides a structured path for learning Flutter from basics to advanced topics.

## Table of Contents

- [Week 1: Fundamentals](#week-1-fundamentals)
- [Week 2: UI Components & User Input](#week-2-ui-components--user-input)
- [Week 3: State Management](#week-3-state-management)
- [Week 4: Data Management & Backend](#week-4-data-management--backend)
- [Week 5: Advanced Flutter](#week-5-advanced-flutter)
- [Week 6: Performance & Deployment](#week-6-performance--deployment)
- [Week 7: Specialized Topics](#week-7-specialized-topics)
- [Week 8: Advanced Architectures and Mastery](#week-8-advanced-architectures-and-mastery)

## Week 1: Fundamentals

### Day 1: Setting Up Flutter Environment

#### Objectives:
- Install Flutter SDK and set up your development environment
- Run your first Flutter application
- Understand the Flutter project structure

#### Key Tasks:
1. Install Flutter SDK from [flutter.dev](https://flutter.dev)
2. Set up Android Studio/VS Code with Flutter and Dart plugins
3. Configure Android emulator/iOS simulator
4. Run `flutter doctor` to verify installation
5. Create and run a basic Flutter app with `flutter create my_app`

#### Sample Code - Basic Flutter App:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My First Flutter App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Installation Guide](https://flutter.dev/docs/get-started/install)
- [Set up an Editor](https://flutter.dev/docs/get-started/editor)
- [Test Drive](https://flutter.dev/docs/get-started/test-drive)

### Day 2: Dart Language Basics

#### Objectives:
- Learn fundamental Dart programming concepts
- Understand variables, data types, and control flow
- Practice basic Dart syntax

#### Key Topics:
1. Variables and data types
   - `int`, `double`, `String`, `bool`
   - `var`, `final`, and `const`
   - Type inference

2. Control flow
   - `if`/`else` statements
   - `for` and `while` loops
   - `switch`/`case` statements

3. Collections
   - Lists, Sets, and Maps
   - Collection manipulation

4. Null safety basics
   - Nullable vs non-nullable types
   - The `?` and `!` operators
   - Late initialization

#### Sample Code - Dart Basics:
```dart
void main() {
  // Variables and types
  String name = 'Flutter';
  int version = 3;
  double value = 3.29;
  bool isAwesome = true;
  
  // Null safety
  String? nullableName = null;
  String nonNullableName = 'Must have a value';
  
  // Control flow
  if (isAwesome) {
    print('Flutter is awesome!');
  } else {
    print('Hmm, something is wrong.');
  }
  
  // Loops
  for (int i = 0; i < 5; i++) {
    print('Count: $i');
  }
  
  // Collections
  List<String> frameworks = ['Flutter', 'React Native', 'SwiftUI'];
  Map<String, String> properties = {
    'language': 'Dart',
    'platform': 'Cross-platform',
  };
  
  // Collection operations
  frameworks.add('Xamarin');
  frameworks.forEach((framework) => print(framework));
}
```

#### Resources:
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [DartPad - Try Dart Online](https://dartpad.dev)
- [Dart Null Safety](https://dart.dev/null-safety)

### Day 3: Object-Oriented Programming in Dart

#### Objectives:
- Learn OOP concepts in Dart
- Understand classes, inheritance, and mixins
- Practice creating reusable code structures

#### Key Topics:
1. Classes and Objects
   - Defining classes
   - Properties and methods
   - Instance and static members

2. Constructors
   - Default constructors
   - Named constructors
   - Factory constructors
   - Initializer lists

3. Inheritance and Interfaces
   - Extending classes
   - Implementing interfaces
   - Method overriding

4. Mixins and Extensions
   - Creating and using mixins
   - Extension methods
   - When to use each

#### Sample Code - OOP in Dart:
```dart
// Basic class
class Person {
  String name;
  int age;
  
  // Constructor
  Person(this.name, this.age);
  
  // Named constructor
  Person.guest() : name = 'Guest', age = 18;
  
  // Method
  void introduce() {
    print('Hello, I am $name and I am $age years old.');
  }
  
  // Static method
  static Person createAdult(String name) {
    return Person(name, 30);
  }
}

// Inheritance
class Student extends Person {
  String school;
  
  Student(String name, int age, this.school) : super(name, age);
  
  @override
  void introduce() {
    super.introduce();
    print('I study at $school.');
  }
}

// Mixin
mixin Musical {
  void playInstrument() {
    print('Playing music');
  }
}

// Using a mixin
class MusicStudent extends Student with Musical {
  MusicStudent(String name, int age, String school) 
      : super(name, age, school);
}

// Extension
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${this.substring(1)}";
  }
}

void main() {
  var person = Person('John', 25);
  person.introduce();
  
  var student = Student('Mary', 20, 'Harvard');
  student.introduce();
  
  var musician = MusicStudent('Bob', 22, 'Juilliard');
  musician.introduce();
  musician.playInstrument();
  
  print('flutter'.capitalize()); // Extension method
}
```

#### Resources:
- [Dart Classes](https://dart.dev/guides/language/language-tour#classes)
- [Mixins in Dart](https://dart.dev/guides/language/language-tour#adding-features-to-a-class-mixins)
- [Extension Methods](https://dart.dev/guides/language/extension-methods)

### Day 4: Flutter Widgets Basics

#### Objectives:
- Understand the Flutter widget concept
- Learn the difference between StatelessWidget and StatefulWidget
- Build simple Flutter UI layouts

#### Key Topics:
1. Understanding Widgets
   - Widget tree and composition
   - Flutter's rendering pipeline
   - Widget lifecycle

2. StatelessWidget vs StatefulWidget
   - When to use each type
   - Converting between the two
   - State management basics

3. Basic Layout Widgets
   - Container widget
   - Row and Column
   - Text widgets
   - Button variants

#### Sample Code - Basic Flutter Widgets:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Widget Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Widget Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
            Container(
              margin: EdgeInsets.all(20),
              padding: EdgeInsets.all(15),
              decoration: BoxDecoration(
                color: Colors.lightBlue[100],
                borderRadius: BorderRadius.circular(10),
              ),
              child: Text('This is a Container widget'),
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Text('Text Button'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated Button'),
                ),
              ],
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Widget Catalog](https://flutter.dev/docs/development/ui/widgets)
- [Introduction to widgets](https://flutter.dev/docs/development/ui/widgets-intro)
- [Building layouts](https://flutter.dev/docs/development/ui/layout)

### Day 5: Layout Building

#### Objectives:
- Master Flutter's layout system
- Learn how to use various layout widgets
- Build complex layouts using multiple widgets

#### Key Topics:
1. Row and Column alignment
   - MainAxisAlignment and CrossAxisAlignment
   - MainAxisSize properties
   - Nesting for complex layouts

2. Container customization
   - Margin and padding
   - Decoration and styling
   - Constraints

3. Working with Stack
   - Positioning widgets
   - Alignment and overlays
   - Z-index equivalent

4. Flexible and Expanded
   - Dynamic space allocation
   - Flex factor
   - When to use each

#### Sample Code - Flutter Layouts:
```dart
import 'package:flutter/material.dart';

class LayoutDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Layout Examples')),
      body: SingleChildScrollView(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Row example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Row with MainAxisAlignment.spaceEvenly:'),
            ),
            Container(
              height: 50,
              color: Colors.amber[100],
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: [
                  Icon(Icons.star),
                  Icon(Icons.star),
                  Icon(Icons.star),
                ],
              ),
            ),
            
            // Column with alignment
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Column with different alignments:'),
            ),
            Container(
              height: 100,
              color: Colors.blue[100],
              child: Column(
                mainAxisAlignment: MainAxisAlignment.center,
                crossAxisAlignment: CrossAxisAlignment.end,
                children: [
                  Text('Right aligned'),
                  Text('Center aligned vertically'),
                ],
              ),
            ),
            
            // Stack example
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Stack with positioned elements:'),
            ),
            Container(
              height: 150,
              color: Colors.green[100],
              child: Stack(
                children: [
                  Positioned(
                    left: 20,
                    top: 20,
                    child: Container(
                      color: Colors.red,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    left: 40,
                    top: 40,
                    child: Container(
                      color: Colors.blue,
                      height: 50,
                      width: 50,
                    ),
                  ),
                  Positioned(
                    right: 40,
                    bottom: 20,
                    child: Container(
                      color: Colors.green,
                      height: 50,
                      width: 50,
                    ),
                  ),
                ],
              ),
            ),
            
            // Expanded and Flexible
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: Text('Expanded and Flexible:'),
            ),
            Container(
              height: 50,
              color: Colors.purple[100],
              child: Row(
                children: [
                  Expanded(
                    flex: 2,
                    child: Container(color: Colors.purple[200]),
                  ),
                  Flexible(
                    flex: 1,
                    child: Container(color: Colors.purple[300]),
                  ),
                  Expanded(
                    flex: 1,
                    child: Container(color: Colors.purple[400]),
                  ),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Layout Cheat Sheet](https://medium.com/flutter-community/flutter-layout-cheat-sheet-5363348d037e)
- [Understanding constraints](https://flutter.dev/docs/development/ui/layout/constraints)
- [Row and Column Classes](https://api.flutter.dev/flutter/widgets/Row-class.html)

### Day 6: Advanced Layout Techniques

#### Objectives:
- Master scrollable widgets in Flutter
- Learn about responsive layouts
- Implement complex layouts using CustomScrollView

#### Key Topics:
1. ListView and GridView
   - Basic usage
   - Builder patterns for efficiency
   - Custom item builders

2. ScrollView variants
   - SingleChildScrollView
   - PageView
   - TabBarView

3. CustomScrollView and Slivers
   - SliverAppBar
   - SliverList and SliverGrid
   - Custom sliver widgets

4. LayoutBuilder for responsive design
   - Adapting to available space
   - Media queries
   - Orientation-based layouts

#### Sample Code - Advanced Layouts:
```dart
import 'package:flutter/material.dart';

class AdvancedLayoutDemo extends StatelessWidget {
  final List<String> items = List.generate(50, (index) => 'Item ${index + 1}');
  
  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 4,
      child: Scaffold(
        appBar: AppBar(
          title: Text('Advanced Layouts'),
          bottom: TabBar(
            tabs: [
              Tab(text: 'ListView'),
              Tab(text: 'GridView'),
              Tab(text: 'CustomScroll'),
              Tab(text: 'Responsive'),
            ],
          ),
        ),
        body: TabBarView(
          children: [
            // ListView example
            ListView.builder(
              itemCount: items.length,
              itemBuilder: (context, index) {
                return ListTile(
                  leading: CircleAvatar(child: Text('${index + 1}')),
                  title: Text(items[index]),
                  subtitle: Text('Tap for details'),
                  trailing: Icon(Icons.arrow_forward_ios),
                  onTap: () {},
                );
              },
            ),
            
            // GridView example
            GridView.builder(
              gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                crossAxisCount: 3,
                childAspectRatio: 1.0,
                crossAxisSpacing: 10,
                mainAxisSpacing: 10,
              ),
              padding: EdgeInsets.all(10),
              itemCount: items.length,
              itemBuilder: (context, index) {
                return Card(
                  color: Colors.primaries[index % Colors.primaries.length],
                  child: Center(
                    child: Text(
                      '${index + 1}',
                      style: TextStyle(color: Colors.white, fontSize: 24),
                    ),
                  ),
                );
              },
            ),
            
            // CustomScrollView example
            CustomScrollView(
              slivers: <Widget>[
                SliverAppBar(
                  expandedHeight: 200.0,
                  floating: false,
                  pinned: true,
                  flexibleSpace: FlexibleSpaceBar(
                    title: Text('Sliver Example'),
                    background: Image.network(
                      'https://picsum.photos/800/600',
                      fit: BoxFit.cover,
                    ),
                  ),
                ),
                SliverPadding(
                  padding: EdgeInsets.all(8.0),
                  sliver: SliverList(
                    delegate: SliverChildBuilderDelegate(
                      (context, index) {
                        return Card(
                          margin: EdgeInsets.symmetric(
                            vertical: 8.0,
                            horizontal: 4.0,
                          ),
                          child: ListTile(
                            title: Text(items[index]),
                          ),
                        );
                      },
                      childCount: 10,
                    ),
                  ),
                ),
                SliverToBoxAdapter(
                  child: Container(
                    padding: EdgeInsets.all(16.0),
                    color: Colors.amber,
                    child: Text(
                      'SliverGrid Section',
                      style: TextStyle(fontSize: 18),
                    ),
                  ),
                ),
                SliverGrid(
                  gridDelegate: SliverGridDelegateWithMaxCrossAxisExtent(
                    maxCrossAxisExtent: 200.0,
                    mainAxisSpacing: 10.0,
                    crossAxisSpacing: 10.0,
                    childAspectRatio: 1.0,
                  ),
                  delegate: SliverChildBuilderDelegate(
                    (BuildContext context, int index) {
                      return Container(
                        color: Colors.primaries[index % Colors.primaries.length],
                        child: Center(
                          child: Text(
                            'Grid Item ${index + 1}',
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      );
                    },
                    childCount: 20,
                  ),
                ),
              ],
            ),
            
            // Responsive layout with LayoutBuilder
            LayoutBuilder(
              builder: (context, constraints) {
                if (constraints.maxWidth > 600) {
                  // Wide layout (tablet/desktop)
                  return GridView.builder(
                    gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                      crossAxisCount: 3,
                      childAspectRatio: 2.0,
                    ),
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: Column(
                          mainAxisAlignment: MainAxisAlignment.center,
                          children: [
                            Icon(Icons.aspect_ratio, size: 30),
                            Text('Width: ${constraints.maxWidth.toInt()}'),
                            Text('Item $index (Wide Layout)'),
                          ],
                        ),
                      );
                    },
                  );
                } else {
                  // Narrow layout (phone)
                  return ListView.builder(
                    itemCount: 12,
                    itemBuilder: (context, index) {
                      return Card(
                        margin: EdgeInsets.all(8.0),
                        child: ListTile(
                          leading: Icon(Icons.aspect_ratio),
                          title: Text('Item $index (Narrow Layout)'),
                          subtitle: Text(
                            'Width: ${constraints.maxWidth.toInt()}',
                          ),
                        ),
                      );
                    },
                  );
                }
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [ListView Class](https://api.flutter.dev/flutter/widgets/ListView-class.html)
- [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)
- [Responsive UI in Flutter](https://flutter.dev/docs/development/ui/layout/responsive)

### Day 7: Navigation and Routing

#### Objectives:
- Implement navigation between screens
- Learn different routing approaches
- Pass data between screens

#### Key Topics:
1. Basic Navigation
   - Navigator.push and Navigator.pop
   - MaterialPageRoute
   - CupertinoPageRoute

2. Named Routes
   - Defining routes
   - Navigator.pushNamed
   - Passing arguments

3. Advanced Navigation
   - Deep linking
   - Navigation history manipulation
   - WillPopScope usage

4. Route Transitions
   - Custom transitions
   - Hero animations with navigation
   - Page route builders

#### Sample Code - Navigation:
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(NavigationApp());
}

class NavigationApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Navigation Demo',
      // Named routes approach
      initialRoute: '/',
      routes: {
        '/': (context) => HomeScreen(),
        '/details': (context) => DetailScreen(),
        '/settings': (context) => SettingsScreen(),
      },
      // Optional: Custom route handling for dynamic routes or unknown routes
      onGenerateRoute: (settings) {
        if (settings.name!.startsWith('/product/')) {
          final productId = settings.name!.split('/')[2];
          return MaterialPageRoute(
            builder: (context) => ProductScreen(productId: productId),
          );
        }
        return null; // Let onUnknownRoute handle null cases
      },
      onUnknownRoute: (settings) {
        return MaterialPageRoute(
          builder: (context) => NotFoundScreen(),
        );
      },
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            // Basic navigation
            ElevatedButton(
              child: Text('Go to Details (Push)'),
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => DetailScreen(),
                  ),
                );
              },
            ),
            SizedBox(height: 20),
            
            // Named route navigation
            ElevatedButton(
              child: Text('Go to Details (Named)'),
              onPressed: () {
                Navigator.pushNamed(
                  context,
                  '/details',
                );
              },
            ),
            SizedBox(height: 20),
            
            // Passing data with navigation
            ElevatedButton(
              child: Text('Go to Product 123'),
              onPressed: () {
                // Option 1: Generate route dynamically
                Navigator.pushNamed(
                  context,
                  '/product/123',
                );
                
                // Option 2: Pass arguments with named routes
                // Navigator.pushNamed(
                //   context,
                //   '/details',
                //   arguments: {'id': '123', 'title': 'Premium Product'},
                // );
                
                // Option 3: Direct construction with data
                // Navigator.push(
                //   context,
                //   MaterialPageRoute(
                //     builder: (context) => ProductScreen(productId: '123'),
                //   ),
                // );
              },
            ),
            SizedBox(height: 20),
            
            // Settings screen
            ElevatedButton(
              child: Text('Settings'),
              onPressed: () {
                Navigator.pushNamed(context, '/settings');
              },
            ),
          ],
        ),
      ),
    );
  }
}

class DetailScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Retrieve arguments if passed
    final args = ModalRoute.of(context)!.settings.arguments as Map<String, dynamic>?;
    
    return Scaffold(
      appBar: AppBar(title: Text('Detail Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            if (args != null) Text('Arguments: $args'),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go Back'),
              onPressed: () {
                Navigator.pop(context);
              },
            ),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go to Home (replacement)'),
              onPressed: () {
                Navigator.pushReplacementNamed(context, '/');
              },
            ),
          ],
        ),
      ),
    );
  }
}

class ProductScreen extends StatelessWidget {
  final String productId;
  
  ProductScreen({required this.productId});
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Product Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Product ID: $productId', style: TextStyle(fontSize: 24)),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go Back'),
              onPressed: () {
                Navigator.pop(context);
              },
            ),
          ],
        ),
      ),
    );
  }
}

class SettingsScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return WillPopScope(
      // Control the back button behavior
      onWillPop: () async {
        // Show confirmation dialog
        bool shouldPop = await showDialog(
          context: context,
          builder: (context) => AlertDialog(
            title: Text('Confirm'),
            content: Text('Do you want to leave settings?'),
            actions: [
              TextButton(
                onPressed: () => Navigator.of(context).pop(false),
                child: Text('No'),
              ),
              TextButton(
                onPressed: () => Navigator.of(context).pop(true),
                child: Text('Yes'),
              ),
            ],
          ),
        ) ?? false;
        
        return shouldPop;
      },
      child: Scaffold(
        appBar: AppBar(title: Text('Settings')),
        body: Center(
          child: Text('Settings Screen'),
        ),
      ),
    );
  }
}

class NotFoundScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Page Not Found')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(Icons.error_outline, size: 80, color: Colors.red),
            SizedBox(height: 20),
            Text('The requested page was not found.'),
            SizedBox(height: 20),
            ElevatedButton(
              child: Text('Go to Home'),
              onPressed: () {
                Navigator.pushReplacementNamed(context, '/');
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Navigation basics](https://flutter.dev/docs/cookbook/navigation/navigation-basics)
- [Named routes](https://flutter.dev/docs/cookbook/navigation/named-routes)
- [Navigate with arguments](https://flutter.dev/docs/cookbook/navigation/navigate-with-arguments)
- [Return data from a screen](https://flutter.dev/docs/cookbook/navigation/returning-data)

## Week 2: UI Components & User Input

### Day 8: Input Widgets

#### Objectives:
- Learn how to use various input widgets
- Implement form validation
- Work with user input

#### Key Topics:
1. TextField and TextFormField
   - Basic usage
   - Input decoration
   - Keyboard types
   - Focus nodes

2. Form validation
   - Form widget
   - FormState and GlobalKey
   - Validation logic
   - Error messages

3. Selection Widgets
   - Checkbox and CheckboxListTile
   - Radio and RadioListTile
   - Switch and SwitchListTile
   - DropdownButton

4. Value Pickers
   - Slider
   - Date and time pickers
   - Range selectors

#### Sample Code - Form With Validation:
```dart
import 'package:flutter/material.dart';

class FormExample extends StatefulWidget {
  @override
  _FormExampleState createState() => _FormExampleState();
}

class _FormExampleState extends State<FormExample> {
  final _formKey = GlobalKey<FormState>();
  final TextEditingController _nameController = TextEditingController();
  final TextEditingController _emailController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();
  
  String? _selectedGender;
  bool _agreeToTerms = false;
  double _ageValue = 18;
  DateTime _selectedDate = DateTime.now();
  
  Future<void> _selectDate(BuildContext context) async {
    final DateTime? picked = await showDatePicker(
      context: context,
      initialDate: _selectedDate,
      firstDate: DateTime(1900),
      lastDate: DateTime.now(),
    );
    if (picked != null && picked != _selectedDate) {
      setState(() {
        _selectedDate = picked;
      });
    }
  }
  
  @override
  void dispose() {
    _nameController.dispose();
    _emailController.dispose();
    _passwordController.dispose();
    super.dispose();
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Input Widgets')),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Form(
          key: _formKey,
          child: SingleChildScrollView(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                // Name field
                TextFormField(
                  controller: _nameController,
                  decoration: InputDecoration(
                    labelText: 'Full Name',
                    hintText: 'Enter your full name',
                    prefixIcon: Icon(Icons.person),
                    border: OutlineInputBorder(),
                  ),
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter your name';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 16),
                
                // Email field
                TextFormField(
                  controller: _emailController,
                  decoration: InputDecoration(
                    labelText: 'Email',
                    hintText: 'Enter your email',
                    prefixIcon: Icon(Icons.email),
                    border: OutlineInputBorder(),
                  ),
                  keyboardType: TextInputType.emailAddress,
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter your email';
                    }
                    if (!RegExp(r'^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$')
                        .hasMatch(value)) {
                      return 'Please enter a valid email';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 16),
                
                // Password field
                TextFormField(
                  controller: _passwordController,
                  decoration: InputDecoration(
                    labelText: 'Password',
                    hintText: 'Enter your password',
                    prefixIcon: Icon(Icons.lock),
                    border: OutlineInputBorder(),
                  ),
                  obscureText: true,
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter a password';
                    }
                    if (value.length < 6) {
                      return 'Password must be at least 6 characters';
                    }
                    return null;
                  },
                ),
                SizedBox(height: 24),
                
                // Gender selection with Radio
                Text('Gender:', style: TextStyle(fontSize: 16)),
                RadioListTile<String>(
                  title: Text('Male'),
                  value: 'male',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                RadioListTile<String>(
                  title: Text('Female'),
                  value: 'female',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                RadioListTile<String>(
                  title: Text('Other'),
                  value: 'other',
                  groupValue: _selectedGender,
                  onChanged: (value) {
                    setState(() {
                      _selectedGender = value;
                    });
                  },
                ),
                SizedBox(height: 16),
                
                // Age slider
                Text('Age: ${_ageValue.round()}', style: TextStyle(fontSize: 16)),
                Slider(
                  value: _ageValue,
                  min: 1,
                  max: 100,
                  divisions: 99,
                  label: _ageValue.round().toString(),
                  onChanged: (value) {
                    setState(() {
                      _ageValue = value;
                    });
                  },
                ),
                SizedBox(height: 16),
                
                // Date picker
                Row(
                  children: [
                    Text('Date of Birth: ${_selectedDate.toLocal().toString().split(' ')[0]}'),
                    Spacer(),
                    ElevatedButton(
                      onPressed: () => _selectDate(context),
                      child: Text('Select Date'),
                    ),
                  ],
                ),
                SizedBox(height: 24),
                
                // Terms and conditions checkbox
                CheckboxListTile(
                  title: Text('I agree to the terms and conditions'),
                  value: _agreeToTerms,
                  onChanged: (value) {
                    setState(() {
                      _agreeToTerms = value ?? false;
                    });
                  },
                  controlAffinity: ListTileControlAffinity.leading,
                ),
                SizedBox(height: 24),
                
                // Submit button
                Center(
                  child: ElevatedButton(
                    style: ElevatedButton.styleFrom(
                      minimumSize: Size(200, 50),
                    ),
                    onPressed: () {
                      if (_formKey.currentState!.validate() && _agreeToTerms) {
                        // Form is valid, process the data
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(content: Text('Processing Data')),
                        );
                      } else if (!_agreeToTerms) {
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(
                            content: Text('Please agree to the terms and conditions'),
                            backgroundColor: Colors.red,
                          ),
                        );
                      }
                    },
                    child: Text('Submit', style: TextStyle(fontSize: 18)),
                  ),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Forms in Flutter](https://flutter.dev/docs/cookbook/forms)
- [TextFormField class](https://api.flutter.dev/flutter/material/TextFormField-class.html)
- [DateTime picker](https://flutter.dev/docs/cookbook/forms/datetime-picker)
- [Form validation](https://flutter.dev/docs/cookbook/forms/validation)

### Day 9: Dialogs and Alerts

#### Objectives:
- Learn how to display dialogs and alerts
- Implement different types of user notifications
- Get user confirmation for actions

#### Key Topics:
1. AlertDialog
   - Basic alert dialogs
   - Confirmation dialogs
   - Custom dialog content

2. SimpleDialog
   - Option selection
   - Custom content
   - Dialog results

3. BottomSheet and ModalBottomSheet
   - Persistent bottom sheets
   - Modal bottom sheets
   - Draggable bottom sheets

4. Snackbar and Toast
   - Showing temporary messages
   - Action buttons
   - Styling notifications

5. Progress Indicators
   - Linear progress
   - Circular progress
   - Indeterminate progress

#### Sample Code - Dialogs and Notifications:
```dart
import 'package:flutter/material.dart';

class DialogsExample extends StatefulWidget {
  @override
  _DialogsExampleState createState() => _DialogsExampleState();
}

class _DialogsExampleState extends State<DialogsExample> {
  String _selectedOption = 'None';
  double _progress = 0.0;
  
  // Simple Alert Dialog
  Future<void> _showAlertDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(
          title: Text('Alert Dialog'),
          content: Text('This is a simple alert dialog.'),
          actions: [
            TextButton(
              onPressed: () {
                Navigator.of(context).pop();
              },
              child: Text('Close'),
            ),
          ],
        );
      },
    );
  }
  
  // Confirmation Dialog
  Future<void> _showConfirmationDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return AlertDialog(
          title: Text('Confirm Action'),
          content: Text('Are you sure you want to perform this action?'),
          actions: [
            TextButton(
              onPressed: () {
                Navigator.of(context).pop('Cancel');
              },
              child: Text('Cancel'),
            ),
            TextButton(
              onPressed: () {
                Navigator.of(context).pop('Confirm');
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Action confirmed!')),
                );
              },
              child: Text('Confirm'),
            ),
          ],
        );
      },
    );
  }
  
  // Simple Dialog with options
  Future<void> _showSimpleDialog() async {
    String? result = await showDialog<String>(
      context: context,
      builder: (BuildContext context) {
        return SimpleDialog(
          title: Text('Select an option'),
          children: [
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 1');
              },
              child: Text('Option 1'),
            ),
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 2');
              },
              child: Text('Option 2'),
            ),
            SimpleDialogOption(
              onPressed: () {
                Navigator.of(context).pop('Option 3');
              },
              child: Text('Option 3'),
            ),
          ],
        );
      },
    );
    
    if (result != null) {
      setState(() {
        _selectedOption = result;
      });
      ScaffoldMessenger.of(context).showSnackBar(
        SnackBar(content: Text('Selected: $result')),
      );
    }
  }
  
  // Custom Dialog
  Future<void> _showCustomDialog() async {
    return showDialog(
      context: context,
      builder: (BuildContext context) {
        return Dialog(
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(20.0),
          ),
          child: Container(
            height: 250,
            padding: EdgeInsets.all(20),
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                Icon(Icons.check_circle, color: Colors.green, size: 60),
                SizedBox(height: 20),
                Text(
                  'Success!',
                  style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
                ),
                SizedBox(height: 10),
                Text('Your operation was completed successfully.'),
                SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    Navigator.of(context).pop();
                  },
                  child: Text('Close'),
                  style: ElevatedButton.styleFrom(
                    minimumSize: Size(150, 40),
                  ),
                ),
              ],
            ),
          ),
        );
      },
    );
  }
  
  // Modal Bottom Sheet
  void _showModalBottomSheet() {
    showModalBottomSheet(
      context: context,
      isScrollControlled: true,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.vertical(top: Radius.circular(20)),
      ),
      builder: (BuildContext context) {
        return DraggableScrollableSheet(
          initialChildSize: 0.5,
          minChildSize: 0.3,
          maxChildSize: 0.9,
          expand: false,
          builder: (context, scrollController) {
            return Container(
              padding: EdgeInsets.all(16),
              child: ListView(
                controller: scrollController,
                children: [
                  Center(
                    child: Container(
                      width: 40,
                      height: 5,
                      margin: EdgeInsets.only(bottom: 20),
                      decoration: BoxDecoration(
                        color: Colors.grey[300],
                        borderRadius: BorderRadius.circular(10),
                      ),
                    ),
                  ),
                  Text(
                    'Modal Bottom Sheet',
                    style: TextStyle(fontSize: 22, fontWeight: FontWeight.bold),
                  ),
                  SizedBox(height: 16),
                  Text(
                    'This is a modal bottom sheet with draggable functionality.',
                    style: TextStyle(fontSize: 16),
                  ),
                  SizedBox(height: 16),
                  for (int i = 1; i <= 20; i++)
                    ListTile(
                      leading: CircleAvatar(child: Text('$i')),
                      title: Text('Item $i'),
                      subtitle: Text('Description for item $i'),
                      onTap: () {
                        Navigator.pop(context);
                        ScaffoldMessenger.of(context).showSnackBar(
                          SnackBar(content: Text('Selected item $i')),
                        );
                      },
                    ),
                ],
              ),
            );
          },
        );
      },
    );
  }
  
  // Show a Snackbar
  void _showSnackBar() {
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(
        content: Text('This is a snackbar message'),
        action: SnackBarAction(
          label: 'Undo',
          onPressed: () {
            // Undo action
          },
        ),
        duration: Duration(seconds: 3),
        behavior: SnackBarBehavior.floating,
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(10),
        ),
      ),
    );
  }
  
  // Show progress dialog
  void _showProgressDialog() {
    setState(() {
      _progress = 0.0;
    });
    
    showDialog(
      context: context,
      barrierDismissible: false,
      builder: (BuildContext context) {
        return StatefulBuilder(
          builder: (context, setState) {
            // Simulate progress
            Future.delayed(Duration(milliseconds: 500), () {
              if (_progress < 1.0) {
                setState(() {
                  _progress += 0.1;
                });
                
                if (_progress >= 1.0) {
                  Navigator.of(context).pop();
                  _showCustomDialog();
                }
              }
            });
            
            return AlertDialog(
              title: Text('Loading...'),
              content: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  LinearProgressIndicator(value: _progress),
                  SizedBox(height: 16),
                  Text('${(_progress * 100).toInt()}%'),
                ],
              ),
            );
          },
        );
      },
    );
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Dialogs and Alerts')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Selected Option: $_selectedOption', style: TextStyle(fontSize: 16)),
            SizedBox(height: 30),
            ElevatedButton(
              onPressed: _showAlertDialog,
              child: Text('Show Alert Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showConfirmationDialog,
              child: Text('Show Confirmation Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showSimpleDialog,
              child: Text('Show Simple Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showCustomDialog,
              child: Text('Show Custom Dialog'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showModalBottomSheet,
              child: Text('Show Modal Bottom Sheet'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showSnackBar,
              child: Text('Show Snackbar'),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _showProgressDialog,
              child: Text('Show Progress Dialog'),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Dialogs](https://flutter.dev/docs/cookbook/design/dialogs)
- [SnackBars](https://flutter.dev/docs/cookbook/design/snackbars)
- [Bottom Sheets](https://api.flutter.dev/flutter/material/showModalBottomSheet.html)
- [Progress Indicators](https://flutter.dev/docs/cookbook/forms/progress-indicator)

### Day 10: Custom Widgets

#### Objectives:
- Learn how to create reusable widgets
- Understand widget lifecycle
- Master widget composition

#### Key Topics:
1. Creating Custom Widgets
   - Composition patterns
   - Property passing
   - Callback functions

2. Widget Lifecycle
   - initState and dispose
   - didChangeDependencies
   - didUpdateWidget

3. Stateful Widget Internals
   - State creation and management
   - Widget rebuilding optimization
   - StatefulWidget vs StatelessWidget trade-offs

4. Keys in Flutter
   - Understanding widget identity
   - ValueKey, ObjectKey, UniqueKey
   - GlobalKey usage

#### Sample Code - Custom Widgets:
```dart
import 'package:flutter/material.dart';

// 1. Simple Custom Widget (Stateless)
class CustomCard extends StatelessWidget {
  final String title;
  final String subtitle;
  final IconData icon;
  final VoidCallback? onTap;
  
  const CustomCard({
    Key? key,
    required this.title,
    required this.subtitle,
    required this.icon,
    this.onTap,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 4,
      margin: EdgeInsets.symmetric(vertical: 8, horizontal: 16),
      child: ListTile(
        leading: Icon(icon, size: 32, color: Theme.of(context).primaryColor),
        title: Text(title, style: TextStyle(fontWeight: FontWeight.bold)),
        subtitle: Text(subtitle),
        trailing: Icon(Icons.arrow_forward_ios),
        onTap: onTap,
      ),
    );
  }
}

// 2. Advanced Custom Widget (Stateful with lifecycle methods)
class CountdownTimer extends StatefulWidget {
  final int duration; // in seconds
  final Function()? onComplete;
  
  const CountdownTimer({
    Key? key,
    required this.duration,
    this.onComplete,
  }) : super(key: key);
  
  @override
  _CountdownTimerState createState() => _CountdownTimerState();
}

class _CountdownTimerState extends State<CountdownTimer> {
  late int _secondsRemaining;
  late bool _isRunning;
  
  @override
  void initState() {
    super.initState();
    _secondsRemaining = widget.duration;
    _isRunning = false;
    print('CountdownTimer: initState called');
  }
  
  @override
  void didChangeDependencies() {
    super.didChangeDependencies();
    print('CountdownTimer: didChangeDependencies called');
    // Called when inherited dependencies change
  }
  
  @override
  void didUpdateWidget(CountdownTimer oldWidget) {
    super.didUpdateWidget(oldWidget);
    print('CountdownTimer: didUpdateWidget called');
    
    // Reset timer if duration changed
    if (oldWidget.duration != widget.duration) {
      setState(() {
        _secondsRemaining = widget.duration;
        _isRunning = false;
      });
    }
  }
  
  @override
  void dispose() {
    print('CountdownTimer: dispose called');
    super.dispose();
  }
  
  void _startTimer() {
    setState(() {
      _isRunning = true;
    });
    
    Future.doWhile(() async {
      await Future.delayed(Duration(seconds: 1));
      
      if (!mounted) return false;
      
      setState(() {
        if (_secondsRemaining > 0) {
          _secondsRemaining--;
        }
        
        if (_secondsRemaining <= 0) {
          _isRunning = false;
          if (widget.onComplete != null) {
            widget.onComplete!();
          }
        }
      });
      
      return _isRunning && _secondsRemaining > 0;
    });
  }
  
  void _resetTimer() {
    setState(() {
      _secondsRemaining = widget.duration;
      _isRunning = false;
    });
  }
  
  String _formatTime() {
    int minutes = _secondsRemaining ~/ 60;
    int seconds = _secondsRemaining % 60;
    return '$minutes:${seconds.toString().padLeft(2, '0')}';
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Text(
              'Countdown Timer',
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            Text(
              _formatTime(),
              style: TextStyle(
                fontSize: 48,
                fontWeight: FontWeight.bold,
                color: _secondsRemaining < 10 ? Colors.red : Colors.black,
              ),
            ),
            SizedBox(height: 16),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: _isRunning ? null : _startTimer,
                  child: Text(_isRunning ? 'Running' : 'Start'),
                ),
                SizedBox(width: 16),
                ElevatedButton(
                  onPressed: _resetTimer,
                  child: Text('Reset'),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// 3. Widget with custom painter
class CircularProgressWidget extends StatelessWidget {
  final double progress; // 0.0 to 1.0
  final double size;
  final Color color;
  
  const CircularProgressWidget({
    Key? key,
    required this.progress,
    this.size = 100,
    this.color = Colors.blue,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return Container(
      width: size,
      height: size,
      child: CustomPaint(
        painter: CircularProgressPainter(
          progress: progress,
          color: color,
        ),
        child: Center(
          child: Text(
            '${(progress * 100).toInt()}%',
            style: TextStyle(
              fontWeight: FontWeight.bold,
              fontSize: size / 5,
            ),
          ),
        ),
      ),
    );
  }
}

class CircularProgressPainter extends CustomPainter {
  final double progress;
  final Color color;
  
  CircularProgressPainter({
    required this.progress,
    required this.color,
  });
  
  @override
  void paint(Canvas canvas, Size size) {
    // Background circle
    final Paint backgroundPaint = Paint()
      ..color = Colors.grey.shade300
      ..style = PaintingStyle.stroke
      ..strokeWidth = size.width / 15;
    
    final Offset center = Offset(size.width / 2, size.height / 2);
    final double radius = (size.width - backgroundPaint.strokeWidth) / 2;
    
    canvas.drawCircle(center, radius, backgroundPaint);
    
    // Progress arc
    final Paint progressPaint = Paint()
      ..color = color
      ..style = PaintingStyle.stroke
      ..strokeWidth = size.width / 15
      ..strokeCap = StrokeCap.round;
    
    final double sweepAngle = 2 * 3.14159 * progress;
    
    canvas.drawArc(
      Rect.fromCircle(center: center, radius: radius),
      -3.14159 / 2, // Start at top
      sweepAngle,
      false,
      progressPaint,
    );
  }
  
  @override
  bool shouldRepaint(CircularProgressPainter oldDelegate) {
    return oldDelegate.progress != progress || oldDelegate.color != color;
  }
}

// Usage example for custom widgets
class CustomWidgetsExample extends StatefulWidget {
  @override
  _CustomWidgetsExampleState createState() => _CustomWidgetsExampleState();
}

class _CustomWidgetsExampleState extends State<CustomWidgetsExample> {
  double _progress = 0.7;
  int _timerDuration = 30;
  
  void _timerComplete() {
    ScaffoldMessenger.of(context).showSnackBar(
      SnackBar(content: Text('Timer completed!')),
    );
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Custom Widgets')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('1. Custom Card Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 8),
            CustomCard(
              title: 'Weather',
              subtitle: 'Sunny, 25°C',
              icon: Icons.wb_sunny,
              onTap: () {
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Weather card tapped')),
                );
              },
            ),
            CustomCard(
              title: 'Calendar',
              subtitle: 'Meeting at 2:00 PM',
              icon: Icons.calendar_today,
              onTap: () {
                ScaffoldMessenger.of(context).showSnackBar(
                  SnackBar(content: Text('Calendar card tapped')),
                );
              },
            ),
            
            Divider(height: 32),
            
            Text('2. Stateful Countdown Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 8),
            CountdownTimer(
              key: ValueKey(_timerDuration),
              duration: _timerDuration,
              onComplete: _timerComplete,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 10;
                    });
                  },
                  child: Text('Set 10s'),
                ),
                SizedBox(width: 8),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 30;
                    });
                  },
                  child: Text('Set 30s'),
                ),
                SizedBox(width: 8),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      _timerDuration = 60;
                    });
                  },
                  child: Text('Set 60s'),
                ),
              ],
            ),
            
            Divider(height: 32),
            
            Text('3. Custom Painter Widget', style: TextStyle(fontSize: 18)),
            SizedBox(height: 16),
            Center(
              child: CircularProgressWidget(progress: _progress),
            ),
            SizedBox(height: 16),
            Slider(
              value: _progress,
              min: 0.0,
              max: 1.0,
              divisions: 100,
              label: '${(_progress * 100).toInt()}%',
              onChanged: (value) {
                setState(() {
                  _progress = value;
                });
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Widget lifecycle](https://flutterbyexample.com/lesson/stateful-widget-lifecycle)
- [Custom Painters](https://flutter.dev/docs/development/ui/advanced/custom-painters)
- [Using keys](https://flutter.dev/docs/development/ui/widgets-intro#keys)
- [Flutter widget of the week videos](https://www.youtube.com/playlist?list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG)

### Day 11: Themes and Styling

#### Objectives:
- Master Flutter's theming system
- Create consistent app styling
- Implement light and dark themes

#### Key Topics:
1. ThemeData Basics
   - Using MaterialApp theme property
   - Color schemes and palettes
   - Typography and text themes

2. Creating Custom Themes
   - Light and dark themes
   - Extending existing themes
   - Theme controllers

3. Using Theme in Widgets
   - Theme.of(context)
   - Accessing theme properties
   - Theme consistency

4. Material Design Guidelines
   - Following Material Design
   - Custom theme extensions
   - Design system implementation

#### Sample Code - Theme Implementation:
```dart
import 'package:flutter/material.dart';

// Define our app theme data
class AppTheme {
  // Light theme
  static ThemeData lightTheme = ThemeData(
    brightness: Brightness.light,
    primarySwatch: Colors.blue,
    colorScheme: ColorScheme.light(
      primary: Colors.blue,
      secondary: Colors.blueAccent,
      surface: Colors.white,
      background: Color(0xFFF5F5F5),
      error: Colors.red,
    ),
    appBarTheme: AppBarTheme(
      backgroundColor: Colors.blue,
      foregroundColor: Colors.white,
      elevation: 4,
    ),
    cardTheme: CardTheme(
      elevation: 2,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(12),
      ),
    ),
    inputDecorationTheme: InputDecorationTheme(
      filled: true,
      fillColor: Colors.grey[100],
      border: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide.none,
      ),
      enabledBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.grey[300]!),
      ),
      focusedBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.blue, width: 2),
      ),
      contentPadding: EdgeInsets.symmetric(horizontal: 16, vertical: 16),
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textTheme: TextTheme(
      displayLarge: TextStyle(
        fontSize: 28,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      displayMedium: TextStyle(
        fontSize: 24,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      displaySmall: TextStyle(
        fontSize: 20,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      headlineMedium: TextStyle(
        fontSize: 18,
        fontWeight: FontWeight.bold,
        color: Colors.black87,
      ),
      bodyLarge: TextStyle(
        fontSize: 16,
        color: Colors.black87,
      ),
      bodyMedium: TextStyle(
        fontSize: 14,
        color: Colors.black87,
      ),
    ),
    dividerTheme: DividerThemeData(
      space: 24,
      thickness: 1,
      color: Colors.grey[300],
    ),
  );

  // Dark theme
  static ThemeData darkTheme = ThemeData(
    brightness: Brightness.dark,
    primarySwatch: Colors.indigo,
    colorScheme: ColorScheme.dark(
      primary: Colors.indigo,
      secondary: Colors.indigoAccent,
      surface: Color(0xFF1E1E1E),
      background: Color(0xFF121212),
      error: Colors.redAccent,
    ),
    scaffoldBackgroundColor: Color(0xFF121212),
    appBarTheme: AppBarTheme(
      backgroundColor: Color(0xFF1E1E1E),
      elevation: 0,
    ),
    cardTheme: CardTheme(
      color: Color(0xFF1E1E1E),
      elevation: 8,
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(12),
      ),
    ),
    inputDecorationTheme: InputDecorationTheme(
      filled: true,
      fillColor: Color(0xFF2C2C2C),
      border: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide.none,
      ),
      enabledBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.grey[700]!),
      ),
      focusedBorder: OutlineInputBorder(
        borderRadius: BorderRadius.circular(8),
        borderSide: BorderSide(color: Colors.indigo, width: 2),
      ),
      contentPadding: EdgeInsets.symmetric(horizontal: 16, vertical: 16),
    ),
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        backgroundColor: Colors.indigo,
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        foregroundColor: Colors.indigo[300],
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(8),
        ),
        padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
      ),
    ),
    textTheme: TextTheme(
      displayLarge: TextStyle(
        fontSize: 28,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      displayMedium: TextStyle(
        fontSize: 24,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      displaySmall: TextStyle(
        fontSize: 20,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      headlineMedium: TextStyle(
        fontSize: 18,
        fontWeight: FontWeight.bold,
        color: Colors.white,
      ),
      bodyLarge: TextStyle(
        fontSize: 16,
        color: Colors.white70,
      ),
      bodyMedium: TextStyle(
        fontSize: 14,
        color: Colors.white70,
      ),
    ),
    dividerTheme: DividerThemeData(
      space: 24,
      thickness: 1,
      color: Colors.grey[800],
    ),
    iconTheme: IconThemeData(
      color: Colors.grey[400],
    ),
  );
}

// Theme Switcher with Provider pattern
class ThemeProvider extends ChangeNotifier {
  ThemeMode _themeMode = ThemeMode.light;
  
  ThemeMode get themeMode => _themeMode;
  
  bool get isDarkMode => _themeMode == ThemeMode.dark;
  
  void toggleTheme() {
    _themeMode = isDarkMode ? ThemeMode.light : ThemeMode.dark;
    notifyListeners();
  }
}

// Example app using themes
class ThemeExample extends StatelessWidget {
  final ThemeProvider themeProvider;
  
  ThemeExample({required this.themeProvider});
  
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Theme Example',
      theme: AppTheme.lightTheme,
      darkTheme: AppTheme.darkTheme,
      themeMode: themeProvider.themeMode,
      home: ThemeShowcaseScreen(themeProvider: themeProvider),
    );
  }
}

class ThemeShowcaseScreen extends StatelessWidget {
  final ThemeProvider themeProvider;
  
  ThemeShowcaseScreen({required this.themeProvider});
  
  @override
  Widget build(BuildContext context) {
    final theme = Theme.of(context);
    
    return Scaffold(
      appBar: AppBar(
        title: Text('Theme Showcase'),
        actions: [
          IconButton(
            icon: Icon(
              themeProvider.isDarkMode ? Icons.light_mode : Icons.dark_mode,
            ),
            onPressed: themeProvider.toggleTheme,
          ),
        ],
      ),
      body: SingleChildScrollView(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Typography',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Text(
              'Display Large',
              style: theme.textTheme.displayLarge,
            ),
            Text(
              'Display Medium',
              style: theme.textTheme.displayMedium,
            ),
            Text(
              'Display Small',
              style: theme.textTheme.displaySmall,
            ),
            Text(
              'Headline Medium',
              style: theme.textTheme.headlineMedium,
            ),
            Text(
              'Body Large',
              style: theme.textTheme.bodyLarge,
            ),
            Text(
              'Body Medium',
              style: theme.textTheme.bodyMedium,
            ),
            
            Divider(),
            
            Text(
              'Buttons',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                ElevatedButton(
                  onPressed: () {},
                  child: Text('Elevated'),
                ),
                TextButton(
                  onPressed: () {},
                  child: Text('Text'),
                ),
                OutlinedButton(
                  onPressed: () {},
                  child: Text('Outlined'),
                ),
              ],
            ),
            
            Divider(),
            
            Text(
              'Input Fields',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            TextField(
              decoration: InputDecoration(
                labelText: 'Username',
                hintText: 'Enter your username',
                prefixIcon: Icon(Icons.person),
              ),
            ),
            SizedBox(height: 16),
            TextField(
              obscureText: true,
              decoration: InputDecoration(
                labelText: 'Password',
                hintText: 'Enter your password',
                prefixIcon: Icon(Icons.lock),
              ),
            ),
            
            Divider(),
            
            Text(
              'Cards',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Card(
              child: Padding(
                padding: const EdgeInsets.all(16.0),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Card Title',
                      style: theme.textTheme.headlineMedium,
                    ),
                    SizedBox(height: 8),
                    Text(
                      'This is a card with some content. Cards are surface components that display content and actions on a single topic.',
                      style: theme.textTheme.bodyMedium,
                    ),
                    SizedBox(height: 16),
                    Row(
                      mainAxisAlignment: MainAxisAlignment.end,
                      children: [
                        TextButton(
                          onPressed: () {},
                          child: Text('CANCEL'),
                        ),
                        SizedBox(width: 8),
                        ElevatedButton(
                          onPressed: () {},
                          child: Text('CONFIRM'),
                        ),
                      ],
                    ),
                  ],
                ),
              ),
            ),
            
            Divider(),
            
            Text(
              'Colors',
              style: theme.textTheme.displayLarge,
            ),
            SizedBox(height: 8),
            Row(
              children: [
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.primary,
                    name: 'Primary',
                  ),
                ),
                SizedBox(width: 8),
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.secondary,
                    name: 'Secondary',
                  ),
                ),
              ],
            ),
            SizedBox(height: 8),
            Row(
              children: [
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.surface,
                    name: 'Surface',
                    textColor: theme.brightness == Brightness.dark
                        ? Colors.white
                        : Colors.black,
                  ),
                ),
                SizedBox(width: 8),
                Expanded(
                  child: _ColorBox(
                    color: theme.colorScheme.background,
                    name: 'Background',
                    textColor: theme.brightness == Brightness.dark
                        ? Colors.white
                        : Colors.black,
                  ),
                ),
              ],
            ),
            SizedBox(height: 8),
            _ColorBox(
              color: theme.colorScheme.error,
              name: 'Error',
            ),
          ],
        ),
      ),
    );
  }
}

class _ColorBox extends StatelessWidget {
  final Color color;
  final String name;
  final Color? textColor;
  
  const _ColorBox({
    required this.color,
    required this.name,
    this.textColor = Colors.white,
  });
  
  @override
  Widget build(BuildContext context) {
    return Container(
      height: 80,
      decoration: BoxDecoration(
        color: color,
        borderRadius: BorderRadius.circular(8),
      ),
      alignment: Alignment.center,
      child: Text(
        name,
        style: TextStyle(
          color: textColor,
          fontWeight: FontWeight.bold,
        ),
      ),
    );
  }
}

### Day 12: Assets and Images

#### Objectives:
- Learn how to work with assets in Flutter
- Understand image loading and optimization
- Implement image caching and placeholders

#### Key Topics:
1. Adding Assets to Your App
   - pubspec.yaml asset declaration
   - Asset folder structure
   - Accessing assets in code

2. Image Types and Formats
   - Local vs network images
   - Image resolution and variants
   - SVG and vector graphics

3. Image Widgets
   - Image widget
   - FadeInImage for smooth loading
   - Hero animations with images

4. Image Optimization
   - Caching strategies
   - Responsive images
   - Performance considerations

#### Sample Code - Working with Assets and Images:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_svg/flutter_svg.dart';
import 'package:cached_network_image/cached_network_image.dart';

class AssetsExample extends StatelessWidget {
  // Sample image URLs for demonstration
  final List<String> networkImages = [
    'https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1600054800747-be294a6a0d26?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1567306226408-c0fe0c9662ea?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
    'https://images.unsplash.com/photo-1488590528505-98d2b5aba04b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
  ];
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Assets and Images')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // 1. Local Asset Images
            Text(
              '1. Local Asset Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            Text(
              'Basic Image.asset():',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: Image.asset(
                'assets/images/flutter_logo.png',
                width: 150,
                height: 150,
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'Asset Image with BoxFit:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                _ImageWithLabel(
                  label: 'contain',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.contain,
                  ),
                ),
                _ImageWithLabel(
                  label: 'cover',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                _ImageWithLabel(
                  label: 'fill',
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.fill,
                  ),
                ),
              ],
            ),
            SizedBox(height: 24),
            
            // 2. Network Images
            Text(
              '2. Network Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            
            Text(
              'Basic Image.network():',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: Image.network(
                networkImages[0],
                width: 200,
                height: 150,
                loadingBuilder: (context, child, loadingProgress) {
                  if (loadingProgress == null) return child;
                  return Center(
                    child: CircularProgressIndicator(
                      value: loadingProgress.expectedTotalBytes != null
                          ? loadingProgress.cumulativeBytesLoaded /
                              loadingProgress.expectedTotalBytes!
                          : null,
                    ),
                  );
                },
                errorBuilder: (context, error, stackTrace) {
                  return Container(
                    width: 200,
                    height: 150,
                    color: Colors.grey[300],
                    child: Center(
                      child: Icon(
                        Icons.error_outline,
                        color: Colors.red,
                        size: 40,
                      ),
                    ),
                  );
                },
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'FadeInImage with placeholder:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: FadeInImage.assetNetwork(
                placeholder: 'assets/images/image_placeholder.png',
                image: networkImages[1],
                width: 200,
                height: 150,
                fit: BoxFit.cover,
                fadeInDuration: Duration(milliseconds: 700),
                fadeInCurve: Curves.easeIn,
              ),
            ),
            SizedBox(height: 16),
            
            Text(
              'CachedNetworkImage with caching:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Center(
              child: CachedNetworkImage(
                imageUrl: networkImages[2],
                width: 200,
                height: 150,
                fit: BoxFit.cover,
                placeholder: (context, url) => Container(
                  color: Colors.grey[300],
                  child: Center(
                    child: CircularProgressIndicator(),
                  ),
                ),
                errorWidget: (context, url, error) => Container(
                  color: Colors.grey[300],
                  child: Center(
                    child: Icon(
                      Icons.error_outline,
                      color: Colors.red,
                      size: 40,
                    ),
                  ),
                ),
              ),
            ),
            SizedBox(height: 24),
            
            // 3. SVG Images
            Text(
              '3. SVG Images',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            Center(
              child: SvgPicture.asset(
                'assets/images/flutter_logo.svg',
                width: 150,
                height: 150,
              ),
            ),
            SizedBox(height: 24),
            
            // 4. Image Manipulation
            Text(
              '4. Image Manipulation',
              style: Theme.of(context).textTheme.titleLarge,
            ),
            SizedBox(height: 8),
            
            Text(
              'Circular images:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Method 1: Using ClipRRect
                ClipRRect(
                  borderRadius: BorderRadius.circular(75),
                  child: Image.network(
                    networkImages[3],
                    width: 150,
                    height: 150,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Method 2: Using Container and BoxDecoration
                Container(
                  width: 150,
                  height: 150,
                  decoration: BoxDecoration(
                    shape: BoxShape.circle,
                    image: DecorationImage(
                      image: NetworkImage(networkImages[3]),
                      fit: BoxFit.cover,
                    ),
                  ),
                ),
              ],
            ),
            SizedBox(height: 16),
            
            Text(
              'Color filters and effects:',
              style: Theme.of(context).textTheme.titleMedium,
            ),
            SizedBox(height: 8),
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Grayscale
                ColorFiltered(
                  colorFilter: ColorFilter.mode(
                    Colors.grey,
                    BlendMode.saturation,
                  ),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Sepia-like
                ColorFiltered(
                  colorFilter: ColorFilter.matrix([
                    0.393, 0.769, 0.189, 0, 0,
                    0.349, 0.686, 0.168, 0, 0,
                    0.272, 0.534, 0.131, 0, 0,
                    0,     0,     0,     1, 0,
                  ]),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
                
                // Inverted
                ColorFiltered(
                  colorFilter: ColorFilter.matrix([
                    -1,  0,  0, 0, 255,
                     0, -1,  0, 0, 255,
                     0,  0, -1, 0, 255,
                     0,  0,  0, 1,   0,
                  ]),
                  child: Image.asset(
                    'assets/images/landscape.jpg',
                    width: 100,
                    height: 100,
                    fit: BoxFit.cover,
                  ),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// Helper widget for displaying images with labels
class _ImageWithLabel extends StatelessWidget {
  final String label;
  final Widget child;
  
  const _ImageWithLabel({
    required this.label,
    required this.child,
  });
  
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Container(
          decoration: BoxDecoration(
            border: Border.all(color: Colors.grey),
          ),
          child: child,
        ),
        SizedBox(height: 4),
        Text(label),
      ],
    );
  }
}

### Day 13: Responsive Design

#### Objectives:
- Understand responsive design principles in Flutter
- Adapt UIs to different screen sizes
- Handle orientation changes

#### Key Topics:
1. Understanding Device Metrics
   - MediaQuery for screen dimensions
   - Device orientation
   - Safe areas and notches

2. Responsive Layout Patterns
   - Flexible and Expanded
   - LayoutBuilder for adaptive layouts
   - OrientationBuilder

3. Responsive UI Libraries
   - flutter_screenutil
   - responsive_framework
   - Breakpoints and grid systems

4. Testing Responsive UIs
   - Testing on different devices
   - Device preview tools
   - Responsive UI best practices

#### Sample Code - Responsive Design:
```dart
import 'package:flutter/material.dart';

class ResponsiveDesignExample extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Responsive Design')),
      body: SafeArea(
        child: ListView(
          padding: EdgeInsets.all(16),
          children: [
            // 1. MediaQuery Example
            _SectionTitle(title: '1. MediaQuery for Screen Information'),
            MediaQueryDemo(),
            _SectionDivider(),
            
            // 2. Orientation-based Layout
            _SectionTitle(title: '2. Orientation-based Layout'),
            OrientationLayoutDemo(),
            _SectionDivider(),
            
            // 3. LayoutBuilder Example
            _SectionTitle(title: '3. LayoutBuilder for Adaptive Layouts'),
            LayoutBuilderDemo(),
            _SectionDivider(),
            
            // 4. Responsive Grid Example
            _SectionTitle(title: '4. Responsive Grid Layout'),
            ResponsiveGridDemo(),
          ],
        ),
      ),
    );
  }
}

// 1. MediaQuery Demo
class MediaQueryDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Get screen size information
    var mediaQuery = MediaQuery.of(context);
    var screenWidth = mediaQuery.size.width;
    var screenHeight = mediaQuery.size.height;
    var orientation = mediaQuery.orientation;
    var devicePixelRatio = mediaQuery.devicePixelRatio;
    var textScaleFactor = mediaQuery.textScaleFactor;
    var viewInsets = mediaQuery.viewInsets;
    var padding = mediaQuery.padding;
    
    return Card(
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Device Information:',
              style: TextStyle(fontWeight: FontWeight.bold, fontSize: 18),
            ),
            SizedBox(height: 8),
            _InfoRow('Screen Width', '${screenWidth.toStringAsFixed(2)} px'),
            _InfoRow('Screen Height', '${screenHeight.toStringAsFixed(2)} px'),
            _InfoRow('Orientation', '$orientation'),
            _InfoRow('Device Pixel Ratio', devicePixelRatio.toString()),
            _InfoRow('Text Scale Factor', textScaleFactor.toString()),
            _InfoRow('View Insets Bottom', viewInsets.bottom.toString()),
            _InfoRow('Safe Area Top', padding.top.toString()),
            _InfoRow('Safe Area Bottom', padding.bottom.toString()),
            
            SizedBox(height: 16),
            
            // Responsive behavior based on screen width
            Container(
              width: double.infinity,
              padding: EdgeInsets.all(16),
              color: screenWidth < 400 ? Colors.red[100] :
                     screenWidth < 600 ? Colors.green[100] : Colors.blue[100],
              child: Column(
                children: [
                  Text(
                    screenWidth < 400 ? 'Small Screen' :
                    screenWidth < 600 ? 'Medium Screen' : 'Large Screen',
                    style: TextStyle(
                      fontWeight: FontWeight.bold,
                      fontSize: 16,
                    ),
                  ),
                  SizedBox(height: 8),
                  Text('Responsive container changes color based on width'),
                ],
              ),
            ),
          ],
        ),
      ),
    );
  }
}

// Helper widget for displaying information rows
class _InfoRow extends StatelessWidget {
  final String label;
  final String value;
  
  const _InfoRow(this.label, this.value);
  
  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.symmetric(vertical: 4),
      child: Row(
        children: [
          Expanded(
            flex: 2,
            child: Text(label, style: TextStyle(fontWeight: FontWeight.w500)),
          ),
          Expanded(
            flex: 3,
            child: Text(value),
          ),
        ],
      ),
    );
  }
}

// 2. Orientation-based Layout
class OrientationLayoutDemo extends StatelessWidget {
  final List<Color> colors = [
    Colors.red,
    Colors.green,
    Colors.blue,
    Colors.yellow,
    Colors.purple,
    Colors.orange,
  ];
  
  @override
  Widget build(BuildContext context) {
    return OrientationBuilder(
      builder: (context, orientation) {
        return Card(
          child: Padding(
            padding: EdgeInsets.all(16),
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  'Current Orientation: $orientation',
                  style: TextStyle(
                    fontWeight: FontWeight.bold,
                    fontSize: 16,
                  ),
                ),
                Text(
                  orientation == Orientation.portrait
                      ? 'Grid shows 2 items per row'
                      : 'Grid shows 4 items per row',
                ),
                SizedBox(height: 16),
                
                // Grid with orientation-dependent crossAxisCount
                GridView.builder(
                  shrinkWrap: true,
                  physics: NeverScrollableScrollPhysics(),
                  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                    crossAxisCount: orientation == Orientation.portrait ? 2 : 4,
                    childAspectRatio: 1.0,
                    crossAxisSpacing: 8,
                    mainAxisSpacing: 8,
                  ),
                  itemCount: colors.length,
                  itemBuilder: (context, index) {
                    return Container(
                      color: colors[index],
                      child: Center(
                        child: Text(
                          'Item ${index + 1}',
                          style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                          ),
                        ),
                      ),
                    );
                  },
                ),
              ],
            ),
          ),
        );
      },
    );
  }
}

// 3. LayoutBuilder Demo
class LayoutBuilderDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'LayoutBuilder adapts to available space:',
              style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
            ),
            SizedBox(height: 16),
            
            // LayoutBuilder example
            Container(
              height: 200,
              color: Colors.grey[200],
              child: LayoutBuilder(
                builder: (BuildContext context, BoxConstraints constraints) {
                  // Determine layout based on available width
                  if (constraints.maxWidth < 300) {
                    return _buildSmallLayout(constraints);
                  } else if (constraints.maxWidth < 500) {
                    return _buildMediumLayout(constraints);
                  } else {
                    return _buildLargeLayout(constraints);
                  }
                },
              ),
            ),
            SizedBox(height: 16),
            
            // Resizable container to demonstrate LayoutBuilder
            Text('Resize this container to see LayoutBuilder in action:'),
            SizedBox(height: 8),
            ResizableContainer(),
          ],
        ),
      ),
    );
  }
  
  Widget _buildSmallLayout(BoxConstraints constraints) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Icon(Icons.smartphone, size: 50),
          SizedBox(height: 16),
          Text(
            'Small Layout',
            style: TextStyle(fontWeight: FontWeight.bold),
          ),
          Text('Width: ${constraints.maxWidth.toStringAsFixed(1)}'),
          Text('Height: ${constraints.maxHeight.toStringAsFixed(1)}'),
        ],
      ),
    );
  }
  
  Widget _buildMediumLayout(BoxConstraints constraints) {
    return Center(
      child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
        children: [
          Icon(Icons.tablet, size: 50),
          Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Text(
                'Medium Layout',
                style: TextStyle(fontWeight: FontWeight.bold),
              ),
              Text('Width: ${constraints.maxWidth.toStringAsFixed(1)}'),
              Text('Height: ${constraints.maxHeight.toStringAsFixed(1)}'),
            ],
          ),
        ],
      ),
    );
  }
  
  Widget _buildLargeLayout(BoxConstraints constraints) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        Icon(Icons.laptop, size: 50),
        Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              'Large Layout',
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
            Text('Width: ${constraints.maxWidth.toStringAsFixed(1)}'),
            Text('Height: ${constraints.maxHeight.toStringAsFixed(1)}'),
          ],
        ),
        Container(
          width: 100,
          height: 100,
          color: Colors.blue[100],
          child: Center(
            child: Text('Extra Content'),
          ),
        ),
      ],
    );
  }
}

// Resizable container for demonstration
class ResizableContainer extends StatefulWidget {
  @override
  _ResizableContainerState createState() => _ResizableContainerState();
}

class _ResizableContainerState extends State<ResizableContainer> {
  double _width = 200;
  
  @override
  Widget build(BuildContext context) {
    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Container(
          width: _width,
          height: 100,
          color: Colors.amber[100],
          child: LayoutBuilder(
            builder: (context, constraints) {
              String sizeCategory = '';
              Color textColor = Colors.black;
              
              if (constraints.maxWidth < 300) {
                sizeCategory = 'Small';
                textColor = Colors.red;
              } else if (constraints.maxWidth < 500) {
                sizeCategory = 'Medium';
                textColor = Colors.green[800]!;
              } else {
                sizeCategory = 'Large';
                textColor = Colors.blue;
              }
              
              return Center(
                child: Text(
                  '$sizeCategory Container\nWidth: ${_width.toInt()}',
                  textAlign: TextAlign.center,
                  style: TextStyle(
                    color: textColor,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              );
            },
          ),
        ),
        SizedBox(height: 16),
        Text('Drag to resize:'),
        Slider(
          min: 100,
          max: MediaQuery.of(context).size.width - 32, // Full width minus padding
          value: _width,
          onChanged: (value) {
            setState(() {
              _width = value;
            });
          },
        ),
      ],
    );
  }
}

// 4. Responsive Grid Layout
class ResponsiveGridDemo extends StatelessWidget {
  final List<String> items = List.generate(9, (index) => 'Item ${index + 1}');
  
  @override
  Widget build(BuildContext context) {
    return Card(
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Responsive Grid Example:',
              style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16),
            ),
            Text('Grid adjusts columns based on available width'),
            SizedBox(height: 16),
            
            LayoutBuilder(
              builder: (context, constraints) {
                // Calculate columns based on available width
                int crossAxisCount;
                if (constraints.maxWidth < 400) {
                  crossAxisCount = 1;
                } else if (constraints.maxWidth < 600) {
                  crossAxisCount = 2;
                } else if (constraints.maxWidth < 900) {
                  crossAxisCount = 3;
                } else {
                  crossAxisCount = 4;
                }
                
                return GridView.builder(
                  shrinkWrap: true,
                  physics: NeverScrollableScrollPhysics(),
                  gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
                    crossAxisCount: crossAxisCount,
                    childAspectRatio: 2,
                    crossAxisSpacing: 10,
                    mainAxisSpacing: 10,
                  ),
                  itemCount: items.length,
                  itemBuilder: (context, index) {
                    return Container(
                      decoration: BoxDecoration(
                        gradient: LinearGradient(
                          colors: [
                            Colors.blue[200]!,
                            Colors.blue[400]!,
                          ],
                          begin: Alignment.topLeft,
                          end: Alignment.bottomRight,
                        ),
                        borderRadius: BorderRadius.circular(8),
                      ),
                      child: Center(
                        child: Text(
                          items[index],
                          style: TextStyle(
                            color: Colors.white,
                            fontWeight: FontWeight.bold,
                            fontSize: 18,
                          ),
                        ),
                      ),
                    );
                  },
                );
              },
            ),
          ],
        ),
      ),
    );
  }
}

// Helper widgets
class _SectionTitle extends StatelessWidget {
  final String title;
  
  const _SectionTitle({required this.title});
  
  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.symmetric(vertical: 16),
      child: Text(
        title,
        style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
      ),
    );
  }
}

class _SectionDivider extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Divider(thickness: 1.5, height: 32);
  }
}

class ResponsiveRowExample extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      padding: EdgeInsets.all(16),
      child: Row(
        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
        children: [
          Expanded(
            child: Container(
              height: 50,
              color: Colors.blue,
              child: Center(child: Text('Item 1', style: TextStyle(color: Colors.white))),
            ),
          ),
          SizedBox(width: 10),
          Expanded(
            child: Container(
              height: 50,
              color: Colors.green,
              child: Center(child: Text('Item 2', style: TextStyle(color: Colors.white))),
            ),
          ),
          SizedBox(width: 10),
          Expanded(
            child: Container(
              height: 50,
              color: Colors.orange,
              child: Center(child: Text('Item 3', style: TextStyle(color: Colors.white))),
            ),
          ),
        ],
      ),
    );
  }
}

#### Example pubspec.yaml Assets Configuration:
```yaml
flutter:
  assets:
    - assets/images/
    - assets/icons/
    - assets/fonts/
    
  fonts:
    - family: Roboto
      fonts:
        - asset: assets/fonts/Roboto-Regular.ttf
        - asset: assets/fonts/Roboto-Bold.ttf
          weight: 700
        - asset: assets/fonts/Roboto-Italic.ttf
          style: italic
```

#### Resources:
- [Adding assets and images](https://flutter.dev/docs/development/ui/assets-and-images)
- [Image class documentation](https://api.flutter.dev/flutter/widgets/Image-class.html)
- [Cached network image package](https://pub.dev/packages/cached_network_image)
- [SVG support in Flutter](https://pub.dev/packages/flutter_svg)

### Day 14: Gestures and Touch Events

#### Objectives:
- Learn how to handle user gestures and touch events  
- Implement touch-based interactions
- Create custom touch-based widgets

#### Key Topics:
1. Basic Touch Widgets
   - GestureDetector
   - InkWell
   - Buttons and interactive widgets

2. Gesture Recognition
   - Tap, double tap, long press
   - Drag and swipe
   - Pan and scale

3. Advanced Gestures
   - Custom gesture recognizers
   - Combining gestures
   - Dismissible widgets
   - Reorderable lists

4. Touch Feedback
   - Visual feedback
   - Haptic feedback
   - Animation responses

#### Sample Code - Gesture Handling:
```dart
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';

class GesturesExample extends StatefulWidget {
  @override
  _GesturesExampleState createState() => _GesturesExampleState();
}

class _GesturesExampleState extends State<GesturesExample> {
  String _lastGesture = 'None';
  double _scale = 1.0;
  double _rotation = 0.0;
  Color _containerColor = Colors.blue;
  
  // For drag examples
  Offset _dragPosition = Offset(0, 0);
  
  // For Dismissible example
  List<String> _items = List.generate(10, (index) => 'Item ${index + 1}');
  
  void _updateGesture(String gesture) {
    setState(() {
      _lastGesture = gesture;
    });
    HapticFeedback.lightImpact(); // Provide haptic feedback
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Gestures and Touch Events')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Display last detected gesture
            Container(
              padding: EdgeInsets.all(16),
              decoration: BoxDecoration(
                color: Colors.grey[200],
                borderRadius: BorderRadius.circular(8),
              ),
              child: Row(
                children: [
                  Icon(Icons.touch_app),
                  SizedBox(width: 8),
                  Text(
                    'Last gesture: $_lastGesture',
                    style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                  ),
                ],
              ),
            ),
            SizedBox(height: 24),
            
            // 1. Basic Tap Gestures
            Text('1. Basic Tap Gestures', 
                 style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Simple tap with GestureDetector
                Column(
                  children: [
                    Text('Tap'),
                    SizedBox(height: 8),
                    GestureDetector(
                      onTap: () => _updateGesture('Tap'),
                      child: Container(
                        width: 100,
                        height: 100,
                        color: Colors.blue,
                        child: Center(
                          child: Text(
                            'Tap me',
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
                
                // Double tap
                Column(
                  children: [
                    Text('Double Tap'),
                    SizedBox(height: 8),
                    GestureDetector(
                      onDoubleTap: () => _updateGesture('Double Tap'),
                      child: Container(
                        width: 100,
                        height: 100,
                        color: Colors.green,
                        child: Center(
                          child: Text(
                            'Double Tap',
                            textAlign: TextAlign.center,
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
                
                // Long press
                Column(
                  children: [
                    Text('Long Press'),
                    SizedBox(height: 8),
                    GestureDetector(
                      onLongPress: () => _updateGesture('Long Press'),
                      child: Container(
                        width: 100,
                        height: 100,
                        color: Colors.red,
                        child: Center(
                          child: Text(
                            'Long Press',
                            textAlign: TextAlign.center,
                            style: TextStyle(color: Colors.white),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ],
            ),
            SizedBox(height: 24),
            
            // 2. InkWell with Ripple Effect
            Text('2. InkWell with Ripple Effect', 
                 style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            
            Center(
              child: Column(
                children: [
                  Text('InkWell'),
                  SizedBox(height: 8),
                  Material(
                    color: Colors.transparent,
                    child: InkWell(
                      onTap: () => _updateGesture('InkWell Tap'),
                      splashColor: Colors.purple,
                      highlightColor: Colors.purpleAccent.withOpacity(0.5),
                      borderRadius: BorderRadius.circular(8),
                      child: Container(
                        width: 200,
                        height: 100,
                        decoration: BoxDecoration(
                          borderRadius: BorderRadius.circular(8),
                          border: Border.all(color: Colors.purple, width: 2),
                        ),
                        child: Center(
                          child: Text(
                            'Tap for ripple effect',
                            style: TextStyle(
                              color: Colors.purple, 
                              fontWeight: FontWeight.bold,
                            ),
                          ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
            ),
            SizedBox(height: 24),
            
            // 3. Drag Gestures
            Text('3. Drag Gestures', 
                 style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            
            Container(
              height: 200,
              decoration: BoxDecoration(
                color: Colors.grey[200],
                borderRadius: BorderRadius.circular(8),
              ),
              child: Stack(
                children: [
                  // Draggable item
                  Positioned(
                    left: _dragPosition.dx,
                    top: _dragPosition.dy,
                    child: GestureDetector(
                      onPanUpdate: (details) {
                        setState(() {
                          _dragPosition = Offset(
                            _dragPosition.dx + details.delta.dx,
                            _dragPosition.dy + details.delta.dy,
                          );
                          _updateGesture('Pan/Drag: ${details.delta.toString()}');
                        });
                      },
                      child: Container(
                        width: 80,
                        height: 80,
                        decoration: BoxDecoration(
                          color: Colors.orange,
                          borderRadius: BorderRadius.circular(40),
                          boxShadow: [
                            BoxShadow(
                              color: Colors.black26,
                              blurRadius: 10,
                              offset: Offset(0, 3),
                            ),
                          ],
                        ),
                        child: Center(
                          child: Text(
                            'Drag me',
                            style: TextStyle(
                              color: Colors.white,
                              fontWeight: FontWeight.bold,
                            ),
                          ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
            ),
            Align(
              alignment: Alignment.centerRight,
              child: TextButton(
                onPressed: () {
                  setState(() {
                    _dragPosition = Offset(0, 0);
                  });
                },
                child: Text('Reset Position'),
              ),
            ),
            SizedBox(height: 24),
            
            // 4. Dismissible Items
            Text('4. Dismissible Widgets', 
                 style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            
            Container(
              decoration: BoxDecoration(
                border: Border.all(color: Colors.grey),
                borderRadius: BorderRadius.circular(8),
              ),
              child: Column(
                children: _items.map((item) {
                  return Dismissible(
                    key: Key(item),
                    background: Container(
                      color: Colors.green,
                      alignment: Alignment.centerLeft,
                      padding: EdgeInsets.only(left: 20),
                      child: Icon(Icons.archive, color: Colors.white),
                    ),
                    secondaryBackground: Container(
                      color: Colors.red,
                      alignment: Alignment.centerRight,
                      padding: EdgeInsets.only(right: 20),
                      child: Icon(Icons.delete, color: Colors.white),
                    ),
                    onDismissed: (direction) {
                      setState(() {
                        _items.remove(item);
                      });
                      
                      ScaffoldMessenger.of(context).showSnackBar(
                        SnackBar(
                          content: Text(
                            direction == DismissDirection.startToEnd
                                ? '$item archived'
                                : '$item deleted',
                          ),
                          action: SnackBarAction(
                            label: 'UNDO',
                            onPressed: () {
                              setState(() {
                                _items.add(item);
                              });
                            },
                          ),
                        ),
                      );
                    },
                    child: ListTile(
                      title: Text(item),
                      subtitle: Text('Swipe left to delete, right to archive'),
                    ),
                  );
                }).toList(),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Gesture detection](https://flutter.dev/docs/development/ui/advanced/gestures)
- [GestureDetector class](https://api.flutter.dev/flutter/widgets/GestureDetector-class.html)
- [Dismissible widget](https://flutter.dev/docs/cookbook/gestures/dismissible)
- [Drag detection](https://flutter.dev/docs/cookbook/gestures/handling-taps)

## Week 3: State Management

### Day 15: State Management Basics

#### Objectives:
- Understand what state is in Flutter applications
- Learn different state management approaches
- Choose the right state management solution for your app

#### Key Topics:
1. Understanding State
   - UI state vs App state
   - Local vs Global state
   - When to use different state types

2. Lifting State Up
   - Sharing state between widgets
   - Callback functions
   - Passing data up and down the widget tree

3. InheritedWidget
   - Flutter's built-in state management
   - Context and dependency
   - Understanding widget rebuilding

4. setState vs State Management Solutions
   - Limitations of setState
   - When to use external solutions
   - Overview of popular state management libraries

#### Sample Code - Basic State Management:
```dart
import 'package:flutter/material.dart';

// 1. Local state with StatefulWidget
class CounterWidget extends StatefulWidget {
  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(16),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Local State with StatefulWidget',
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            Text('Counter: $_counter'),
            SizedBox(height: 8),
            ElevatedButton(
              onPressed: _incrementCounter,
              child: Text('Increment'),
            ),
          ],
        ),
      ),
    );
  }
}

// 2. Lifting state up
class ParentWidget extends StatefulWidget {
  @override
  _ParentWidgetState createState() => _ParentWidgetState();
}

class _ParentWidgetState extends State<ParentWidget> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(16),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Lifting State Up',
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            Text(
              'This parent widget manages the state and passes it to children',
              style: TextStyle(fontStyle: FontStyle.italic),
            ),
            SizedBox(height: 16),
            Text('Counter: $_counter'),
            SizedBox(height: 8),
            // Pass state down to child
            ChildWidget(
              counter: _counter,
              onIncrement: _incrementCounter,
            ),
          ],
        ),
      ),
    );
  }
}

class ChildWidget extends StatelessWidget {
  final int counter;
  final VoidCallback onIncrement;
  
  ChildWidget({
    required this.counter,
    required this.onIncrement,
  });
  
  @override
  Widget build(BuildContext context) {
    return Container(
      padding: EdgeInsets.all(16),
      color: Colors.grey[200],
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text('Child Widget'),
          Text('Counter value from parent: $counter'),
          SizedBox(height: 8),
          ElevatedButton(
            onPressed: onIncrement,
            child: Text('Increment (from child)'),
          ),
        ],
      ),
    );
  }
}

// 3. InheritedWidget example
class CounterInheritedWidget extends InheritedWidget {
  final int counter;
  final Function incrementCounter;
  
  CounterInheritedWidget({
    required this.counter,
    required this.incrementCounter,
    required Widget child,
  }) : super(child: child);
  
  static CounterInheritedWidget of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<CounterInheritedWidget>()!;
  }
  
  @override
  bool updateShouldNotify(CounterInheritedWidget oldWidget) {
    return counter != oldWidget.counter;
  }
}

class InheritedWidgetExample extends StatefulWidget {
  @override
  _InheritedWidgetExampleState createState() => _InheritedWidgetExampleState();
}

class _InheritedWidgetExampleState extends State<InheritedWidgetExample> {
  int _counter = 0;
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return CounterInheritedWidget(
      counter: _counter,
      incrementCounter: _incrementCounter,
      child: Card(
        margin: EdgeInsets.all(16),
        child: Padding(
          padding: EdgeInsets.all(16),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              Text(
                'InheritedWidget Example',
                style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
              ),
              SizedBox(height: 16),
              Text(
                'InheritedWidget provides state to descendants without prop drilling',
                style: TextStyle(fontStyle: FontStyle.italic),
              ),
              SizedBox(height: 16),
              // These widgets can access the InheritedWidget
              DeepChildWidget(),
              DeeperChildWidget(),
            ],
          ),
        ),
      ),
    );
  }
}

class DeepChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = CounterInheritedWidget.of(context);
    
    return Container(
      padding: EdgeInsets.all(16),
      margin: EdgeInsets.only(bottom: 16),
      color: Colors.blue[100],
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text('Deep Child'),
          Text('Counter from InheritedWidget: ${inheritedWidget.counter}'),
          SizedBox(height: 8),
          ElevatedButton(
            onPressed: () => inheritedWidget.incrementCounter(),
            child: Text('Increment'),
          ),
        ],
      ),
    );
  }
}

class DeeperChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = CounterInheritedWidget.of(context);
    
    return Container(
      padding: EdgeInsets.all(16),
      color: Colors.red[100],
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text('Deeper Child'),
          Text('Counter from InheritedWidget: ${inheritedWidget.counter}'),
          SizedBox(height: 8),
          ElevatedButton(
            onPressed: () => inheritedWidget.incrementCounter(),
            child: Text('Increment'),
          ),
        ],
      ),
    );
  }
}
```

#### Resources:
- [Flutter State Management Options](https://flutter.dev/docs/development/data-and-backend/state-mgmt/options)
- [Simple App State Management](https://flutter.dev/docs/development/data-and-backend/state-mgmt/simple)
- [InheritedWidget documentation](https://api.flutter.dev/flutter/widgets/InheritedWidget-class.html)
- [Effective Dart: State Management](https://dart.dev/guides/language/effective-dart/usage)

### Day 16: Provider Package

#### Objectives:
- Learn how to use the Provider package for state management
- Understand the basics of Provider
- Implement Provider in your Flutter application

#### Key Topics:
1. Understanding Provider
   - What is Provider?
   - Why use Provider?
   - Basic usage

2. Creating a Provider
   - Using ChangeNotifierProvider
   - Using Consumer
   - Using Provider.of

3. Provider with InheritedWidget
   - Using InheritedProvider
   - Combining Provider and InheritedWidget

4. Advanced Provider Patterns
   - Using MultiProvider
   - Using ChangeNotifierProvider.value
   - Using ProxyProvider

#### Sample Code - Provider Usage:
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer<CounterProvider>(
        builder: (context, counterProvider, child) {
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Provider documentation](https://pub.dev/packages/provider)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Provider best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/provider)

### Day 17: Riverpod Package

#### Objectives:
- Learn how to use the Riverpod package for state management
- Understand the basics of Riverpod
- Implement Riverpod in your Flutter application

#### Key Topics:
1. Understanding Riverpod
   - What is Riverpod?
   - Why use Riverpod?
   - Basic usage

2. Creating a Riverpod
   - Using Provider
   - Using Riverpod.autoDispose
   - Using Riverpod.family

3. Riverpod with InheritedWidget
   - Using InheritedRiverpod
   - Combining Riverpod and InheritedWidget

4. Advanced Riverpod Patterns
   - Using MultiRiverpod
   - Using Riverpod.autoDispose.value
   - Using Riverpod.family.value

#### Sample Code - Riverpod Usage:
```dart
import 'package:flutter/material.dart';
import 'package:riverpod/riverpod.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer(
        builder: (context, ref, child) {
          final counterProvider = ref.watch(counterProviderProvider);
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Riverpod documentation](https://pub.dev/packages/riverpod)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Riverpod best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/riverpod)

### Day 18: BLoC Pattern

#### Objectives:
- Learn how to implement the BLoC pattern for state management
- Understand the basics of BLoC
- Implement BLoC in your Flutter application

#### Key Topics:
1. Understanding BLoC
   - What is BLoC?
   - Why use BLoC?
   - Basic usage

2. Creating a BLoC
   - Using StreamController
   - Using Stream
   - Using Bloc

3. BLoC with InheritedWidget
   - Using InheritedBloc
   - Combining BLoC and InheritedWidget

4. Advanced BLoC Patterns
   - Using MultiBloc
   - Using Bloc.observer
   - Using Bloc.event

#### Sample Code - BLoC Usage:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

class CounterBloc extends Bloc<CounterEvent, int> {
  CounterBloc() : super(0) {
    on<IncrementEvent>((event, emit) => emit(state + 1));
    on<DecrementEvent>((event, emit) => emit(state - 1));
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return BlocProvider(
      create: (context) => CounterBloc(),
      child: BlocConsumer<CounterBloc, int>(
        listener: (context, state) {
          // Add your listener logic here
        },
        builder: (context, state) {
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: $state',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: Row(
              mainAxisAlignment: MainAxisAlignment.end,
              children: [
                FloatingActionButton(
                  onPressed: () => context.read<CounterBloc>().add(IncrementEvent()),
                  child: Icon(Icons.add),
                ),
                SizedBox(width: 10),
                FloatingActionButton(
                  onPressed: () => context.read<CounterBloc>().add(DecrementEvent()),
                  child: Icon(Icons.remove),
                ),
              ],
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Bloc documentation](https://pub.dev/packages/flutter_bloc)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Bloc best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/bloc)

### Day 19: Cubit Pattern

#### Objectives:
- Learn how to implement the Cubit pattern for state management
- Understand the basics of Cubit
- Implement Cubit in your Flutter application

#### Key Topics:
1. Understanding Cubit
   - What is Cubit?
   - Why use Cubit?
   - Basic usage

2. Creating a Cubit
   - Using Cubit
   - Using Cubit.value
   - Using Cubit.event

3. Cubit with InheritedWidget
   - Using InheritedCubit
   - Combining Cubit and InheritedWidget

4. Advanced Cubit Patterns
   - Using MultiCubit
   - Using Cubit.value.event
   - Using Cubit.event.value

#### Sample Code - Cubit Usage:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_cubit/flutter_cubit.dart';

class CounterCubit extends Cubit<int> {
  CounterCubit() : super(0);
  
  void increment() => emit(state + 1);
  void decrement() => emit(state - 1);
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return CubitProvider(
      create: (context) => CounterCubit(),
      child: Consumer<CounterCubit>(
        builder: (context, counterCubit, child) {
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterCubit.state}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: Row(
              mainAxisAlignment: MainAxisAlignment.end,
              children: [
                FloatingActionButton(
                  onPressed: counterCubit.increment,
                  child: Icon(Icons.add),
                ),
                SizedBox(width: 10),
                FloatingActionButton(
                  onPressed: counterCubit.decrement,
                  child: Icon(Icons.remove),
                ),
              ],
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Cubit documentation](https://pub.dev/packages/flutter_cubit)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Cubit best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/cubit)

### Day 20: Redux Pattern

#### Objectives:
- Learn how to implement the Redux pattern for state management
- Understand the basics of Redux
- Implement Redux in your Flutter application

#### Key Topics:
1. Understanding Redux
   - What is Redux?
   - Why use Redux?
   - Basic usage

2. Creating a Redux Store
   - Using Store
   - Using StoreProvider
   - Using StoreBuilder

3. Redux with InheritedWidget
   - Using InheritedStore
   - Combining Redux and InheritedWidget

4. Advanced Redux Patterns
   - Using Middleware
   - Using Thunks
   - Using Sagas

#### Sample Code - Redux Usage:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_redux/flutter_redux.dart';
import 'package:redux/redux.dart';

class CounterAction {
  final int value;
  CounterAction(this.value);
}

int counterReducer(int state, dynamic action) {
  if (action is CounterAction) {
    return state + action.value;
  }
  return state;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final store = Store<int>(
      counterReducer,
      initialState: 0,
    );
    
    return StoreProvider(
      store: store,
      child: Scaffold(
        appBar: AppBar(title: Text('Counter')),
        body: Center(
          child: Text(
            'Counter: ${store.state}',
            style: Theme.of(context).textTheme.headline4,
          ),
        ),
        floatingActionButton: Row(
          mainAxisAlignment: MainAxisAlignment.end,
          children: [
            FloatingActionButton(
              onPressed: () => store.dispatch(CounterAction(1)),
              child: Icon(Icons.add),
            ),
            SizedBox(width: 10),
            FloatingActionButton(
              onPressed: () => store.dispatch(CounterAction(-1)),
              child: Icon(Icons.remove),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Redux documentation](https://pub.dev/packages/flutter_redux)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Redux best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/redux)

### Day 21: MobX Pattern

#### Objectives:
- Learn how to implement the MobX pattern for state management
- Understand the basics of MobX
- Implement MobX in your Flutter application

#### Key Topics:
1. Understanding MobX
   - What is MobX?
   - Why use MobX?
   - Basic usage

2. Creating a MobX Store
   - Using Store
   - Using StoreProvider
   - Using StoreBuilder

3. MobX with InheritedWidget
   - Using InheritedStore
   - Combining MobX and InheritedWidget

4. Advanced MobX Patterns
   - Using Middleware
   - Using Thunks
   - Using Sagas

#### Sample Code - MobX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_mobx/flutter_mobx.dart';
import 'package:mobx/mobx.dart';

class CounterStore {
  @observable
  int counter = 0;
  
  @action
  void increment() => counter++;
  
  @action
  void decrement() => counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final counterStore = CounterStore();
    
    return MobxProvider(
      create: () => counterStore,
      child: Scaffold(
        appBar: AppBar(title: Text('Counter')),
        body: Center(
          child: Obx(() => Text(
            'Counter: ${counterStore.counter}',
            style: Theme.of(context).textTheme.headline4,
          )),
        ),
        floatingActionButton: Row(
          mainAxisAlignment: MainAxisAlignment.end,
          children: [
            FloatingActionButton(
              onPressed: counterStore.increment,
              child: Icon(Icons.add),
            ),
            SizedBox(width: 10),
            FloatingActionButton(
              onPressed: counterStore.decrement,
              child: Icon(Icons.remove),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [MobX documentation](https://pub.dev/packages/flutter_mobx)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [MobX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/mobx)

### Day 22: GetX Pattern

#### Objectives:
- Learn how to implement the GetX pattern for state management
- Understand the basics of GetX
- Implement GetX in your Flutter application

#### Key Topics:
1. Understanding GetX
   - What is GetX?
   - Why use GetX?
   - Basic usage

2. Creating a GetX Controller
   - Using GetXController
   - Using GetX.lazyPut
   - Using GetX.put

3. GetX with InheritedWidget
   - Using InheritedGetX
   - Combining GetX and InheritedWidget

4. Advanced GetX Patterns
   - Using GetX.keepAlive
   - Using GetX.smartManagement
   - Using GetX.arguments

#### Sample Code - GetX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:get/get.dart';

class CounterController extends GetxController {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() => _counter++;
  void decrement() => _counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GetX<CounterController>(
      init: CounterController(),
      builder: (controller) {
        return Scaffold(
          appBar: AppBar(title: Text('Counter')),
          body: Center(
            child: Text(
              'Counter: ${controller.counter}',
              style: Theme.of(context).textTheme.headline4,
            ),
          ),
          floatingActionButton: Row(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              FloatingActionButton(
                onPressed: controller.increment,
                child: Icon(Icons.add),
              ),
              SizedBox(width: 10),
              FloatingActionButton(
                onPressed: controller.decrement,
                child: Icon(Icons.remove),
              ),
            ],
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [GetX documentation](https://pub.dev/packages/get)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [GetX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/getx)

### Day 23: State Management with Cubit

#### Objectives:
- Learn how to use the Cubit pattern for state management
- Understand the basics of Cubit
- Implement Cubit in your Flutter application

#### Key Topics:
1. Understanding Cubit
   - What is Cubit?
   - Why use Cubit?
   - Basic usage

2. Creating a Cubit
   - Using Cubit
   - Using Cubit.value
   - Using Cubit.event

3. Cubit with InheritedWidget
   - Using InheritedCubit
   - Combining Cubit and InheritedWidget

4. Advanced Cubit Patterns
   - Using MultiCubit
   - Using Cubit.value.event
   - Using Cubit.event.value

#### Sample Code - Cubit Usage:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_cubit/flutter_cubit.dart';

class CounterCubit extends Cubit<int> {
  CounterCubit() : super(0);
  
  void increment() => emit(state + 1);
  void decrement() => emit(state - 1);
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return CubitProvider(
      create: (context) => CounterCubit(),
      child: Consumer<CounterCubit>(
        builder: (context, counterCubit, child) {
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterCubit.state}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: Row(
              mainAxisAlignment: MainAxisAlignment.end,
              children: [
                FloatingActionButton(
                  onPressed: counterCubit.increment,
                  child: Icon(Icons.add),
                ),
                SizedBox(width: 10),
                FloatingActionButton(
                  onPressed: counterCubit.decrement,
                  child: Icon(Icons.remove),
                ),
              ],
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Cubit documentation](https://pub.dev/packages/flutter_cubit)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Cubit best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/cubit)

### Day 24: State Management with Riverpod

#### Objectives:
- Learn how to use the Riverpod package for state management
- Understand the basics of Riverpod
- Implement Riverpod in your Flutter application

#### Key Topics:
1. Understanding Riverpod
   - What is Riverpod?
   - Why use Riverpod?
   - Basic usage

2. Creating a Riverpod
   - Using Provider
   - Using Riverpod.autoDispose
   - Using Riverpod.family

3. Riverpod with InheritedWidget
   - Using InheritedRiverpod
   - Combining Riverpod and InheritedWidget

4. Advanced Riverpod Patterns
   - Using MultiRiverpod
   - Using Riverpod.autoDispose.value
   - Using Riverpod.family.value

#### Sample Code - Riverpod Usage:
```dart
import 'package:flutter/material.dart';
import 'package:riverpod/riverpod.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer(
        builder: (context, ref, child) {
          final counterProvider = ref.watch(counterProviderProvider);
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Riverpod documentation](https://pub.dev/packages/riverpod)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Riverpod best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/riverpod)

### Day 25: State Management with GetX

#### Objectives:
- Learn how to use the GetX package for state management
- Understand the basics of GetX
- Implement GetX in your Flutter application

#### Key Topics:
1. Understanding GetX
   - What is GetX?
   - Why use GetX?
   - Basic usage

2. Creating a GetX Controller
   - Using GetXController
   - Using GetX.lazyPut
   - Using GetX.put

3. GetX with InheritedWidget
   - Using InheritedGetX
   - Combining GetX and InheritedWidget

4. Advanced GetX Patterns
   - Using GetX.keepAlive
   - Using GetX.smartManagement
   - Using GetX.arguments

#### Sample Code - GetX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:get/get.dart';

class CounterController extends GetxController {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() => _counter++;
  void decrement() => _counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GetX<CounterController>(
      init: CounterController(),
      builder: (controller) {
        return Scaffold(
          appBar: AppBar(title: Text('Counter')),
          body: Center(
            child: Text(
              'Counter: ${controller.counter}',
              style: Theme.of(context).textTheme.headline4,
            ),
          ),
          floatingActionButton: Row(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              FloatingActionButton(
                onPressed: controller.increment,
                child: Icon(Icons.add),
              ),
              SizedBox(width: 10),
              FloatingActionButton(
                onPressed: controller.decrement,
                child: Icon(Icons.remove),
              ),
            ],
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [GetX documentation](https://pub.dev/packages/get)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [GetX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/getx)

### Day 26: State Management with Riverpod

#### Objectives:
- Learn how to use the Riverpod package for state management
- Understand the basics of Riverpod
- Implement Riverpod in your Flutter application

#### Key Topics:
1. Understanding Riverpod
   - What is Riverpod?
   - Why use Riverpod?
   - Basic usage

2. Creating a Riverpod
   - Using Provider
   - Using Riverpod.autoDispose
   - Using Riverpod.family

3. Riverpod with InheritedWidget
   - Using InheritedRiverpod
   - Combining Riverpod and InheritedWidget

4. Advanced Riverpod Patterns
   - Using MultiRiverpod
   - Using Riverpod.autoDispose.value
   - Using Riverpod.family.value

#### Sample Code - Riverpod Usage:
```dart
import 'package:flutter/material.dart';
import 'package:riverpod/riverpod.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer(
        builder: (context, ref, child) {
          final counterProvider = ref.watch(counterProviderProvider);
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Riverpod documentation](https://pub.dev/packages/riverpod)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Riverpod best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/riverpod)

### Day 27: State Management with GetX

#### Objectives:
- Learn how to use the GetX package for state management
- Understand the basics of GetX
- Implement GetX in your Flutter application

#### Key Topics:
1. Understanding GetX
   - What is GetX?
   - Why use GetX?
   - Basic usage

2. Creating a GetX Controller
   - Using GetXController
   - Using GetX.lazyPut
   - Using GetX.put

3. GetX with InheritedWidget
   - Using InheritedGetX
   - Combining GetX and InheritedWidget

4. Advanced GetX Patterns
   - Using GetX.keepAlive
   - Using GetX.smartManagement
   - Using GetX.arguments

#### Sample Code - GetX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:get/get.dart';

class CounterController extends GetxController {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() => _counter++;
  void decrement() => _counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GetX<CounterController>(
      init: CounterController(),
      builder: (controller) {
        return Scaffold(
          appBar: AppBar(title: Text('Counter')),
          body: Center(
            child: Text(
              'Counter: ${controller.counter}',
              style: Theme.of(context).textTheme.headline4,
            ),
          ),
          floatingActionButton: Row(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              FloatingActionButton(
                onPressed: controller.increment,
                child: Icon(Icons.add),
              ),
              SizedBox(width: 10),
              FloatingActionButton(
                onPressed: controller.decrement,
                child: Icon(Icons.remove),
              ),
            ],
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [GetX documentation](https://pub.dev/packages/get)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [GetX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/getx)

### Day 28: State Management with Riverpod

#### Objectives:
- Learn how to use the Riverpod package for state management
- Understand the basics of Riverpod
- Implement Riverpod in your Flutter application

#### Key Topics:
1. Understanding Riverpod
   - What is Riverpod?
   - Why use Riverpod?
   - Basic usage

2. Creating a Riverpod
   - Using Provider
   - Using Riverpod.autoDispose
   - Using Riverpod.family

3. Riverpod with InheritedWidget
   - Using InheritedRiverpod
   - Combining Riverpod and InheritedWidget

4. Advanced Riverpod Patterns
   - Using MultiRiverpod
   - Using Riverpod.autoDispose.value
   - Using Riverpod.family.value

#### Sample Code - Riverpod Usage:
```dart
import 'package:flutter/material.dart';
import 'package:riverpod/riverpod.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer(
        builder: (context, ref, child) {
          final counterProvider = ref.watch(counterProviderProvider);
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Riverpod documentation](https://pub.dev/packages/riverpod)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Riverpod best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/riverpod)

### Day 29: State Management with GetX

#### Objectives:
- Learn how to use the GetX package for state management
- Understand the basics of GetX
- Implement GetX in your Flutter application

#### Key Topics:
1. Understanding GetX
   - What is GetX?
   - Why use GetX?
   - Basic usage

2. Creating a GetX Controller
   - Using GetXController
   - Using GetX.lazyPut
   - Using GetX.put

3. GetX with InheritedWidget
   - Using InheritedGetX
   - Combining GetX and InheritedWidget

4. Advanced GetX Patterns
   - Using GetX.keepAlive
   - Using GetX.smartManagement
   - Using GetX.arguments

#### Sample Code - GetX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:get/get.dart';

class CounterController extends GetxController {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() => _counter++;
  void decrement() => _counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GetX<CounterController>(
      init: CounterController(),
      builder: (controller) {
        return Scaffold(
          appBar: AppBar(title: Text('Counter')),
          body: Center(
            child: Text(
              'Counter: ${controller.counter}',
              style: Theme.of(context).textTheme.headline4,
            ),
          ),
          floatingActionButton: Row(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              FloatingActionButton(
                onPressed: controller.increment,
                child: Icon(Icons.add),
              ),
              SizedBox(width: 10),
              FloatingActionButton(
                onPressed: controller.decrement,
                child: Icon(Icons.remove),
              ),
            ],
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [GetX documentation](https://pub.dev/packages/get)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [GetX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/getx)

### Day 30: State Management with Riverpod

#### Objectives:
- Learn how to use the Riverpod package for state management
- Understand the basics of Riverpod
- Implement Riverpod in your Flutter application

#### Key Topics:
1. Understanding Riverpod
   - What is Riverpod?
   - Why use Riverpod?
   - Basic usage

2. Creating a Riverpod
   - Using Provider
   - Using Riverpod.autoDispose
   - Using Riverpod.family

3. Riverpod with InheritedWidget
   - Using InheritedRiverpod
   - Combining Riverpod and InheritedWidget

4. Advanced Riverpod Patterns
   - Using MultiRiverpod
   - Using Riverpod.autoDispose.value
   - Using Riverpod.family.value

#### Sample Code - Riverpod Usage:
```dart
import 'package:flutter/material.dart';
import 'package:riverpod/riverpod.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer(
        builder: (context, ref, child) {
          final counterProvider = ref.watch(counterProviderProvider);
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Riverpod documentation](https://pub.dev/packages/riverpod)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Riverpod best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/riverpod)

### Day 31: State Management with GetX

#### Objectives:
- Learn how to use the GetX package for state management
- Understand the basics of GetX
- Implement GetX in your Flutter application

#### Key Topics:
1. Understanding GetX
   - What is GetX?
   - Why use GetX?
   - Basic usage

2. Creating a GetX Controller
   - Using GetXController
   - Using GetX.lazyPut
   - Using GetX.put

3. GetX with InheritedWidget
   - Using InheritedGetX
   - Combining GetX and InheritedWidget

4. Advanced GetX Patterns
   - Using GetX.keepAlive
   - Using GetX.smartManagement
   - Using GetX.arguments

#### Sample Code - GetX Usage:
```dart
import 'package:flutter/material.dart';
import 'package:get/get.dart';

class CounterController extends GetxController {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() => _counter++;
  void decrement() => _counter--;
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GetX<CounterController>(
      init: CounterController(),
      builder: (controller) {
        return Scaffold(
          appBar: AppBar(title: Text('Counter')),
          body: Center(
            child: Text(
              'Counter: ${controller.counter}',
              style: Theme.of(context).textTheme.headline4,
            ),
          ),
          floatingActionButton: Row(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              FloatingActionButton(
                onPressed: controller.increment,
                child: Icon(Icons.add),
              ),
              SizedBox(width: 10),
              FloatingActionButton(
                onPressed: controller.decrement,
                child: Icon(Icons.remove),
              ),
            ],
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [GetX documentation](https://pub.dev/packages/get)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [GetX best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/getx)

### Day 32: Advanced State Management Patterns

#### Objectives:
- Learn and implement advanced state management patterns
- Compare different state management approaches
- Understand when to use each approach

#### Key Topics:
1. Comparing State Management Solutions
   - Pros and cons of each approach
   - Performance considerations
   - Learning curve and team adoption

2. Combined Approaches
   - Using Provider with BLoC
   - Mixing local and global state
   - State management layering

3. Testing State Management
   - Unit testing state
   - Widget testing with state
   - Integration testing

4. Best Practices
   - State organization
   - Code structure
   - Separation of concerns

#### Sample Code - Advanced Provider Pattern:
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';

// Advanced Provider example with multiple providers
class CounterProvider extends ChangeNotifier {
  int _counter = 0;
  
  int get counter => _counter;
  
  void increment() {
    _counter++;
    notifyListeners();
  }
}

class CounterScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => CounterProvider(),
      child: Consumer<CounterProvider>(
        builder: (context, counterProvider, child) {
          return Scaffold(
            appBar: AppBar(title: Text('Counter')),
            body: Center(
              child: Text(
                'Counter: ${counterProvider.counter}',
                style: Theme.of(context).textTheme.headline4,
              ),
            ),
            floatingActionButton: FloatingActionButton(
              onPressed: counterProvider.increment,
              child: Icon(Icons.add),
            ),
          );
        },
      ),
    );
  }
}
```

#### Resources:
- [Provider documentation](https://pub.dev/packages/provider)
- [State Management in Flutter](https://flutter.dev/docs/development/data-and-backend/state-mgmt)
- [Provider best practices](https://flutter.dev/docs/development/data-and-backend/state-mgmt/provider)

### Day 33: HTTP and RESTful APIs

#### Objectives:
- Learn how to make HTTP requests in Flutter
- Understand RESTful API concepts
- Implement API integration in Flutter apps

#### Key Topics:
1. HTTP Basics
   - HTTP methods (GET, POST, PUT, DELETE)
   - Request/response structure
   - Status codes

2. Making API Calls
   - Using http package
   - Handling responses
   - Error handling

3. JSON Parsing
   - Manual JSON serialization
   - Using json_serializable
   - Nested objects and arrays

4. RESTful Best Practices
   - API service pattern
   - Repository pattern
   - Error handling strategies

#### Sample Code - API Integration:
```dart
import 'dart:convert';
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;

// Model class
class Post {
  final int id;
  final String title;
  final String body;
  
  Post({required this.id, required this.title, required this.body});
  
  factory Post.fromJson(Map<String, dynamic> json) {
    return Post(
      id: json['id'],
      title: json['title'],
      body: json['body'],
    );
  }
}

// API Service
class ApiService {
  final String baseUrl = 'https://jsonplaceholder.typicode.com';
  
  Future<List<Post>> getPosts() async {
    final response = await http.get(Uri.parse('$baseUrl/posts'));
    
    if (response.statusCode == 200) {
      List<dynamic> data = jsonDecode(response.body);
      return data.map((json) => Post.fromJson(json)).toList();
    } else {
      throw Exception('Failed to load posts: ${response.statusCode}');
    }
  }
  
  Future<Post> createPost(String title, String body) async {
    final response = await http.post(
      Uri.parse('$baseUrl/posts'),
      headers: {'Content-Type': 'application/json'},
      body: jsonEncode({
        'title': title,
        'body': body,
        'userId': 1,
      }),
    );
    
    if (response.statusCode == 201) {
      return Post.fromJson(jsonDecode(response.body));
    } else {
      throw Exception('Failed to create post: ${response.statusCode}');
    }
  }
}

// Usage in a widget
class ApiDemoScreen extends StatefulWidget {
  @override
  _ApiDemoScreenState createState() => _ApiDemoScreenState();
}

class _ApiDemoScreenState extends State<ApiDemoScreen> {
  final ApiService _apiService = ApiService();
  late Future<List<Post>> _futurePosts;
  
  @override
  void initState() {
    super.initState();
    _futuresPosts = _apiService.getPosts();
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('API Integration')),
      body: FutureBuilder<List<Post>>(
        future: _futuresPosts,
        builder: (context, snapshot) {
          if (snapshot.connectionState == ConnectionState.waiting) {
            return Center(child: CircularProgressIndicator());
          } else if (snapshot.hasError) {
            return Center(child: Text('Error: ${snapshot.error}'));
          } else if (snapshot.hasData) {
            return ListView.builder(
              itemCount: snapshot.data!.length,
              itemBuilder: (context, index) {
                final post = snapshot.data![index];
                return ListTile(
                  title: Text(post.title),
                  subtitle: Text(post.body),
                  leading: CircleAvatar(child: Text('${post.id}')),
                );
              },
            );
          } else {
            return Center(child: Text('No data available'));
          }
        },
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () async {
          try {
            final newPost = await _apiService.createPost(
              'New Post',
              'This is a new post created from Flutter'
            );
            ScaffoldMessenger.of(context).showSnackBar(
              SnackBar(content: Text('Created post with ID: ${newPost.id}')),
            );
          } catch (e) {
            ScaffoldMessenger.of(context).showSnackBar(
              SnackBar(content: Text('Error: $e')),
            );
          }
        },
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [HTTP package documentation](https://pub.dev/packages/http)
- [JSON and serialization guide](https://flutter.dev/docs/development/data-and-backend/json)
- [RESTful API best practices](https://flutter.dev/docs/cookbook/networking/fetch-data)
- [Error handling in Flutter](https://flutter.dev/docs/cookbook/networking/fetch-data#error-handling)

### Day 34: Local Data Storage

#### Objectives:
- Learn different methods for local data storage in Flutter
- Implement persistent storage in your applications
- Choose the right storage solution for different scenarios

#### Key Topics:
1. Shared Preferences
   - Storing simple key-value pairs
   - Reading and writing data
   - Limitations

2. SQLite Database with sqflite
   - Database creation and schema
   - CRUD operations
   - Transactions and queries

3. Hive NoSQL Database
   - Setting up Hive
   - Type adapters
   - CRUD operations

4. File Storage
   - Accessing device file system
   - Reading and writing files
   - Working with paths

#### Sample Code - Local Storage Examples:
```dart
import 'dart:io';
import 'package:flutter/material.dart';
import 'package:shared_preferences/shared_preferences.dart';
import 'package:sqflite/sqflite.dart';
import 'package:path/path.dart' as path;
import 'package:hive/hive.dart';
import 'package:hive_flutter/hive_flutter.dart';
import 'package:path_provider/path_provider.dart';

// 1. Shared Preferences Example
class SharedPreferencesDemo extends StatefulWidget {
  @override
  _SharedPreferencesDemoState createState() => _SharedPreferencesDemoState();
}

class _SharedPreferencesDemoState extends State<SharedPreferencesDemo> {
  final TextEditingController _controller = TextEditingController();
  String _savedText = '';
  
  @override
  void initState() {
    super.initState();
    _loadSavedText();
  }
  
  Future<void> _loadSavedText() async {
    final prefs = await SharedPreferences.getInstance();
    setState(() {
      _savedText = prefs.getString('savedText') ?? 'No saved text yet';
    });
  }
  
  Future<void> _saveText() async {
    final prefs = await SharedPreferences.getInstance();
    await prefs.setString('savedText', _controller.text);
    _loadSavedText();
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(16),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('Shared Preferences', style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            TextField(
              controller: _controller,
              decoration: InputDecoration(
                labelText: 'Enter text to save',
                border: OutlineInputBorder(),
              ),
            ),
            SizedBox(height: 8),
            ElevatedButton(
              onPressed: _saveText,
              child: Text('Save Text'),
            ),
            SizedBox(height: 16),
            Text('Last saved text: $_savedText'),
          ],
        ),
      ),
    );
  }
}

// 2. SQLite Database Example
class DatabaseHelper {
  static Database? _database;
  
  Future<Database> get database async {
    if (_database != null) return _database!;
    _database = await _initDatabase();
    return _database!;
  }
  
  Future<Database> _initDatabase() async {
    final dbPath = await getDatabasesPath();
    final pathToDatabase = path.join(dbPath, 'notes_database.db');
    
    return await openDatabase(
      pathToDatabase,
      version: 1,
      onCreate: (db, version) {
        return db.execute(
          'CREATE TABLE notes(id INTEGER PRIMARY KEY AUTOINCREMENT, title TEXT, content TEXT)',
        );
      },
    );
  }
  
  Future<void> insertNote(Map<String, dynamic> note) async {
    final db = await database;
    await db.insert(
      'notes',
      note,
      conflictAlgorithm: ConflictAlgorithm.replace,
    );
  }
  
  Future<List<Map<String, dynamic>>> getNotes() async {
    final db = await database;
    return await db.query('notes');
  }
  
  Future<void> updateNote(Map<String, dynamic> note) async {
    final db = await database;
    await db.update(
      'notes',
      note,
      where: 'id = ?',
      whereArgs: [note['id']],
    );
  }
  
  Future<void> deleteNote(int id) async {
    final db = await database;
    await db.delete(
      'notes',
      where: 'id = ?',
      whereArgs: [id],
    );
  }
}

// 3. Hive Example
@HiveType(typeId: 0)
class Task {
  @HiveField(0)
  final String id;
  
  @HiveField(1)
  final String title;
  
  @HiveField(2)
  bool isCompleted;
  
  Task({
    required this.id,
    required this.title,
    this.isCompleted = false,
  });
}

class HiveDemo extends StatefulWidget {
  @override
  _HiveDemoState createState() => _HiveDemoState();
}

class _HiveDemoState extends State<HiveDemo> {
  late Box<Task> _taskBox;
  final TextEditingController _controller = TextEditingController();
  
  @override
  void initState() {
    super.initState();
    _taskBox = Hive.box<Task>('tasks');
  }
  
  void _addTask() {
    final task = Task(
      id: DateTime.now().toString(),
      title: _controller.text,
    );
    _taskBox.add(task);
    _controller.clear();
  }
  
  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(16),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text('Hive Database', style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
            SizedBox(height: 8),
            TextField(
              controller: _controller,
              decoration: InputDecoration(
                labelText: 'New Task',
                border: OutlineInputBorder(),
              ),
            ),
            SizedBox(height: 8),
            ElevatedButton(
              onPressed: _addTask,
              child: Text('Add Task'),
            ),
            SizedBox(height: 16),
            ValueListenableBuilder(
              valueListenable: _taskBox.listenable(),
              builder: (context, Box<Task> box, _) {
                if (box.values.isEmpty) {
                  return Center(child: Text('No tasks yet'));
                }
                
                return ListView.builder(
                  shrinkWrap: true,
                  itemCount: box.values.length,
                  itemBuilder: (context, index) {
                    final task = box.getAt(index);
                    return ListTile(
                      title: Text(task!.title),
                      leading: Checkbox(
                        value: task.isCompleted,
                        onChanged: (val) {
                          task.isCompleted = val!;
                          box.putAt(index, task);
                        },
                      ),
                      trailing: IconButton(
                        icon: Icon(Icons.delete),
                        onPressed: () => box.deleteAt(index),
                      ),
                    );
                  },
                );
              },
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Shared Preferences package](https://pub.dev/packages/shared_preferences)
- [SQLite in Flutter with sqflite](https://pub.dev/packages/sqflite)
- [Hive database documentation](https://pub.dev/packages/hive)
- [Flutter File IO operations](https://flutter.dev/docs/cookbook/persistence/reading-writing-files)

### Day 35: Firebase Integration

#### Objectives:
- Learn how to integrate Firebase with Flutter apps
- Implement Firebase Authentication
- Use Firestore for cloud storage

#### Key Topics:
1. Firebase Setup
   - Creating Firebase project
   - Adding Flutter app to Firebase
   - Configuring dependencies

2. Firebase Authentication
   - Email/password authentication
   - Social auth (Google, Facebook)
   - Phone authentication

3. Cloud Firestore
   - Database structure
   - CRUD operations
   - Real-time updates

4. Firebase Storage
   - File uploads
   - Download and display
   - Security rules

#### Sample Code - Firebase Integration:
```dart
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';
import 'package:firebase_auth/firebase_auth.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import 'package:firebase_storage/firebase_storage.dart';
import 'package:image_picker/image_picker.dart';
import 'dart:io';

// Firebase Authentication
class AuthService {
  final FirebaseAuth _auth = FirebaseAuth.instance;
  
  // Sign in with email and password
  Future<UserCredential?> signInWithEmailAndPassword(String email, String password) async {
    try {
      return await _auth.signInWithEmailAndPassword(
        email: email,
        password: password,
      );
    } catch (e) {
      print('Sign in error: $e');
      return null;
    }
  }
  
  // Register with email and password
  Future<UserCredential?> registerWithEmailAndPassword(String email, String password) async {
    try {
      return await _auth.createUserWithEmailAndPassword(
        email: email,
        password: password,
      );
    } catch (e) {
      print('Registration error: $e');
      return null;
    }
  }
  
  // Sign out
  Future<void> signOut() async {
    await _auth.signOut();
  }
  
  // Get current user
  User? get currentUser => _auth.currentUser;
  
  // Auth state changes stream
  Stream<User?> get authStateChanges => _auth.authStateChanges();
}

// Firestore Database Service
class DatabaseService {
  final FirebaseFirestore _firestore = FirebaseFirestore.instance;
  
  // Collection reference
  final CollectionReference userCollection = 
      FirebaseFirestore.instance.collection('users');
  
  // Create/update user data
  Future<void> updateUserData(String uid, String name, String email) async {
    return await userCollection.doc(uid).set({
      'uid': uid,
      'name': name,
      'email': email,
      'lastUpdated': Timestamp.now(),
    });
  }
  
  // Get user document stream
  Stream<DocumentSnapshot> getUserData(String uid) {
    return userCollection.doc(uid).snapshots();
  }
  
  // Get all users stream
  Stream<QuerySnapshot> get users {
    return userCollection.snapshots();
  }
  
  // Add a task
  Future<void> addTask(String uid, String title, String description) async {
    return await userCollection
        .doc(uid)
        .collection('tasks')
        .add({
          'title': title,
          'description': description,
          'isCompleted': false,
          'createdAt': Timestamp.now(),
        });
  }
  
  // Get user tasks stream
  Stream<QuerySnapshot> getUserTasks(String uid) {
    return userCollection
        .doc(uid)
        .collection('tasks')
        .orderBy('createdAt', descending: true)
        .snapshots();
  }
  
  // Update task status
  Future<void> updateTaskStatus(String uid, String taskId, bool isCompleted) async {
    return await userCollection
        .doc(uid)
        .collection('tasks')
        .doc(taskId)
        .update({
          'isCompleted': isCompleted,
        });
  }
  
  // Delete task
  Future<void> deleteTask(String uid, String taskId) async {
    return await userCollection
        .doc(uid)
        .collection('tasks')
        .doc(taskId)
        .delete();
  }
}

// Firebase Storage Service
class StorageService {
  final FirebaseStorage _storage = FirebaseStorage.instance;
  final FirebaseAuth _auth = FirebaseAuth.instance;
  
  // Upload profile image
  Future<String?> uploadProfileImage(File imageFile) async {
    try {
      final uid = _auth.currentUser?.uid;
      if (uid == null) return null;
      
      final storageRef = _storage.ref().child('profile_images/$uid.jpg');
      final uploadTask = storageRef.putFile(imageFile);
      
      final snapshot = await uploadTask.whenComplete(() => null);
      final downloadUrl = await snapshot.ref.getDownloadURL();
      
      return downloadUrl;
    } catch (e) {
      print('Upload error: $e');
      return null;
    }
  }
  
  // Get profile image URL
  Future<String?> getProfileImageUrl() async {
    try {
      final uid = _auth.currentUser?.uid;
      if (uid == null) return null;
      
      final storageRef = _storage.ref().child('profile_images/$uid.jpg');
      return await storageRef.getDownloadURL();
    } catch (e) {
      print('Get image URL error: $e');
      return null;
    }
  }
}

// Main Firebase App Widget
class FirebaseApp extends StatefulWidget {
  @override
  _FirebaseAppState createState() => _FirebaseAppState();
}

class _FirebaseAppState extends State<FirebaseApp> {
  final Future<FirebaseApp> _initialization = Firebase.initializeApp();
  
  @override
  Widget build(BuildContext context) {
    return FutureBuilder(
      future: _initialization,
      builder: (context, snapshot) {
        // Check for errors
        if (snapshot.hasError) {
          return Material(
            child: Center(
              child: Text(
                'Error initializing Firebase: ${snapshot.error}',
                textDirection: TextDirection.ltr,
              ),
            ),
          );
        }
        
        // Once complete, show your application
        if (snapshot.connectionState == ConnectionState.done) {
          return AuthWrapper();
        }
        
        // Otherwise, show loading indicator
        return Material(
          child: Center(
            child: CircularProgressIndicator(),
          ),
        );
      },
    );
  }
}

// Auth Wrapper to handle auth state changes
class AuthWrapper extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final authService = AuthService();
    
    return StreamBuilder<User?>(
      stream: authService.authStateChanges,
      builder: (context, snapshot) {
        if (snapshot.connectionState == ConnectionState.active) {
          final user = snapshot.data;
          
          if (user == null) {
            return LoginScreen();
          } else {
            return HomeScreen();
          }
        }
        
        return Scaffold(
          body: Center(
            child: CircularProgressIndicator(),
          ),
        );
      },
    );
  }
}
```

#### Resources:
- [Firebase Flutter documentation](https://firebase.flutter.dev/docs/overview)
- [Firebase Authentication guide](https://firebase.flutter.dev/docs/auth/overview)
- [Cloud Firestore guide](https://firebase.flutter.dev/docs/firestore/overview)
- [Firebase Storage guide](https://firebase.flutter.dev/docs/storage/overview)

## Week 5: Advanced Flutter

### Day 36: Advanced Animations

#### Objectives:
- Master complex animations in Flutter
- Understand animation controllers and curves
- Implement custom animations

#### Key Topics:
1. Advanced Animation Controllers
   - Multiple animations
   - Animation sequences
   - Staggered animations

2. Custom Animated Widgets
   - Creating reusable animations
   - Animated Builder
   - Implicit vs explicit animations

3. Hero Animations and Shared Element Transitions
   - Basic Hero animations
   - Custom Hero animations
   - Navigation transitions

4. Physics-based Animations
   - Spring animations
   - Simulating physics
   - Fling animations

#### Sample Code - Advanced Animation:
```dart
import 'package:flutter/material.dart';
import 'package:flutter/physics.dart';

class StaggeredAnimationDemo extends StatefulWidget {
  @override
  _StaggeredAnimationDemoState createState() => _StaggeredAnimationDemoState();
}

class _StaggeredAnimationDemoState extends State<StaggeredAnimationDemo> with TickerProviderStateMixin {
  late AnimationController _controller;
  
  // Multiple animations
  late Animation<double> _sizeAnimation;
  late Animation<Color?> _colorAnimation;
  late Animation<double> _rotationAnimation;
  late Animation<Offset> _slideAnimation;
  
  @override
  void initState() {
    super.initState();
    
    _controller = AnimationController(
      duration: const Duration(milliseconds: 2000),
      vsync: this,
    );
    
    // Staggered interval timings
    final sizeCurve = CurvedAnimation(
      parent: _controller,
      curve: Interval(0.0, 0.4, curve: Curves.easeOut),
    );
    
    final colorCurve = CurvedAnimation(
      parent: _controller,
      curve: Interval(0.2, 0.6, curve: Curves.easeIn),
    );
    
    final rotationCurve = CurvedAnimation(
      parent: _controller,
      curve: Interval(0.4, 0.8, curve: Curves.easeInOut),
    );
    
    final slideCurve = CurvedAnimation(
      parent: _controller,
      curve: Interval(0.6, 1.0, curve: Curves.elasticOut),
    );
    
    // Define animations
    _sizeAnimation = Tween<double>(begin: 50, end: 200).animate(sizeCurve);
    _colorAnimation = ColorTween(begin: Colors.blue, end: Colors.purple).animate(colorCurve);
    _rotationAnimation = Tween<double>(begin: 0, end: 2 * 3.14).animate(rotationCurve);
    _slideAnimation = Tween<Offset>(begin: Offset.zero, end: Offset(0.2, 0)).animate(slideCurve);
  }
  
  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Staggered Animation')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            AnimatedBuilder(
              animation: _controller,
              builder: (context, child) {
                return SlideTransition(
                  position: _slideAnimation,
                  child: Transform.rotate(
                    angle: _rotationAnimation.value,
                    child: Container(
                      width: _sizeAnimation.value,
                      height: _sizeAnimation.value,
                      decoration: BoxDecoration(
                        color: _colorAnimation.value,
                        borderRadius: BorderRadius.circular(15),
                      ),
                      child: Icon(
                        Icons.star,
                        color: Colors.white,
                        size: _sizeAnimation.value * 0.6,
                      ),
                    ),
                  ),
                );
              },
            ),
            SizedBox(height: 40),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () {
                    if (_controller.status == AnimationStatus.completed) {
                      _controller.reverse();
                    } else {
                      _controller.forward();
                    }
                  },
                  child: Text('Animate'),
                ),
                SizedBox(width: 20),
                ElevatedButton(
                  onPressed: () {
                    _controller.stop();
                  },
                  child: Text('Stop'),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

// Physics-based animation
class DraggableCard extends StatefulWidget {
  @override
  _DraggableCardState createState() => _DraggableCardState();
}

class _DraggableCardState extends State<DraggableCard> with TickerProviderStateMixin {
  late AnimationController _controller;
  late Animation<Alignment> _animation;
  Alignment _dragAlignment = Alignment.center;
  
  @override
  void initState() {
    super.initState();
    _controller = AnimationController(vsync: this, duration: Duration(seconds: 1));
    _controller.addListener(() {
      setState(() {
        _dragAlignment = _animation.value;
      });
    });
  }
  
  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }
  
  void _runAnimation(Offset pixelsPerSecond, Size size) {
    _animation = _controller.drive(
      AlignmentTween(
        begin: _dragAlignment,
        end: Alignment.center,
      ),
    );
    
    // Calculate the velocity relative to the unit interval
    final unitsPerSecondX = pixelsPerSecond.dx / size.width;
    final unitsPerSecondY = pixelsPerSecond.dy / size.height;
    final unitsPerSecond = Offset(unitsPerSecondX, unitsPerSecondY);
    final unitVelocity = unitsPerSecond.distance;
    
    const spring = SpringDescription(
      mass: 30,
      stiffness: 1,
      damping: 1,
    );
    
    final simulation = SpringSimulation(spring, 0, 1, -unitVelocity);
    
    _controller.animateWith(simulation);
  }
  
  @override
  Widget build(BuildContext context) {
    final size = MediaQuery.of(context).size;
    
    return GestureDetector(
      onPanDown: (details) {
        _controller.stop();
      },
      onPanUpdate: (details) {
        setState(() {
          _dragAlignment += Alignment(
            details.delta.dx / (size.width / 2),
            details.delta.dy / (size.height / 2),
          );
        });
      },
      onPanEnd: (details) {
        _runAnimation(details.velocity.pixelsPerSecond, size);
      },
      child: Align(
        alignment: _dragAlignment,
        child: Card(
          elevation: 8,
          color: Colors.red,
          child: Container(
            width: 150,
            height: 150,
            child: Center(
              child: Text(
                'Drag me!',
                style: TextStyle(
                  color: Colors.white,
                  fontSize: 18,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Animation documentation](https://flutter.dev/docs/development/ui/animations)
- [Staggered Animations](https://flutter.dev/docs/development/ui/animations/staggered-animations)
- [Physics-based Animations](https://flutter.dev/docs/cookbook/animation/physics-simulation)
- [Hero Animations](https://flutter.dev/docs/development/ui/animations/hero-animations)

### Day 37: Advanced Gestures and Interactivity

#### Objectives:
- Master complex gesture detection in Flutter
- Create custom gesture recognizers
- Build highly interactive interfaces

#### Key Topics:
1. Advanced GestureDetector
   - Custom hit testing
   - Combining gestures
   - Competing gestures

2. Custom Gesture Recognizers
   - Extending GestureRecognizer
   - Creating specialized recognizers
   - Pattern recognition

3. Drag and Drop
   - Implementing drag and drop
   - Draggable and DragTarget
   - Reorderable lists

4. Interactive Visualizations
   - Touch-based charts
   - Interactive maps
   - Custom interactive widgets

#### Sample Code - Advanced Gestures:
```dart
import 'package:flutter/material.dart';
import 'package:flutter/gestures.dart';

class AdvancedGesturesDemo extends StatefulWidget {
  @override
  _AdvancedGesturesDemoState createState() => _AdvancedGesturesDemoState();
}

class _AdvancedGesturesDemoState extends State<AdvancedGesturesDemo> {
  String _gestureStatus = 'No gesture detected';
  Color _boxColor = Colors.blue;
  double _scale = 1.0;
  double _rotation = 0.0;
  double _progress = 0.0;
  
  void _updateStatus(String status) {
    setState(() {
      _gestureStatus = status;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Advanced Gestures')),
      body: Column(
        children: [
          // Status display
          Container(
            padding: EdgeInsets.all(16),
            color: Colors.grey[200],
            width: double.infinity,
            child: Text(
              'Gesture Status: $_gestureStatus',
              style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold),
            ),
          ),
          
          // Combined gesture demo
          Expanded(
            child: Center(
              child: GestureDetector(
                onTap: () {
                  _updateStatus('Tap detected');
                  setState(() {
                    _boxColor = Colors.primaries[(_boxColor.value % Colors.primaries.length + 1) % Colors.primaries.length];
                  });
                },
                onDoubleTap: () {
                  _updateStatus('Double tap detected');
                  setState(() {
                    _scale = _scale == 1.0 ? 1.5 : 1.0;
                  });
                },
                onLongPress: () {
                  _updateStatus('Long press detected');
                  setState(() {
                    _rotation += 45;
                  });
                },
                onScaleStart: (details) {
                  _updateStatus('Scale/Rotation start');
                },
                onScaleUpdate: (details) {
                  setState(() {
                    _scale = details.scale;
                    _rotation = details.rotation * 360;
                  });
                  _updateStatus('Scale: ${_scale.toStringAsFixed(2)}, Rotation: ${_rotation.toStringAsFixed(2)}°');
                },
                onScaleEnd: (details) {
                  _updateStatus('Scale/Rotation end');
                },
                child: Transform.scale(
                  scale: _scale,
                  child: Transform.rotate(
                    angle: _rotation * 3.14159 / 180,
                    child: Container(
                      width: 200,
                      height: 200,
                      decoration: BoxDecoration(
                        color: _boxColor,
                        borderRadius: BorderRadius.circular(20),
                      ),
                      child: Center(
                        child: Text(
                          'Interact with me!',
                          style: TextStyle(
                            color: Colors.white,
                            fontSize: 18,
                            fontWeight: FontWeight.bold,
                          ),
                        ),
                      ),
                    ),
                  ),
                ),
              ),
            ),
          ),
          
          // Custom slider
          Padding(
            padding: EdgeInsets.all(20),
            child: Column(
              children: [
                Text('Custom Slider: ${(_progress * 100).toStringAsFixed(0)}%'),
                SizedBox(height: 10),
                GestureDetector(
                  onHorizontalDragStart: (details) {
                    _updateStatus('Slider drag started');
                  },
                  onHorizontalDragUpdate: (details) {
                    final RenderBox renderBox = context.findRenderObject() as RenderBox;
                    final position = renderBox.globalToLocal(details.globalPosition);
                    final totalWidth = renderBox.size.width - 40;
                    final localPosition = position.dx - 20;
                    setState(() {
                      _progress = (localPosition / totalWidth).clamp(0.0, 1.0);
                    });
                    _updateStatus('Slider position: ${(_progress * 100).toStringAsFixed(0)}%');
                  },
                  onHorizontalDragEnd: (details) {
                    _updateStatus('Slider drag ended');
                  },
                  child: Container(
                    height: 20,
                    decoration: BoxDecoration(
                      color: Colors.grey[300],
                      borderRadius: BorderRadius.circular(10),
                    ),
                    child: Row(
                      children: [
                        Container(
                          width: _progress * (MediaQuery.of(context).size.width - 40),
                          decoration: BoxDecoration(
                            color: Colors.green,
                            borderRadius: BorderRadius.circular(10),
                          ),
                        ),
                      ],
                    ),
                  ),
                ),
              ],
            ),
          ),
          
          // Drag and drop demo
          Container(
            padding: EdgeInsets.all(16),
            child: Text(
              'Drag and Drop Demo',
              style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
            ),
          ),
          Container(
            height: 150,
            child: Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                // Draggable widgets
                Draggable<String>(
                  data: 'red',
                  feedback: Container(
                    width: 80,
                    height: 80,
                    color: Colors.red.withOpacity(0.5),
                    child: Center(child: Text('Red')),
                  ),
                  childWhenDragging: Container(
                    width: 80,
                    height: 80,
                    color: Colors.grey,
                  ),
                  child: Container(
                    width: 80,
                    height: 80,
                    color: Colors.red,
                    child: Center(
                      child: Text(
                        'Drag me',
                        style: TextStyle(color: Colors.white),
                      ),
                    ),
                  ),
                ),
                Draggable<String>(
                  data: 'blue',
                  feedback: Container(
                    width: 80,
                    height: 80,
                    color: Colors.blue.withOpacity(0.5),
                    child: Center(child: Text('Blue')),
                  ),
                  childWhenDragging: Container(
                    width: 80,
                    height: 80,
                    color: Colors.grey,
                  ),
                  child: Container(
                    width: 80,
                    height: 80,
                    color: Colors.blue,
                    child: Center(
                      child: Text(
                        'Drag me',
                        style: TextStyle(color: Colors.white),
                      ),
                    ),
                  ),
                ),
                
                // Drop target
                DragTarget<String>(
                  builder: (context, candidateData, rejectedData) {
                    return Container(
                      width: 120,
                      height: 120,
                      decoration: BoxDecoration(
                        border: Border.all(color: Colors.black, width: 2),
                        borderRadius: BorderRadius.circular(10),
                        color: candidateData.isEmpty ? Colors.grey[200] : Colors.grey[400],
                      ),
                      child: Center(
                        child: Text('Drop here'),
                      ),
                    );
                  },
                  onAccept: (data) {
                    _updateStatus('Dropped: $data');
                    setState(() {
                      _boxColor = data == 'red' ? Colors.red : Colors.blue;
                    });
                  },
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}
```

#### Resources:
- [Flutter Gestures documentation](https://api.flutter.dev/flutter/gestures/gestures-library.html)
- [Drag and drop in Flutter](https://flutter.dev/docs/cookbook/effects/drag-a-widget)
- [Custom GestureRecognizers](https://api.flutter.dev/flutter/gestures/GestureRecognizer-class.html)
- [Interactive viewer widget](https://api.flutter.dev/flutter/widgets/InteractiveViewer-class.html)

### Day 38: Internationalization and Localization

#### Objectives:
- Learn how to internationalize Flutter apps
- Implement localization for multiple languages
- Handle RTL layouts and cultural differences

#### Key Topics:
1. Internationalization Basics
   - Setting up Flutter localization
   - Supported locales
   - Language selection

2. Text Translation
   - Using .arb files
   - Dynamic string lookup
   - Pluralization and interpolation

3. RTL Support
   - Supporting right-to-left languages
   - Bidirectional text
   - Layout mirroring

4. Cultural Adaptation
   - Date and time formatting
   - Number and currency formatting
   - Cultural considerations

#### Sample Code - Internationalization:
```dart
import 'package:flutter/material.dart';
import 'package:flutter_localizations/flutter_localizations.dart';
import 'package:intl/intl.dart';

// Generated localization file (usually generated automatically)
import 'l10n/app_localizations.dart';

class LocalizedApp extends StatefulWidget {
  @override
  _LocalizedAppState createState() => _LocalizedAppState();
}

class _LocalizedAppState extends State<LocalizedApp> {
  Locale _locale = Locale('en');
  
  void _changeLanguage(Locale newLocale) {
    setState(() {
      _locale = newLocale;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Localized App',
      locale: _locale,
      supportedLocales: [
        Locale('en'), // English
        Locale('es'), // Spanish
        Locale('fr'), // French
        Locale('ar'), // Arabic (RTL)
      ],
      localizationsDelegates: [
        AppLocalizations.delegate,
        GlobalMaterialLocalizations.delegate,
        GlobalWidgetsLocalizations.delegate,
        GlobalCupertinoLocalizations.delegate,
      ],
      home: LocalizationDemo(changeLanguage: _changeLanguage),
    );
  }
}

class LocalizationDemo extends StatefulWidget {
  final Function(Locale) changeLanguage;
  
  LocalizationDemo({required this.changeLanguage});
  
  @override
  _LocalizationDemoState createState() => _LocalizationDemoState();
}

class _LocalizationDemoState extends State<LocalizationDemo> {
  int _counter = 0;
  DateTime _now = DateTime.now();
  
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    // Get the AppLocalizations instance
    final localizations = AppLocalizations.of(context)!;
    
    return Scaffold(
      appBar: AppBar(
        title: Text(localizations.appTitle),
        actions: [
          PopupMenuButton<String>(
            onSelected: (String languageCode) {
              widget.changeLanguage(Locale(languageCode));
            },
            itemBuilder: (BuildContext context) {
              return [
                PopupMenuItem(
                  value: 'en',
                  child: Text('English'),
                ),
                PopupMenuItem(
                  value: 'es',
                  child: Text('Español'),
                ),
                PopupMenuItem(
                  value: 'fr',
                  child: Text('Français'),
                ),
                PopupMenuItem(
                  value: 'ar',
                  child: Text('العربية'),
                ),
              ];
            },
          ),
        ],
      ),
      body: Center(
        child: Padding(
          padding: EdgeInsets.all(16),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              // Basic translated text
              Text(
                localizations.helloWorld,
                style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
              ),
              SizedBox(height: 20),
              
              // Text with parameter
              Text(
                localizations.greetings('Flutter Developer'),
                style: TextStyle(fontSize: 18),
              ),
              SizedBox(height: 20),
              
              // Text with plural
              Text(
                localizations.itemCount(_counter),
                style: TextStyle(fontSize: 18),
              ),
              SizedBox(height: 10),
              ElevatedButton(
                onPressed: _incrementCounter,
                child: Text(localizations.increment),
              ),
              SizedBox(height: 30),
              
              // Date formatting
              Text(
                localizations.todayIs(
                  DateFormat.yMMMMd(Localizations.localeOf(context).languageCode).format(_now),
                ),
                style: TextStyle(fontSize: 16),
              ),
              SizedBox(height: 10),
              Text(
                localizations.timeNow(
                  DateFormat.jm(Localizations.localeOf(context).languageCode).format(_now),
                ),
                style: TextStyle(fontSize: 16),
              ),
              SizedBox(height: 30),
              
              // Currency formatting
              Text(
                localizations.price(
                  NumberFormat.currency(
                    locale: Localizations.localeOf(context).toString(),
                    symbol: localizations.currencySymbol,
                  ).format(1234.56),
                ),
                style: TextStyle(fontSize: 16),
              ),
              SizedBox(height: 30),
              
              // RTL Examples (specifically for Arabic)
              Text(
                localizations.rtlExample,
                style: TextStyle(fontSize: 16),
                textAlign: TextAlign.start,
              ),
              SizedBox(height: 20),
              
              // Directional aware widget
              Directionality(
                textDirection: TextDirection.ltr,
                child: Row(
                  children: [
                    Icon(Icons.arrow_back),
                    SizedBox(width: 8),
                    Text('This is always LTR'),
                  ],
                ),
              ),
              SizedBox(height: 10),
              Row(
                children: [
                  Icon(Icons.arrow_back),
                  SizedBox(width: 8),
                  Text('This follows app direction'),
                ],
              ),
            ],
          ),
        ),
      ),
    );
  }
}

// Example ARB content (these would be in separate files)
// app_en.arb
/*
{
  "appTitle": "Localized App",
  "helloWorld": "Hello World!",
  "greetings": "Hello, {name}!",
  "@greetings": {
    "placeholders": {
      "name": {}
    }
  },
  "itemCount": "{count, plural, =0{No items} =1{1 item} other{{count} items}}",
  "@itemCount": {
    "placeholders": {
      "count": {}
    }
  },
  "increment": "Increment",
  "todayIs": "Today is {date}",
  "@todayIs": {
    "placeholders": {
      "date": {}
    }
  },
  "timeNow": "Current time: {time}",
  "@timeNow": {
    "placeholders": {
      "time": {}
    }
  },
  "price": "Price: {price}",
  "@price": {
    "placeholders": {
      "price": {}
    }
  },
  "currencySymbol": "$",
  "rtlExample": "This text respects the app's text direction"
}
*/

// app_ar.arb
/*
{
  "appTitle": "تطبيق مترجم",
  "helloWorld": "مرحبا بالعالم!",
  "greetings": "مرحبا، {name}!",
  "itemCount": "{count, plural, =0{لا توجد عناصر} =1{عنصر واحد} other{{count} عناصر}}",
  "increment": "زيادة",
  "todayIs": "اليوم هو {date}",
  "timeNow": "الوقت الحالي: {time}",
  "price": "السعر: {price}",
  "currencySymbol": "د.إ",
  "rtlExample": "هذا النص يحترم اتجاه النص للتطبيق"
}
*/
}
```

#### Resources:
- [Internationalization guide](https://flutter.dev/docs/development/accessibility-and-localization/internationalization)
- [flutter_localizations package](https://api.flutter.dev/flutter/flutter_localizations/flutter_localizations-library.html)
- [intl package](https://pub.dev/packages/intl)
- [Building a localized app tutorial](https://flutter.dev/docs/development/accessibility-and-localization/internationalization#an-alternative-class-for-the-apps-localized-resources)

### Day 39: Expandable Widgets and Custom UI Components

#### Objectives:
- Learn how to build collapsible/expandable UI components
- Understand custom widget creation patterns
- Implement reusable UI components with state management

#### Key Topics:
1. Expandable Widgets
   - Creating collapsible sections
   - Animation for smooth transitions
   - Managing expansion state

2. Custom UI Components
   - Widget composition patterns
   - Creating reusable widget libraries
   - Custom widget parameters

3. Advanced UI Patterns
   - Accordions and expandable lists
   - Disclosure widgets
   - Progressive disclosure UI

4. State Management for UI Components
   - Local vs. external state
   - Callbacks for state changes
   - Stateful widget lifecycle

#### Sample Code - Expandable Widget:
```dart
import 'package:flutter/material.dart';

class ExpandableCodeBlock extends StatefulWidget {
  final String title;
  final String codeContent;
  final String language;
  final bool initiallyExpanded;

  const ExpandableCodeBlock({
    Key? key,
    required this.title,
    required this.codeContent,
    this.language = 'dart',
    this.initiallyExpanded = false,
  }) : super(key: key);

  @override
  _ExpandableCodeBlockState createState() => _ExpandableCodeBlockState();
}

class _ExpandableCodeBlockState extends State<ExpandableCodeBlock> with SingleTickerProviderStateMixin {
  late AnimationController _animationController;
  late Animation<double> _heightFactor;
  bool _isExpanded = false;

  @override
  void initState() {
    super.initState();
    _isExpanded = widget.initiallyExpanded;
    _animationController = AnimationController(
      duration: const Duration(milliseconds: 300),
      vsync: this,
    );
    _heightFactor = _animationController.drive(CurveTween(curve: Curves.easeInOut));
    if (_isExpanded) {
      _animationController.value = 1.0;
    }
  }

  @override
  void dispose() {
    _animationController.dispose();
    super.dispose();
  }

  void _toggleExpand() {
    setState(() {
      _isExpanded = !_isExpanded;
      if (_isExpanded) {
        _animationController.forward();
      } else {
        _animationController.reverse();
      }
    });
  }

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: EdgeInsets.symmetric(vertical: 8),
      decoration: BoxDecoration(
        border: Border.all(color: Colors.grey.shade300),
        borderRadius: BorderRadius.circular(8),
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          // Header with expand/collapse button
          InkWell(
            onTap: _toggleExpand,
            child: Container(
              padding: EdgeInsets.symmetric(horizontal: 16, vertical: 12),
              decoration: BoxDecoration(
                color: Colors.grey.shade100,
                borderRadius: BorderRadius.only(
                  topLeft: Radius.circular(8),
                  topRight: Radius.circular(8),
                  bottomLeft: _isExpanded ? Radius.zero : Radius.circular(8),
                  bottomRight: _isExpanded ? Radius.zero : Radius.circular(8),
                ),
              ),
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Text(
                    widget.title,
                    style: TextStyle(
                      fontWeight: FontWeight.bold,
                      fontSize: 16,
                    ),
                  ),
                  AnimatedRotation(
                    turns: _isExpanded ? 0.5 : 0.0,
                    duration: Duration(milliseconds: 300),
                    child: Icon(Icons.keyboard_arrow_down),
                  ),
                ],
              ),
            ),
          ),
          
          // Expandable content
          AnimatedBuilder(
            animation: _animationController,
            builder: (context, child) {
              return ClipRect(
                child: Align(
                  heightFactor: _heightFactor.value,
                  child: child,
                ),
              );
            },
            child: Container(
              width: double.infinity,
              padding: EdgeInsets.all(16),
              decoration: BoxDecoration(
                color: Colors.grey.shade50,
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(8),
                  bottomRight: Radius.circular(8),
                ),
              ),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  // Language indicator
                  Container(
                    padding: EdgeInsets.symmetric(horizontal: 8, vertical: 2),
                    decoration: BoxDecoration(
                      color: Colors.blue.withOpacity(0.1),
                      borderRadius: BorderRadius.circular(4),
                    ),
                    child: Text(
                      widget.language,
                      style: TextStyle(
                        fontFamily: 'monospace',
                        fontSize: 12,
                        color: Colors.blue.shade700,
                      ),
                    ),
                  ),
                  SizedBox(height: 8),
                  
                  // Code content
                  Container(
                    padding: EdgeInsets.all(12),
                    decoration: BoxDecoration(
                      color: Colors.grey.shade900,
                      borderRadius: BorderRadius.circular(8),
                    ),
                    width: double.infinity,
                    child: Text(
                      widget.codeContent,
                      style: TextStyle(
                        fontFamily: 'monospace',
                        fontSize: 14,
                        color: Colors.grey.shade200,
                      ),
                    ),
                  ),
                  
                  // Copy button
                  Align(
                    alignment: Alignment.centerRight,
                    child: TextButton.icon(
                      onPressed: () {
                        // Here you would add logic to copy code to clipboard
                        // Clipboard.setData(ClipboardData(text: widget.codeContent));
                      },
                      icon: Icon(Icons.copy, size: 16),
                      label: Text('Copy'),
                      style: TextButton.styleFrom(
                        padding: EdgeInsets.symmetric(horizontal: 12, vertical: 8),
                        minimumSize: Size.zero,
                        tapTargetSize: MaterialTapTargetSize.shrinkWrap,
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ],
      ),
    );
  }
}

// Example usage of the expandable code block
class ExpandableExample extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Expandable Code Blocks')),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Expandable Code Examples',
              style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            Text(
              'Click on the headers to expand or collapse the code blocks.',
              style: TextStyle(fontSize: 16),
            ),
            SizedBox(height: 24),
            
            // First example - initially collapsed
            ExpandableCodeBlock(
              title: 'Basic Flutter App',
              codeContent: '''
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}
''',
            ),
            
            // Second example - initially expanded
            ExpandableCodeBlock(
              title: 'Stateful Widget Example',
              codeContent: '''
class Counter extends StatefulWidget {
  @override
  _CounterState createState() => _CounterState();
}

class _CounterState extends State<Counter> {
  int _count = 0;
  
  void _increment() {
    setState(() {
      _count++;
    });
  }
  
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Count: \$_count'),
        ElevatedButton(
          onPressed: _increment,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
''',
              initiallyExpanded: true,
            ),
            
            // Additional example
            ExpandableCodeBlock(
              title: 'Advanced Animation Example',
              codeContent: '''
class AnimatedLogo extends StatefulWidget {
  @override
  _AnimatedLogoState createState() => _AnimatedLogoState();
}

class _AnimatedLogoState extends State<AnimatedLogo>
    with SingleTickerProviderStateMixin {
  late AnimationController _controller;
  late Animation<double> _animation;

  @override
  void initState() {
    super.initState();
    _controller = AnimationController(
      duration: const Duration(seconds: 2),
      vsync: this,
    )..repeat(reverse: true);
    _animation = CurvedAnimation(
      parent: _controller,
      curve: Curves.elasticOut,
    );
  }

  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return AnimatedBuilder(
      animation: _animation,
      builder: (_, child) {
        return Transform.scale(
          scale: _animation.value,
          child: child,
        );
      },
      child: FlutterLogo(size: 100),
    );
  }
}
''',
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [ExpansionPanel Widget documentation](https://api.flutter.dev/flutter/material/ExpansionPanel-class.html)
- [Animations in Flutter](https://flutter.dev/docs/development/ui/animations)
- [Custom Widget best practices](https://flutter.dev/docs/development/ui/widgets-intro)
- [Reusable UI Components in Flutter](https://flutter.dev/docs/development/ui/widgets/catalog)

### Day 40: Platform Integration and Native Features

#### Objectives:
- Learn how to integrate with platform-specific features
- Access device capabilities like camera and sensors
- Build apps that leverage native functionality

#### Key Topics:
1. Platform Channels
   - Communication with native code
   - Method channels
   - Event channels

2. Device Capabilities
   - Camera access
   - Location services
   - Sensors and hardware features

3. Platform-Specific UIs
   - Adapting UI for different platforms
   - Material vs. Cupertino design
   - Platform detection

4. Native Integration Best Practices
   - Error handling
   - Permission management
   - Resource optimization

#### Sample Code - Platform Integration:
```dart
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';
import 'package:camera/camera.dart';
import 'package:geolocator/geolocator.dart';
import 'package:sensors_plus/sensors_plus.dart';
import 'dart:io' show Platform;

class PlatformFeaturesDemo extends StatefulWidget {
  @override
  _PlatformFeaturesDemoState createState() => _PlatformFeaturesDemoState();
}

class _PlatformFeaturesDemoState extends State<PlatformFeaturesDemo> {
  // Platform channel
  static const platform = MethodChannel('samples.flutter.dev/battery');
  String _batteryLevel = 'Unknown battery level';

  // Camera
  late CameraController _cameraController;
  late Future<void> _initializeCameraControllerFuture;
  bool _isCameraInitialized = false;

  // Location
  Position? _currentPosition;
  String _locationStatus = 'Unknown';

  // Accelerometer values
  AccelerometerEvent? _accelerometerValues;

  @override
  void initState() {
    super.initState();
    _getBatteryLevel();
    _initializeCamera();
    _initAccelerometer();
  }

  @override
  void dispose() {
    if (_isCameraInitialized) {
      _cameraController.dispose();
    }
    super.dispose();
  }

  // Platform channel example - getting battery level
  Future<void> _getBatteryLevel() async {
    String batteryLevel;
    try {
      final int result = await platform.invokeMethod('getBatteryLevel');
      batteryLevel = 'Battery level: $result%';
    } on PlatformException catch (e) {
      batteryLevel = "Failed to get battery level: '${e.message}'.";
    }

    setState(() {
      _batteryLevel = batteryLevel;
    });
  }

  // Camera initialization
  Future<void> _initializeCamera() async {
    try {
      final cameras = await availableCameras();
      if (cameras.isEmpty) return;

      _cameraController = CameraController(
        cameras.first,
        ResolutionPreset.medium,
      );

      _initializeCameraControllerFuture = _cameraController.initialize();
      await _initializeCameraControllerFuture;
      setState(() {
        _isCameraInitialized = true;
      });
    } catch (e) {
      print('Error initializing camera: $e');
    }
  }

  // Location service
  Future<void> _determinePosition() async {
    setState(() {
      _locationStatus = 'Determining position...';
    });

    bool serviceEnabled;
    LocationPermission permission;

    try {
      // Test if location services are enabled
      serviceEnabled = await Geolocator.isLocationServiceEnabled();
      if (!serviceEnabled) {
        setState(() {
          _locationStatus = 'Location services are disabled.';
        });
        return;
      }

      permission = await Geolocator.checkPermission();
      if (permission == LocationPermission.denied) {
        permission = await Geolocator.requestPermission();
        if (permission == LocationPermission.denied) {
          setState(() {
            _locationStatus = 'Location permissions are denied.';
          });
          return;
        }
      }
      
      if (permission == LocationPermission.deniedForever) {
        setState(() {
          _locationStatus = 'Location permissions are permanently denied.';
        });
        return;
      }

      // When we reach here, permissions are granted
      Position position = await Geolocator.getCurrentPosition();
      setState(() {
        _currentPosition = position;
        _locationStatus = 'Location obtained.';
      });
    } catch (e) {
      setState(() {
        _locationStatus = 'Error: $e';
      });
    }
  }

  // Accelerometer initialization
  void _initAccelerometer() {
    accelerometerEvents.listen((AccelerometerEvent event) {
      setState(() {
        _accelerometerValues = event;
      });
    });
  }

  // Platform adaptive widget
  Widget _getPlatformAdaptiveButton(String text, VoidCallback onPressed) {
    if (Platform.isIOS) {
      return CupertinoButton(
        onPressed: onPressed,
        child: Text(text),
      );
    } else {
      return ElevatedButton(
        onPressed: onPressed,
        child: Text(text),
      );
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Platform Features'),
      ),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            // Platform detection
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Platform Information',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 8),
                    Text('Operating System: ${Platform.operatingSystem}'),
                    Text('OS Version: ${Platform.operatingSystemVersion}'),
                    Text('Is Android: ${Platform.isAndroid}'),
                    Text('Is iOS: ${Platform.isIOS}'),
                  ],
                ),
              ),
            ),
            SizedBox(height: 16),

            // Battery level - Platform Channel
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Platform Channel',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 8),
                    Text(_batteryLevel),
                    SizedBox(height: 8),
                    _getPlatformAdaptiveButton(
                      'Get Battery Level',
                      _getBatteryLevel,
                    ),
                  ],
                ),
              ),
            ),
            SizedBox(height: 16),

            // Camera preview
            if (_isCameraInitialized)
              Card(
                child: Padding(
                  padding: EdgeInsets.all(16),
                  child: Column(
                    crossAxisAlignment: CrossAxisAlignment.start,
                    children: [
                      Text(
                        'Camera',
                        style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                      ),
                      SizedBox(height: 8),
                      Container(
                        height: 200,
                        width: double.infinity,
                        child: CameraPreview(_cameraController),
                      ),
                    ],
                  ),
                ),
              ),
            SizedBox(height: 16),

            // Location
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Location',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 8),
                    Text('Status: $_locationStatus'),
                    if (_currentPosition != null)
                      Column(
                        crossAxisAlignment: CrossAxisAlignment.start,
                        children: [
                          Text('Latitude: ${_currentPosition!.latitude}'),
                          Text('Longitude: ${_currentPosition!.longitude}'),
                          Text('Altitude: ${_currentPosition!.altitude}'),
                          Text('Accuracy: ${_currentPosition!.accuracy} meters'),
                        ],
                      ),
                    SizedBox(height: 8),
                    _getPlatformAdaptiveButton(
                      'Get Current Location',
                      _determinePosition,
                    ),
                  ],
                ),
              ),
            ),
            SizedBox(height: 16),

            // Accelerometer
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Accelerometer',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 8),
                    if (_accelerometerValues != null)
                      Column(
                        crossAxisAlignment: CrossAxisAlignment.start,
                        children: [
                          Text('X: ${_accelerometerValues!.x.toStringAsFixed(2)}'),
                          Text('Y: ${_accelerometerValues!.y.toStringAsFixed(2)}'),
                          Text('Z: ${_accelerometerValues!.z.toStringAsFixed(2)}'),
                        ],
                      )
                    else
                      Text('No accelerometer data available'),
                  ],
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Platform Channels guide](https://flutter.dev/docs/development/platform-integration/platform-channels)
- [Camera plugin](https://pub.dev/packages/camera)
- [Geolocator plugin](https://pub.dev/packages/geolocator)
- [Sensors Plus plugin](https://pub.dev/packages/sensors_plus)

### Day 41: Background Processing and Isolates

#### Objectives:
- Understand Dart isolates and background execution
- Implement long-running tasks without blocking the UI
- Learn best practices for background processing

#### Key Topics:
1. Dart Isolates
   - Understanding isolate concept
   - Creating and managing isolates
   - Communication between isolates

2. Background Processing
   - Long-running operations
   - Background fetch and processing
   - Platform-specific background execution

3. Compute Function
   - Simplified isolate creation
   - Use cases for compute
   - Performance considerations

4. Multithreading Best Practices
   - Avoiding UI freezes
   - State management with isolates
   - Error handling

#### Sample Code - Isolates and Background Processing:
```dart
import 'package:flutter/material.dart';
import 'package:flutter/foundation.dart';
import 'dart:isolate';
import 'dart:math';
import 'dart:async';

class IsolatesDemo extends StatefulWidget {
  @override
  _IsolatesDemoState createState() => _IsolatesDemoState();
}

class _IsolatesDemoState extends State<IsolatesDemo> {
  // State for UI
  bool _isCalculating = false;
  String _calculationResult = 'No calculation performed';
  double _progress = 0.0;
  
  // Compute function example
  Future<void> _runHeavyComputation() async {
    setState(() {
      _isCalculating = true;
      _calculationResult = 'Calculating...';
    });
    
    try {
      // Using compute function for a heavy calculation
      final result = await compute(
        _findPrimesInRange,
        [1, 500000], // Range to find primes
      );
      
      setState(() {
        _calculationResult = 'Found ${result.length} prime numbers';
        _isCalculating = false;
      });
    } catch (e) {
      setState(() {
        _calculationResult = 'Error: $e';
        _isCalculating = false;
      });
    }
  }
  
  // Manual isolate management with progress updates
  Future<void> _runWithProgress() async {
    setState(() {
      _isCalculating = true;
      _calculationResult = 'Calculating with progress...';
      _progress = 0.0;
    });
    
    // Create a ReceivePort for receiving messages from the isolate
    final receivePort = ReceivePort();
    late Isolate isolate;
    
    try {
      // Spawn the isolate
      isolate = await Isolate.spawn(
        _calculateWithProgress,
        receivePort.sendPort,
      );
      
      // Listen for messages from the isolate
      await for (final message in receivePort) {
        if (message is double) {
          // Progress update
          setState(() {
            _progress = message;
          });
        } else if (message is int) {
          // Final result
          setState(() {
            _calculationResult = 'Found $message prime numbers';
            _isCalculating = false;
          });
          break;
        } else if (message is String) {
          // Error message
          setState(() {
            _calculationResult = message;
            _isCalculating = false;
          });
          break;
        }
      }
    } catch (e) {
      setState(() {
        _calculationResult = 'Error: $e';
        _isCalculating = false;
      });
    } finally {
      // Close the receive port and kill the isolate
      receivePort.close();
      isolate.kill();
    }
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Background Processing'),
      ),
      body: SingleChildScrollView(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Heavy Computation Demo',
              style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 20),
            
            // Example 1: Compute function
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Using compute()',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 10),
                    Text(
                      'This example uses Flutter\'s compute() function to run a '
                      'prime number calculation in a separate isolate, without '
                      'blocking the UI thread.',
                    ),
                    SizedBox(height: 16),
                    Text(_calculationResult),
                    SizedBox(height: 16),
                    ElevatedButton(
                      onPressed: _isCalculating ? null : _runHeavyComputation,
                      child: Text('Find Prime Numbers'),
                    ),
                  ],
                ),
              ),
            ),
            SizedBox(height: 20),
            
            // Example 2: Manual isolate with progress
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Manual Isolate with Progress',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 10),
                    Text(
                      'This example manually manages an isolate and shows how to '
                      'communicate between the main isolate and the background '
                      'isolate, with progress updates.',
                    ),
                    SizedBox(height: 16),
                    if (_isCalculating && _progress > 0)
                      Column(
                        children: [
                          LinearProgressIndicator(
                            value: _progress,
                          ),
                          SizedBox(height: 8),
                          Text('${(_progress * 100).toStringAsFixed(1)}%'),
                        ],
                      ),
                    SizedBox(height: 8),
                    Text(_calculationResult),
                    SizedBox(height: 16),
                    ElevatedButton(
                      onPressed: _isCalculating ? null : _runWithProgress,
                      child: Text('Calculate With Progress'),
                    ),
                  ],
                ),
              ),
            ),
            SizedBox(height: 20),
            
            // Example 3: Background Task Demo
            Card(
              child: Padding(
                padding: EdgeInsets.all(16),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Real-world Background Task',
                      style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: 10),
                    Text(
                      'This example demonstrates a more realistic use case: '
                      'processing images or data in the background while keeping '
                      'the UI responsive.',
                    ),
                    SizedBox(height: 16),
                    ElevatedButton(
                      onPressed: () {
                        // Show a dialog explaining platform limitations
                        showDialog(
                          context: context,
                          builder: (context) => AlertDialog(
                            title: Text('Platform-specific implementation'),
                            content: Text(
                              'Actual background processing implementation would '
                              'depend on the platform (iOS, Android) and would '
                              'use WorkManager, AlarmManager, or background fetch '
                              'capabilities that require platform-specific code.\n\n'
                              'For this example, we\'re just showing the concept.'
                            ),
                            actions: [
                              TextButton(
                                onPressed: () => Navigator.of(context).pop(),
                                child: Text('OK'),
                              ),
                            ],
                          ),
                        );
                      },
                      child: Text('Process Data in Background'),
                    ),
                  ],
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter for web](https://flutter.dev/web)
- [Flutter desktop support](https://flutter.dev/desktop)
- [Responsive design in Flutter](https://flutter.dev/docs/development/ui/layout/responsive)
- [Platform-specific considerations](https://flutter.dev/docs/development/ui/layout/building-adaptive-apps)

## Week 6: Performance & Deployment

### Day 43: Performance Optimization Techniques

#### Objectives:
- Identify and fix common performance issues in Flutter apps
- Learn how to measure and profile app performance
- Implement performance optimization techniques

#### Key Topics:
1. Performance Measurement
   - Flutter DevTools profiler
   - Frame timeline analysis
   - Performance metrics

2. UI Rendering Optimization
   - Widget rebuilds optimization
   - Render object optimization
   - BuildContext considerations

3. Memory Management
   - Image caching strategies
   - Memory leaks prevention
   - Resource cleanup

4. Computation Optimization
   - Expensive operations handling
   - Lazy loading and pagination
   - Caching strategies

#### Sample Code - Performance Optimization:
```dart
import 'package:flutter/material.dart';
import 'package:cached_network_image/cached_network_image.dart';

class PerformanceOptimizationDemo extends StatefulWidget {
  @override
  _PerformanceOptimizationDemoState createState() => _PerformanceOptimizationDemoState();
}

class _PerformanceOptimizationDemoState extends State<PerformanceOptimizationDemo> {
  // Toggle flags for different examples
  bool _useConstWidget = true;
  bool _useRepaintBoundary = true;
  bool _useCachedImages = true;
  bool _usePagination = true;
  
  // List of items for the pagination example
  final List<String> _allItems = List.generate(
    1000,
    (index) => 'Item ${index + 1}',
  );
  
  // Initially loaded items for pagination
  late List<String> _displayedItems;
  
  // Controller for list scrolling
  final ScrollController _scrollController = ScrollController();
  
  // Page size for pagination
  final int _pageSize = 20;
  
  @override
  void initState() {
    super.initState();
    
    // Initially load only the first page
    _displayedItems = _allItems.take(_pageSize).toList();
    
    // Add scroll listener for pagination
    _scrollController.addListener(_onScroll);
  }
  
  @override
  void dispose() {
    _scrollController.removeListener(_onScroll);
    _scrollController.dispose();
    super.dispose();
  }
  
  // Load more items when scrolling to the bottom
  void _onScroll() {
    if (_usePagination &&
        _scrollController.position.pixels >= _scrollController.position.maxScrollExtent * 0.8 &&
        _displayedItems.length < _allItems.length) {
      setState(() {
        final int nextPageSize = _pageSize;
        final int startIndex = _displayedItems.length;
        final int endIndex = startIndex + nextPageSize < _allItems.length ? 
                            startIndex + nextPageSize : _allItems.length;
        
        _displayedItems.addAll(_allItems.sublist(startIndex, endIndex));
      });
    }
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Performance Optimization'),
      ),
      body: Column(
        children: [
          // Settings panel
          _buildSettingsPanel(),
          
          // Examples
          Expanded(
            child: ListView(
              controller: _scrollController,
              children: [
                // Example 1: Const widgets
                _buildSectionHeader('1. Const Widgets'),
                _buildConstWidgetsExample(),
                
                // Example 2: RepaintBoundary
                _buildSectionHeader('2. RepaintBoundary'),
                _buildRepaintBoundaryExample(),
                
                // Example 3: Image caching
                _buildSectionHeader('3. Image Caching'),
                _buildImageCachingExample(),
                
                // Example 4: Pagination
                _buildSectionHeader('4. List Pagination'),
                _buildPaginationExample(),
              ],
            ),
          ),
        ],
      ),
    );
  }
  
  // Settings panel with toggle options
  Widget _buildSettingsPanel() {
    return Container(
      padding: EdgeInsets.all(16),
      color: Colors.grey[200],
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(
            'Performance Optimization Settings',
            style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
          ),
          SizedBox(height: 8),
          
          // Toggle for const widgets
          SwitchListTile(
            title: Text('Use Const Widgets'),
            subtitle: Text('Reduces widget rebuilds'),
            value: _useConstWidget,
            onChanged: (value) {
              setState(() {
                _useConstWidget = value;
              });
            },
          ),
          
          // Toggle for RepaintBoundary
          SwitchListTile(
            title: Text('Use RepaintBoundary'),
            subtitle: Text('Reduces unnecessary repainting'),
            value: _useRepaintBoundary,
            onChanged: (value) {
              setState(() {
                _useRepaintBoundary = value;
              });
            },
          ),
          
          // Toggle for image caching
          SwitchListTile(
            title: Text('Use Cached Images'),
            subtitle: Text('Optimizes network image loading'),
            value: _useCachedImages,
            onChanged: (value) {
              setState(() {
                _useCachedImages = value;
              });
            },
          ),
          
          // Toggle for pagination
          SwitchListTile(
            title: Text('Use Pagination'),
            subtitle: Text('Loads list items on demand'),
            value: _usePagination,
            onChanged: (value) {
              setState(() {
                _usePagination = value;
                
                // Reset displayed items when toggling pagination
                if (value) {
                  _displayedItems = _allItems.take(_pageSize).toList();
                } else {
                  _displayedItems = List.from(_allItems);
                }
              });
            },
          ),
        ],
      ),
    );
  }
  
  // Section header widget
  Widget _buildSectionHeader(String title) {
    return Padding(
      padding: EdgeInsets.fromLTRB(16, 24, 16, 8),
      child: Text(
        title,
        style: TextStyle(
          fontSize: 20,
          fontWeight: FontWeight.bold,
          color: Colors.blue[800],
        ),
      ),
    );
  }
  
  // Example 1: Const widgets
  Widget _buildConstWidgetsExample() {
    return Card(
      margin: EdgeInsets.symmetric(horizontal: 16, vertical: 8),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Using const constructors reduces rebuilds',
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            
            // With const vs without const
            Row(
              children: [
                Expanded(
                  child: Column(
                    children: [
                      Text('With const:'),
                      SizedBox(height: 8),
                      
                      // Example with const
                      _useConstWidget
                          ? const ExampleWidget(color: Colors.green, label: 'Optimized')
                          : ExampleWidget(color: Colors.green, label: 'Optimized'),
                    ],
                  ),
                ),
                Expanded(
                  child: Column(
                    children: [
                      Text('Without const:'),
                      SizedBox(height: 8),
                      
                      // Example without const
                      ExampleWidget(color: Colors.red, label: 'Unoptimized'),
                    ],
                  ),
                ),
              ],
            ),
            
            SizedBox(height: 16),
            Text(
              'When a parent widget rebuilds, const widgets avoid '
              'unnecessary recreation and rebuilding, improving performance.',
            ),
          ],
        ),
      ),
    );
  }
  
  // Example 2: RepaintBoundary
  Widget _buildRepaintBoundaryExample() {
    final currentTime = DateTime.now().second.toString();
    
    return Card(
      margin: EdgeInsets.symmetric(horizontal: 16, vertical: 8),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'RepaintBoundary prevents unnecessary repainting',
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            
            Row(
              children: [
                Expanded(
                  child: Column(
                    children: [
                      Text('With RepaintBoundary:'),
                      SizedBox(height: 8),
                      
                      // Clock that forces updates, but animation is isolated
                      Container(
                        padding: EdgeInsets.all(8),
                        color: Colors.grey[200],
                        child: Column(
                          children: [
                            Text('Current second: $currentTime'),
                            SizedBox(height: 8),
                            
                            // RepaintBoundary wraps the animation
                            _useRepaintBoundary
                                ? RepaintBoundary(
                                    child: AnimatedContainer(
                                      duration: Duration(seconds: 1),
                                      height: 100,
                                      width: 100,
                                      color: Colors.blue,
                                      child: Center(
                                        child: Text(
                                          'Isolated',
                                          style: TextStyle(color: Colors.white),
                                        ),
                                      ),
                                    ),
                                  )
                                : AnimatedContainer(
                                    duration: Duration(seconds: 1),
                                    height: 100,
                                    width: 100,
                                    color: Colors.blue,
                                    child: Center(
                                      child: Text(
                                        'Isolated',
                                        style: TextStyle(color: Colors.white),
                                      ),
                                    ),
                                  ),
                          ],
                        ),
                      ),
                    ],
                  ),
                ),
                Expanded(
                  child: Column(
                    children: [
                      Text('Without RepaintBoundary:'),
                      SizedBox(height: 8),
                      
                      // Clock that forces updates with direct animation
                      Container(
                        padding: EdgeInsets.all(8),
                        color: Colors.grey[200],
                        child: Column(
                          children: [
                            Text('Current second: $currentTime'),
                            SizedBox(height: 8),
                            
                            // No RepaintBoundary
                            AnimatedContainer(
                              duration: Duration(seconds: 1),
                              height: 100,
                              width: 100,
                              color: Colors.red,
                              child: Center(
                                child: Text(
                                  'Not Isolated',
                                  style: TextStyle(color: Colors.white),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ],
                  ),
                ),
              ],
            ),
            
            SizedBox(height: 16),
            Text(
              'RepaintBoundary creates a new layer for its child widget, '
              'preventing it from being repainted when its parent changes. '
              'This is useful for complex UI elements that rarely change.',
            ),
          ],
        ),
      ),
    );
  }
  
  // Example 3: Image caching
  Widget _buildImageCachingExample() {
    final List<String> imageUrls = [
      'https://picsum.photos/200/300?random=1',
      'https://picsum.photos/200/300?random=2',
      'https://picsum.photos/200/300?random=3',
      'https://picsum.photos/200/300?random=4',
    ];
    
    return Card(
      margin: EdgeInsets.symmetric(horizontal: 16, vertical: 8),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'Image Caching reduces network requests',
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 16),
            
            Row(
              children: [
                Expanded(
                  child: Column(
                    children: [
                      Text('Cached Images:'),
                      SizedBox(height: 8),
                      
                      Container(
                        height: 150,
                        child: ListView.builder(
                          scrollDirection: Axis.horizontal,
                          itemCount: imageUrls.length,
                          itemBuilder: (context, index) {
                            return Padding(
                              padding: EdgeInsets.only(right: 8),
                              child: _useCachedImages
                                  ? CachedNetworkImage(
                                      imageUrl: imageUrls[index],
                                      width: 100,
                                      height: 150,
                                      fit: BoxFit.cover,
                                      placeholder: (context, url) => Container(
                                        color: Colors.grey[300],
                                        child: Center(
                                          child: CircularProgressIndicator(),
                                        ),
                                      ),
                                      errorWidget: (context, url, error) => Container(
                                        color: Colors.grey[300],
                                        child: Icon(Icons.error),
                                      ),
                                    )
                                  : Image.network(
                                      imageUrls[index],
                                      width: 100,
                                      height: 150,
                                      fit: BoxFit.cover,
                                      loadingBuilder: (context, child, loadingProgress) {
                                        if (loadingProgress == null) return child;
                                        return Container(
                                          color: Colors.grey[300],
                                          width: 100,
                                          height: 150,
                                          child: Center(
                                            child: CircularProgressIndicator(
                                              value: loadingProgress.expectedTotalBytes != null
                                                  ? loadingProgress.cumulativeBytesLoaded /
                                                      loadingProgress.expectedTotalBytes!
                                                  : null,
                                            ),
                                          ),
                                        );
                                      },
                                    ),
                            );
                          },
                        ),
                      ),
                    ],
                  ),
                ),
              ],
            ),
            
            SizedBox(height: 16),
            Text(
              'CachedNetworkImage stores images in the cache after loading them, '
              'preventing repeated downloads when navigating back to the same image. '
              'This reduces network usage and improves loading times.',
            ),
            
            // Button to clear cache for demonstration
            Align(
              alignment: Alignment.centerRight,
              child: ElevatedButton(
                onPressed: () {
                  setState(() {
                    // This will trigger a UI rebuild, showing the cache effect
                  });
                },
                child: Text('Reload Images'),
              ),
            ),
          ],
        ),
      ),
    );
  }
  
  // Example 4: Pagination
  Widget _buildPaginationExample() {
    return Card(
      margin: EdgeInsets.symmetric(horizontal: 16, vertical: 8),
      child: Padding(
        padding: EdgeInsets.all(16),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(
              'List Pagination for performance',
              style: TextStyle(fontWeight: FontWeight.bold),
            ),
            SizedBox(height: 8),
            Text(
              _usePagination
                  ? 'Showing ${_displayedItems.length} of ${_allItems.length} items. Scroll to load more.'
                  : 'Showing all ${_allItems.length} items at once.',
            ),
            SizedBox(height: 16),
            
            // List with items
            Container(
              height: 300,
              child: ListView.builder(
                // Don't use the main scroll controller
                // to avoid interference with the main scroll
                itemCount: _displayedItems.length + (_usePagination && _displayedItems.length < _allItems.length ? 1 : 0),
                itemBuilder: (context, index) {
                  // Show loading indicator at the end when more items can be loaded
                  if (_usePagination && index == _displayedItems.length) {
                    return Center(
                      child: Padding(
                        padding: EdgeInsets.all(16),
                        child: CircularProgressIndicator(),
                      ),
                    );
                  }
                  
                  return ListTile(
                    leading: CircleAvatar(
                      child: Text((index + 1).toString()),
                    ),
                    title: Text(_displayedItems[index]),
                    subtitle: Text('This is item #${index + 1}'),
                  );
                },
              ),
            ),
            
            SizedBox(height: 16),
            Text(
              'Pagination loads items only when needed, reducing memory usage '
              'and improving initial loading performance. This is especially '
              'important for large lists or complex items.',
            ),
          ],
        ),
      ),
    );
  }
}

// Example widget for const demonstration
class ExampleWidget extends StatelessWidget {
  final Color color;
  final String label;
  
  // Constructor with optional const
  const ExampleWidget({
    Key? key,
    required this.color,
    required this.label,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    print('Building ExampleWidget with label: $label'); // For demonstration
    
    return Container(
      width: 150,
      height: 100,
      color: color,
      child: Center(
        child: Text(
          label,
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.bold,
          ),
        ),
      ),
    );
  }
}
```

#### Resources:
- [Flutter performance best practices](https://flutter.dev/docs/perf/rendering/best-practices)
- [Flutter DevTools](https://flutter.dev/docs/development/tools/devtools/overview)
- [Measuring app startup time](https://flutter.dev/docs/perf/metrics)
- [Rendering pipeline](https://flutter.dev/docs/development/ui/widgets-intro#layering)

### Day 44: Memory Management and Profiling

#### Objectives:
- Understand memory management in Flutter
- Identify and fix memory leaks
- Learn how to profile and optimize memory usage

#### Key Topics:
1. Memory Management Basics
   - Garbage collection in Dart
   - Memory allocation and deallocation
   - Reference counting vs garbage collection

2. Common Memory Issues
   - Memory leaks identification
   - Resource intensive operations
   - Image and asset caching

3. Performance Profiling
   - Flutter DevTools memory profiler
   - Timeline events and snapshots
   - Performance overlay

4. Optimization Techniques
   - Widget disposal best practices
   - Stream and listener cleanup
   - Caching strategies

#### Sample Code - Memory Management:
```dart
import 'package:flutter/material.dart';
import 'dart:async';

class MemoryManagementDemo extends StatefulWidget {
  @override
  _MemoryManagementDemoState createState() => _MemoryManagementDemoState();
}

class _MemoryManagementDemoState extends State<MemoryManagementDemo> {
  // Example of potential memory leak
  List<String> _largeStringList = [];
  StreamController<int>? _counterStreamController;
  StreamSubscription<int>? _counterSubscription;
  Timer? _timer;
  
  @override
  void initState() {
    super.initState();
    // Create a stream controller
    _counterStreamController = StreamController<int>.broadcast();
  }
  
  @override
  void dispose() {
    // Proper cleanup is essential to prevent memory leaks
    _cancelTimer();
    _cancelSubscription();
    _counterStreamController?.close();
    _largeStringList.clear();
    super.dispose();
  }
  
  // Method to simulate memory leak by creating large strings
  void _createMemoryLeak() {
    setState(() {
      // Create 1,000 strings, each 10,000 characters long
      for (int i = 0; i < 1000; i++) {
        _largeStringList.add(String.fromCharCodes(List.filled(10000, 65 + (i % 26))));
      }
    });
  }
  
  // Method to clear memory
  void _clearMemory() {
    setState(() {
      _largeStringList.clear();
    });
  }
  
  // Method to start a timer that updates a stream without cleaning up (potential memory leak)
  void _startLeakyTimer() {
    _timer = Timer.periodic(Duration(milliseconds: 100), (timer) {
      _counterStreamController?.add(timer.tick);
    });
    
    // Create a subscription that we never cancel (memory leak)
    _counterStreamController?.stream.listen((count) {
      // This listener is never canceled
      print('Counter updated: $count');
    });
  }
  
  // Method to properly cleanup resources
  void _cancelTimer() {
    _timer?.cancel();
    _timer = null;
  }
  
  void _cancelSubscription() {
    _counterSubscription?.cancel();
    _counterSubscription = null;
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Memory Management')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Memory Usage Demo'),
            SizedBox(height: 20),
            Text('String list size: ${_largeStringList.length} items'),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _createMemoryLeak,
              child: Text('Create Memory Leak'),
            ),
            ElevatedButton(
              onPressed: _clearMemory,
              child: Text('Clear Memory'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: _startLeakyTimer,
              child: Text('Start Leaky Timer'),
            ),
            ElevatedButton(
              onPressed: _cancelTimer,
              child: Text('Stop Timer'),
            ),
          ],
        ),
      ),
    );
  }
}
```

#### Best Practices for Memory Management:
1. Always dispose controllers, subscriptions, animations in `dispose()`
2. Be cautious with large collections and clear them when done
3. Use lazy loading and pagination for large datasets
4. Optimize images by resizing them before loading
5. Profile your app regularly with DevTools memory profiler

#### Resources:
- [Dart memory management](https://dart.dev/guides/language/sound-null-safety)
- [Flutter DevTools memory tab](https://flutter.dev/docs/development/tools/devtools/memory)
- [Performance best practices](https://flutter.dev/docs/perf/rendering/best-practices)
- [Understanding Flutter performance](https://flutter.dev/docs/perf)

### Day 45: Flutter DevTools and Profiling

#### Objectives:
- Master Flutter DevTools for performance analysis
- Learn how to profile different aspects of Flutter apps
- Identify and fix performance bottlenecks

#### Key Topics:
1. DevTools Introduction
   - Setting up DevTools
   - Available tools and panels
   - Integration with IDE

2. Performance Profiling
   - CPU profiling
   - Timeline events
   - Frame analysis

3. Widget Inspector
   - Exploring widget tree
   - Debugging layout issues
   - Performance overlay

4. Advanced Profiling Techniques
   - Identifying jank
   - Tracking expensive builds
   - Optimizing rendering

#### Sample Code - DevTools Integration:
```dart
import 'dart:developer' as developer;
import 'package:flutter/material.dart';

class DevToolsDemoPage extends StatefulWidget {
  @override
  _DevToolsDemoPageState createState() => _DevToolsDemoPageState();
}

class _DevToolsDemoPageState extends State<DevToolsDemoPage> {
  int _counter = 0;
  bool _showPerformanceOverlay = false;
  bool _buildExpensiveList = false;
  late List<Widget> _manyWidgets;
  
  @override
  void initState() {
    super.initState();
    _manyWidgets = [];
    
    // Add a user timing for DevTools timeline
    developer.Timeline.startSync('DevToolsPage initialization');
    _doExpensiveCalculation();
    developer.Timeline.finishSync();
  }
  
  void _doExpensiveCalculation() {
    // This is intentionally inefficient for demonstration
    for (int i = 0; i < 500; i++) {
      String result = '';
      for (int j = 0; j < 100; j++) {
        result += '$j,';
      }
    }
  }
  
  void _incrementCounter() {
    // Create a timeline event for this method
    developer.Timeline.timeSync('incrementCounter', () {
      setState(() {
        _counter++;
      });
      
      // Log to DevTools console
      developer.log('Counter incremented to $_counter');
    });
  }
  
  void _toggleExpensiveList() {
    setState(() {
      _buildExpensiveList = !_buildExpensiveList;
      
      if (_buildExpensiveList) {
        // Create many widgets to demonstrate performance impact
        _manyWidgets = List.generate(500, (index) {
          return Container(
            height: 20,
            margin: EdgeInsets.symmetric(vertical: 2),
            color: Colors.primaries[index % Colors.primaries.length],
            child: Text('Item $index'),
          );
        });
      } else {
        _manyWidgets = [];
      }
    });
  }
  
  @override
  Widget build(BuildContext context) {
    // Wrap the entire build method in a timeline event
    return developer.Timeline.timeSync('DevToolsPage.build', () {
      return Scaffold(
        appBar: AppBar(
          title: Text('DevTools Demo'),
          actions: [
            // Toggle for performance overlay
            IconButton(
              icon: Icon(_showPerformanceOverlay ? 
                  Icons.visibility_off : Icons.visibility),
              onPressed: () {
                setState(() {
                  _showPerformanceOverlay = !_showPerformanceOverlay;
                });
              },
              tooltip: 'Toggle Performance Overlay',
            ),
          ],
        ),
        body: Column(
          children: [
            // Performance overlay UI
            if (_showPerformanceOverlay)
              Container(
                color: Colors.black,
                padding: EdgeInsets.all(8),
                width: double.infinity,
                child: Text(
                  'Performance Overlay Enabled',
                  style: TextStyle(color: Colors.white),
                  textAlign: TextAlign.center,
                ),
              ),
            
            // Counter section for timeline events
            Padding(
              padding: EdgeInsets.all(16),
              child: Column(
                children: [
                  Text('Counter: $_counter', 
                      style: TextStyle(fontSize: 24)),
                  ElevatedButton(
                    onPressed: _incrementCounter,
                    child: Text('Increment'),
                  ),
                ],
              ),
            ),
            
            // Toggle for expensive operation
            Padding(
              padding: EdgeInsets.all(16),
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceBetween,
                children: [
                  Text('Show Expensive List:'),
                  Switch(
                    value: _buildExpensiveList,
                    onChanged: (value) => _toggleExpensiveList(),
                  ),
                ],
              ),
            ),
            
            // Expensive list that will show in the widget inspector
            Expanded(
              child: _buildExpensiveList
                ? ListView.builder(
                    itemCount: _manyWidgets.length,
                    itemBuilder: (context, index) => _manyWidgets[index],
                  )
                : Center(child: Text('Enable list to test performance')),
            ),
          ],
        ),
      );
    });
  }
}
```

#### DevTools Features to Master:
1. **Inspector**: Explore the widget tree and properties
2. **Performance**: Analyze UI performance and frame rendering
3. **CPU Profiler**: Find expensive methods and operations
4. **Memory**: Track memory usage and find leaks
5. **Network**: Monitor network requests and responses
6. **Logging**: View logs and timeline events

#### Resources:
- [Flutter DevTools overview](https://flutter.dev/docs/development/tools/devtools/overview)
- [Performance profiling with DevTools](https://flutter.dev/docs/perf/rendering/ui-performance)
- [Timeline events guide](https://api.flutter.dev/flutter/dart-developer/Timeline-class.html)
- [Widget inspector documentation](https://flutter.dev/docs/development/tools/devtools/inspector)

### Day 46: App Deployment - Android

#### Objectives:
- Learn how to prepare Flutter apps for Android deployment
- Understand signing and app bundling
- Create release builds for the Google Play Store

#### Key Topics:
1. App Preparation
   - App icons and splash screens
   - App manifest configuration
   - Version information

2. Release Build Configuration
   - Signing configuration
   - ProGuard and code shrinking
   - Build variants

3. App Bundle Creation
   - Creating app bundles
   - Size optimization
   - Testing app bundles

4. Google Play Store Publishing
   - Store listing requirements
   - Play Console configuration
   - Release tracks and testing

#### Android Deployment Checklist:

##### Step 1: Configure app icon and splash screen
- Update icons in `android/app/src/main/res/` directories
- Configure `AndroidManifest.xml` with proper app info

##### Step 2: Set app version in pubspec.yaml
```yaml
# pubspec.yaml
name: my_flutter_app
description: My amazing Flutter application
version: 1.0.0+1  # Version format is: version+build_number
```

##### Step 3: Set up signing
1. Create a keystore file:
```shell
keytool -genkey -v -keystore ~/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
```

2. Create `android/key.properties` file (don't commit to version control):
```properties
storePassword=<password>
keyPassword=<password>
keyAlias=key
storeFile=<path to key.jks>
```

3. Configure Gradle for signing in `android/app/build.gradle`:
```gradle
def keystoreProperties = new Properties()
def keystorePropertiesFile = rootProject.file('key.properties')
if (keystorePropertiesFile.exists()) {
    keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
}

android {
    // ...
    defaultConfig { /* ... */ }

    signingConfigs {
        release {
            keyAlias keystoreProperties['keyAlias']
            keyPassword keystoreProperties['keyPassword']
            storeFile keystoreProperties['storeFile'] ? file(keystoreProperties['storeFile']) : null
            storePassword keystoreProperties['storePassword']
        }
    }
    
    buildTypes {
        release {
            signingConfig signingConfigs.release
            // Enable code shrinking if needed
            minifyEnabled true
            shrinkResources true
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}
```

##### Step 4: Build release APK or App Bundle
```shell
# For APK:
flutter build apk --release

# For App Bundle (recommended for Play Store):
flutter build appbundle --release
```

##### Step 5: Test release build
```shell
# Install APK directly:
flutter install

# Or test App Bundle with bundletool
```

##### Step 6: Prepare for Play Store submission
1. Create a privacy policy
2. Prepare store listing assets:
   - Screenshots in multiple sizes
   - Feature graphic (1024×500 px)
   - App icon (512×512 px)
   - App descriptions and keywords

##### Step 7: Submit to Google Play Console
1. Create developer account
2. Create new application
3. Complete store listing details
4. Upload App Bundle
5. Set content rating and pricing
6. Submit for review

#### Resources:
- [Preparing an Android app for release](https://flutter.dev/docs/deployment/android)
- [Android signing configuration](https://developer.android.com/studio/publish/app-signing)
- [App Bundle documentation](https://developer.android.com/guide/app-bundle)
- [Google Play Console documentation](https://support.google.com/googleplay/android-developer/answer/6112435)

### Day 47: App Deployment - iOS

#### Objectives:
- Learn how to prepare Flutter apps for iOS deployment
- Understand code signing and provisioning profiles
- Create release builds for the App Store

#### Key Topics:
1. iOS Project Configuration
   - App icons and launch screens
   - Info.plist configuration
   - Version and build numbers

2. Code Signing Setup
   - Apple Developer account setup
   - Certificates and provisioning profiles
   - Xcode signing configuration

3. Release Build Creation
   - Building for release
   - Archiving and validating
   - TestFlight preparation

4. App Store Publishing
   - App Store Connect setup
   - App submission requirements
   - Review process and guidelines

#### iOS Deployment Checklist:

##### Step 1: Configure app icon and launch screen
- Update icons in `ios/Runner/Assets.xcassets/AppIcon.appiconset`
- Configure launch screen in `ios/Runner/Base.lproj/LaunchScreen.storyboard`

##### Step 2: Set app version in pubspec.yaml
```yaml
# pubspec.yaml
name: my_flutter_app
description: My amazing Flutter application
version: 1.0.0+1  # Version format is: version+build_number
```

##### Step 3: Configure Info.plist
```xml
<!-- ios/Runner/Info.plist -->
<key>CFBundleDisplayName</key>
<string>My Flutter App</string>
<key>CFBundleShortVersionString</key>
<string>$(FLUTTER_BUILD_NAME)</string>
<key>CFBundleVersion</key>
<string>$(FLUTTER_BUILD_NUMBER)</string>
```

##### Step 4: Set up code signing
1. Create or open iOS project in Xcode:
```shell
open ios/Runner.xcworkspace
```

2. In Xcode:
   - Select Runner project > Runner target > Signing & Capabilities
   - Sign in to your Apple Developer account
   - Choose team and provisioning profile

##### Step 5: Build and archive for release
```shell
# Build for release
flutter build ios --release

# Open in Xcode to archive
open ios/Runner.xcworkspace
```
In Xcode:
1. Select Product > Archive
2. Wait for archiving to complete
3. In the Organizer, validate the archive
4. Distribute the app to App Store Connect

##### Step 6: Prepare for App Store submission
1. Create a privacy policy
2. Prepare store listing assets:
   - Screenshots for various devices
   - App preview videos (optional)
   - App icon (1024×1024 px)
   - App descriptions and keywords

##### Step 7: Submit to App Store Connect
1. Create a new app or new version
2. Complete all required information
3. Upload screenshots and preview media
4. Set pricing and availability
5. Submit for review

#### Resources:
- [Preparing an iOS app for release](https://flutter.dev/docs/deployment/ios)
- [iOS code signing guide](https://developer.apple.com/support/code-signing/)
- [App Store Connect guide](https://developer.apple.com/app-store-connect/)
- [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)

### Day 48: Responsive and Adaptive UI

#### Objectives:
- Learn how to create responsive UIs that work across different screen sizes
- Implement adaptive designs that respond to platform differences
- Master techniques for creating flexible layouts

#### Key Topics:
1. Responsive Design Principles
   - Understanding device constraints
   - Flexible vs fixed layouts
   - Screen size and orientation handling

2. Layout Techniques
   - MediaQuery and LayoutBuilder
   - Aspect ratio considerations
   - Flexible sizing with Expanded and Flexible

3. Device Adaptation
   - Platform-specific widgets (Cupertino vs Material)
   - Conditional rendering based on platform
   - Adapting to different form factors

4. Testing Responsiveness
   - Device preview tools
   - Responsive testing methods
   - Debugging layout issues

#### Sample Code:

##### Responsive Grid Layout
```dart
class ResponsiveGridLayout extends StatelessWidget {
  final List<Widget> children;
  
  const ResponsiveGridLayout({Key? key, required this.children}) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return LayoutBuilder(
      builder: (context, constraints) {
        // Calculate columns based on available width
        int crossAxisCount;
        if (constraints.maxWidth < 600) {
          crossAxisCount = 2; // Phone
        } else if (constraints.maxWidth < 900) {
          crossAxisCount = 3; // Tablet
        } else {
          crossAxisCount = 4; // Desktop or large tablet
        }
        
        return GridView.builder(
          gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
            crossAxisCount: crossAxisCount,
            childAspectRatio: 1.0,
            crossAxisSpacing: 8.0,
            mainAxisSpacing: 8.0,
          ),
          itemCount: children.length,
          itemBuilder: (context, index) => children[index],
        );
      },
    );
  }
}
```

##### Adaptive UI Based on Platform
```dart
class AdaptiveButton extends StatelessWidget {
  final String label;
  final VoidCallback onPressed;

  const AdaptiveButton({
    Key? key,
    required this.label,
    required this.onPressed,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    final platform = Theme.of(context).platform;
    
    if (platform == TargetPlatform.iOS) {
      return CupertinoButton(
        onPressed: onPressed,
        child: Text(label),
      );
    } else {
      return ElevatedButton(
        onPressed: onPressed,
        child: Text(label),
      );
    }
  }
}
```

##### Orientation-Responsive Layout
```dart
class OrientationResponsiveLayout extends StatelessWidget {
  final Widget portrait;
  final Widget landscape;
  
  const OrientationResponsiveLayout({
    Key? key,
    required this.portrait,
    required this.landscape,
  }) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    return OrientationBuilder(
      builder: (context, orientation) {
        return orientation == Orientation.portrait
            ? portrait
            : landscape;
      },
    );
  }
}
```

##### Using MediaQuery for Screen Awareness
```dart
class ResponsiveContainer extends StatelessWidget {
  final Widget child;
  
  const ResponsiveContainer({Key? key, required this.child}) : super(key: key);
  
  @override
  Widget build(BuildContext context) {
    final screenSize = MediaQuery.of(context).size;
    final isSmallScreen = screenSize.width < 600;
    
    return Container(
      padding: EdgeInsets.all(isSmallScreen ? 8.0 : 16.0),
      margin: EdgeInsets.all(isSmallScreen ? 8.0 : 16.0),
      width: isSmallScreen ? screenSize.width * 0.9 : screenSize.width * 0.7,
      child: child,
    );
  }
}
```

#### Resources:
- [Responsive design in Flutter](https://flutter.dev/docs/development/ui/layout/responsive)
- [Building adaptive apps](https://flutter.dev/docs/development/ui/layout/building-adaptive-apps)
- [Flutter's device_preview package](https://pub.dev/packages/device_preview)
- [MediaQuery documentation](https://api.flutter.dev/flutter/widgets/MediaQuery-class.html)
- [LayoutBuilder documentation](https://api.flutter.dev/flutter/widgets/LayoutBuilder-class.html)

### Day 49: Web Deployment

#### Objectives:
- Learn how to build and deploy Flutter web applications
- Understand web-specific configurations and optimizations
- Deploy to various hosting platforms

#### Key Topics:
1. Flutter Web Basics
   - Web renderer options (HTML vs CanvasKit)
   - Web performance considerations
   - Browser compatibility

2. Build Configuration
   - Web-specific settings
   - Asset optimization
   - Progressive Web App (PWA) setup

3. Deployment Options
   - Firebase Hosting
   - GitHub Pages
   - Netlify and Vercel
   - Custom web servers

4. Web-Specific Features
   - URL strategies
   - Browser history management
   - Web plugins and JavaScript interop

#### Sample Code - Web Deployment Configuration:

##### Web URL Strategy Configuration
```dart
import 'package:flutter/material.dart';
import 'package:flutter_web_plugins/flutter_web_plugins.dart';

void main() {
  // Configure URL strategy for web
  setUrlStrategy(PathUrlStrategy());
  
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Web App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: MyHomePage(),
    );
  }
}
```

##### JavaScript Interop Example
```dart
import 'dart:js' as js;
import 'package:flutter/material.dart';

class WebInteropDemo extends StatelessWidget {
  // Call JavaScript function from Dart
  void _callJavaScriptAlert(String message) {
    js.context.callMethod('alert', [message]);
  }
  
  // Get browser information
  String _getBrowserInfo() {
    return js.context['navigator']['userAgent'].toString();
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Web Interop Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () => _callJavaScriptAlert('Hello from Flutter!'),
              child: Text('Show JS Alert'),
            ),
            SizedBox(height: 20),
            Text('Browser Info:'),
            Padding(
              padding: EdgeInsets.all(16.0),
              child: Text(
                _getBrowserInfo(),
                textAlign: TextAlign.center,
                style: TextStyle(fontFamily: 'monospace', fontSize: 12),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

##### Firebase Web Hosting Configuration (index.html)
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flutter Web App</title>
  
  <!-- PWA meta tags -->
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black">
  <meta name="apple-mobile-web-app-title" content="Flutter Web">
  <link rel="apple-touch-icon" href="icons/Icon-192.png">
  <link rel="icon" type="image/png" href="favicon.png">
  <link rel="manifest" href="manifest.json">
  
  <!-- Optimization for initial load -->
  <script>
    // The value below is injected by flutter build, do not touch.
    var serviceWorkerVersion = null;
  </script>
  <script src="flutter.js" defer></script>
</head>
<body>
  <script>
    window.addEventListener('load', function() {
      // Wait for service worker registration
      navigator.serviceWorker.register('flutter_service_worker.js?v=' + serviceWorkerVersion);
      
      // Download main.dart.js
      _flutter.loader.loadEntrypoint({
        serviceWorker: {
          serviceWorkerVersion: serviceWorkerVersion,
        },
        onEntrypointLoaded: function(engineInitializer) {
          engineInitializer.initializeEngine().then(function(appRunner) {
            appRunner.runApp();
          });
        }
      });
    });
  </script>
</body>
</html>
```

#### Web Deployment Steps:

##### For Firebase Hosting:
1. Install Firebase CLI:
```shell
npm install -g firebase-tools
```

2. Build the web app:
```shell
flutter build web --release
```

3. Initialize Firebase in your project:
```shell
firebase login
firebase init hosting
```

4. Deploy to Firebase:
```shell
firebase deploy
```

##### For GitHub Pages:
1. Build for GitHub Pages:
```shell
flutter build web --release --base-href /your_repo_name/
```

2. Create a deploy script (deploy.sh):
```shell
#!/bin/bash
flutter build web --release --base-href /your_repo_name/
git checkout -b gh-pages
cp -R build/web/* .
git add .
git commit -m "Deploy to GitHub Pages"
git push origin gh-pages -f
git checkout master
```

#### Resources:
- [Flutter web documentation](https://flutter.dev/docs/get-started/web)
- [Web renderers in Flutter](https://flutter.dev/docs/development/tools/web-renderers)
- [Deploying to Firebase Hosting](https://firebase.google.com/docs/hosting/deploying)
- [GitHub Pages deployment](https://pages.github.com/)
- [Progressive Web Apps with Flutter](https://medium.com/flutter/bringing-progressive-web-apps-to-the-mainstream-with-flutter-b1b0a444a99)

[Return to top](#flutter-56-days-learning-path)

### Day 50: Desktop Deployment

#### Objectives:
- Understand how to build and deploy Flutter desktop applications
- Learn platform-specific configurations for Windows, macOS, and Linux
- Implement desktop-specific features and optimizations

#### Key Topics:
1. Desktop Platform Setup
   - Windows configuration
   - macOS configuration
   - Linux configuration
   - Development environment requirements

2. Desktop-Specific Features
   - Window management
   - Keyboard shortcuts and focus
   - Mouse and cursor handling
   - File system integration

3. Desktop UI Considerations
   - Menu bars and context menus
   - Desktop-specific layouts
   - Input handling differences
   - Native look and feel

4. Packaging and Distribution
   - Creating installers
   - Code signing
   - Auto-updates
   - App store submissions (Microsoft Store, Mac App Store)

#### Sample Code - Desktop Features:

##### Window Management
```dart
import 'package:flutter/material.dart';
import 'package:window_manager/window_manager.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  
  // Initialize window manager
  await windowManager.ensureInitialized();
  
  // Configure window properties
  WindowOptions windowOptions = WindowOptions(
    size: Size(800, 600),
    center: true,
    backgroundColor: Colors.transparent,
    skipTaskbar: false,
    title: "Flutter Desktop App",
  );
  
  await windowManager.waitUntilReadyToShow(windowOptions, () async {
    await windowManager.show();
    await windowManager.focus();
  });
  
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Desktop Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: DesktopHomePage(),
    );
  }
}

class DesktopHomePage extends StatefulWidget with WindowListener {
  @override
  _DesktopHomePageState createState() => _DesktopHomePageState();
}

class _DesktopHomePageState extends State<DesktopHomePage> with WindowListener {
  @override
  void initState() {
    super.initState();
    windowManager.addListener(this);
  }
  
  @override
  void dispose() {
    windowManager.removeListener(this);
    super.dispose();
  }
  
  @override
  void onWindowClose() async {
    bool isPreventClose = await windowManager.isPreventClose();
    if (isPreventClose) {
      showDialog(
        context: context,
        builder: (_) {
          return AlertDialog(
            title: Text('Confirm close'),
            content: Text('Are you sure you want to close this window?'),
            actions: [
              TextButton(
                child: Text('Cancel'),
                onPressed: () {
                  Navigator.of(context).pop();
                },
              ),
              TextButton(
                child: Text('Yes'),
                onPressed: () {
                  Navigator.of(context).pop();
                  windowManager.destroy();
                },
              ),
            ],
          );
        },
      );
    }
  }
  
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Flutter Desktop Demo'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              'Flutter Desktop Application',
              style: TextStyle(fontSize: 24),
            ),
            SizedBox(height: 20),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                ElevatedButton(
                  onPressed: () async {
                    await windowManager.minimize();
                  },
                  child: Text('Minimize'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () async {
                    await windowManager.maximize();
                  },
                  child: Text('Maximize'),
                ),
                SizedBox(width: 10),
                ElevatedButton(
                  onPressed: () async {
                    await windowManager.close();
                  },
                  child: Text('Close'),
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}
```

##### Desktop Menu Bar
```dart
import 'package:flutter/material.dart';
import 'package:menubar/menubar.dart';

void main() {
  runApp(MyApp());
  
  // Set up the native menu bar
  setApplicationMenu([
    Submenu(
      label: 'File',
      children: [
        MenuItem(
          label: 'New',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyN),
          onClicked: () {
            print('New file');
          },
        ),
        MenuItem(
          label: 'Open',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyO),
          onClicked: () {
            print('Open file');
          },
        ),
        MenuDivider(),
        MenuItem(
          label: 'Exit',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyQ),
          onClicked: () {
            exit(0);
          },
        ),
      ],
    ),
    Submenu(
      label: 'Edit',
      children: [
        MenuItem(
          label: 'Cut',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyX),
          onClicked: () {
            print('Cut');
          },
        ),
        MenuItem(
          label: 'Copy',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyC),
          onClicked: () {
            print('Copy');
          },
        ),
        MenuItem(
          label: 'Paste',
          shortcut: LogicalKeySet(LogicalKeyboardKey.meta, LogicalKeyboardKey.keyV),
          onClicked: () {
            print('Paste');
          },
        ),
      ],
    ),
    Submenu(
      label: 'Help',
      children: [
        MenuItem(
          label: 'About',
          onClicked: () {
            print('About');
          },
        ),
      ],
    ),
  ]);
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Desktop Menu Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('Desktop Menu Demo'),
        ),
        body: Center(
          child: Text(
            'Check the native menu bar at the top of the screen',
            style: TextStyle(fontSize: 18),
          ),
        ),
      ),
    );
  }
}
```

#### Desktop Deployment Steps:

##### For Windows:
1. Enable Windows support:
```shell
flutter config --enable-windows-desktop
```

2. Build the Windows app:
```shell
flutter build windows --release
```

3. Create installer with InnoSetup or MSIX Packaging Tool

##### For macOS:
1. Enable macOS support:
```shell
flutter config --enable-macos-desktop
```

2. Build the macOS app:
```shell
flutter build macos --release
```

3. Code signing:
```shell
codesign --force --deep --sign "Developer ID Application: Your Name (TEAM_ID)" build/macos/Build/Products/Release/YourApp.app
```

4. Create DMG:
```shell
create-dmg \
  --volname "Your App" \
  --volicon "assets/icon.icns" \
  --window-pos 200 120 \
  --window-size 800 400 \
  --icon-size 100 \
  --icon "YourApp.app" 200 190 \
  --hide-extension "YourApp.app" \
  --app-drop-link 600 185 \
  "YourApp-Installer.dmg" \
  "build/macos/Build/Products/Release/YourApp.app"
```

##### For Linux:
1. Enable Linux support:
```shell
flutter config --enable-linux-desktop
```

2. Build the Linux app:
```shell
flutter build linux --release
```

3. Create Debian package:
```shell
# Install dependencies
sudo apt-get install ruby ruby-dev rubygems build-essential
sudo gem install fpm

# Create package
fpm -s dir -t deb -n your-app -v 1.0.0 \
  --vendor "Your Company" \
  --license "Your License" \
  --description "Your App Description" \
  --url "https://yourwebsite.com" \
  -d "libgtk-3-0" -d "libblkid1" -d "liblzma5" \
  build/linux/x64/release/bundle=/usr/local/your-app \
  yourapp.desktop=/usr/share/applications/ \
  yourapp.png=/usr/share/icons/hicolor/256x256/apps/
```

#### Resources:
- [Flutter desktop documentation](https://flutter.dev/desktop)
- [window_manager package](https://pub.dev/packages/window_manager)
- [menubar package](https://pub.dev/packages/menubar)
- [file_selector package](https://pub.dev/packages/file_selector)
- [Windows deployment guide](https://docs.flutter.dev/platform-integration/windows/building)
- [macOS deployment guide](https://docs.flutter.dev/platform-integration/macos/building)
- [Linux deployment guide](https://docs.flutter.dev/platform-integration/linux/building)

[Return to top](#flutter-56-days-learning-path)

### Day 51: Continuous Integration and Continuous Deployment (CI/CD)

#### Objectives:
- Learn how to set up CI/CD pipelines for Flutter applications
- Understand automated testing, building, and deployment strategies
- Implement CI/CD for different platforms (mobile, web, desktop)

#### Key Topics:
1. CI/CD Fundamentals
   - Continuous Integration principles
   - Continuous Deployment/Delivery concepts
   - Benefits for Flutter development workflow

2. CI/CD Platforms
   - GitHub Actions
   - Codemagic
   - Bitrise
   - CircleCI
   - Firebase App Distribution

3. Automated Testing in CI
   - Unit tests
   - Widget tests
   - Integration tests
   - Test coverage reporting

4. Automated Building and Deployment
   - Multi-platform build configuration
   - Environment management
   - Versioning strategies
   - Release channels (alpha, beta, production)

#### Sample Code - GitHub Actions Workflow:

```yaml
name: Flutter CI/CD

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    name: Test on ${{ matrix.os }}
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest, macos-latest]
    
    steps:
      - uses: actions/checkout@v3
      - uses: subosito/flutter-action@v2
        with:
          flutter-version: '3.10.0'
          channel: 'stable'
      
      - name: Get dependencies
        run: flutter pub get
      
      - name: Verify formatting
        run: flutter format --set-exit-if-changed .
      
      - name: Analyze project source
        run: flutter analyze
      
      - name: Run tests
        run: flutter test --coverage
      
      - name: Upload coverage to Codecov
        uses: codecov/codecov-action@v3
        with:
          file: coverage/lcov.info

  build-android:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          distribution: 'zulu'
          java-version: '11'
      
      - uses: subosito/flutter-action@v2
        with:
          flutter-version: '3.10.0'
          channel: 'stable'
      
      - name: Get dependencies
        run: flutter pub get
      
      - name: Build APK
        run: flutter build apk --release
      
      - name: Upload APK
        uses: actions/upload-artifact@v3
        with:
          name: release-apk
          path: build/app/outputs/flutter-apk/app-release.apk
      
      - name: Upload to Firebase App Distribution
        uses: wzieba/Firebase-Distribution-Github-Action@v1
        with:
          appId: ${{ secrets.FIREBASE_ANDROID_APP_ID }}
          serviceCredentialsFileContent: ${{ secrets.FIREBASE_CREDENTIALS }}
          groups: testers
          file: build/app/outputs/flutter-apk/app-release.apk
          releaseNotes: "New build from GitHub Actions"

  build-ios:
    needs: test
    runs-on: macos-latest
    steps:
      - uses: actions/checkout@v3
      - uses: subosito/flutter-action@v2
        with:
          flutter-version: '3.10.0'
          channel: 'stable'
      
      - name: Get dependencies
        run: flutter pub get
      
      - name: Build iOS
        run: |
          flutter build ios --release --no-codesign
          cd ios
          xcodebuild -workspace Runner.xcworkspace -scheme Runner -sdk iphoneos -configuration Release archive -archivePath Runner.xcarchive
          xcodebuild -exportArchive -archivePath Runner.xcarchive -exportOptionsPlist ExportOptions.plist -exportPath build
      
      - name: Upload IPA
        uses: actions/upload-artifact@v3
        with:
          name: release-ipa
          path: ios/build/Runner.ipa
```

#### CI/CD Environment Setup:

##### Setting up Flutter in CI environment
```yaml
# Setting up Flutter in GitHub Actions
- uses: subosito/flutter-action@v2
  with:
    flutter-version: '3.10.0'
    channel: 'stable'
```

##### Environment Variables Management
```dart
// Using environment variables in Flutter app
import 'package:flutter_dotenv/flutter_dotenv.dart';

Future<void> main() async {
  // Load environment variables based on build configuration
  await dotenv.load(fileName: ".env.${const String.fromEnvironment('ENV', defaultValue: 'dev')}");
  
  runApp(MyApp());
}

// Accessing environment variables
final apiKey = dotenv.env['API_KEY'] ?? 'default_key';
```

##### Fastlane for iOS deployment
```ruby
# Fastfile
default_platform(:ios)

platform :ios do
  desc "Build and upload to TestFlight"
  lane :beta do
    setup_ci if ENV['CI']
    match(type: "appstore", readonly: is_ci)
    build_app(
      workspace: "Runner.xcworkspace",
      scheme: "Runner",
      export_method: "app-store",
      output_directory: "build"
    )
    upload_to_testflight(
      skip_waiting_for_build_processing: true
    )
  end
  
  desc "Deploy to App Store"
  lane :release do
    setup_ci if ENV['CI']
    match(type: "appstore", readonly: is_ci)
    build_app(
      workspace: "Runner.xcworkspace",
      scheme: "Runner",
      export_method: "app-store",
      output_directory: "build"
    )
    upload_to_app_store(
      force: true,
      skip_metadata: true,
      skip_screenshots: true,
      submit_for_review: true
    )
  end
end
```

#### Resources:
- [Flutter CI/CD with GitHub Actions](https://docs.flutter.dev/deployment/cd)
- [Codemagic CI/CD for Flutter](https://docs.codemagic.io/flutter-configuration/flutter-projects/)
- [Bitrise Flutter documentation](https://devcenter.bitrise.io/en/getting-started/getting-started-with-flutter-apps)
- [Firebase App Distribution](https://firebase.google.com/docs/app-distribution)
- [Fastlane documentation](https://docs.fastlane.tools/)

[Return to top](#flutter-56-days-learning-path)### Day 52: Flutter Hooks

#### Objectives:
- Understand Flutter Hooks and their advantages
- Learn how to use built-in hooks
- Create custom hooks for reusable logic

#### Key Topics:
1. Introduction to Hooks
   - What are Flutter Hooks?
   - Advantages over StatefulWidget
   - When to use hooks

2. Built-in Hooks
   - useState
   - useEffect
   - useContext
   - useMemoized
   - useRef

3. Creating Custom Hooks
   - Hook composition
   - Reusable logic patterns
   - Best practices

4. Advanced Hook Patterns
   - Complex state management with hooks
   - Combining hooks with other patterns
   - Performance considerations

#### Sample Code - Flutter Hooks:

```dart
import 'package:flutter/material.dart';
import 'package:flutter_hooks/flutter_hooks.dart';

// Basic counter with hooks
class CounterWithHooks extends HookWidget {
  @override
  Widget build(BuildContext context) {
    // Similar to useState in React
    final counter = useState(0);
    
    return Scaffold(
      appBar: AppBar(title: Text('Hooks Counter')),
      body: Center(
        child: Text(
          'Count: ${counter.value}',
          style: Theme.of(context).textTheme.headlineMedium,
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () => counter.value++,
        child: Icon(Icons.add),
      ),
    );
  }
}

// Custom hook for animation
Hook<Animation<double>> useAnimation({Duration duration = const Duration(milliseconds: 750)}) {
  return use(_AnimationHook(duration: duration));
}

class _AnimationHook extends Hook<Animation<double>> {
  final Duration duration;
  
  const _AnimationHook({required this.duration});
  
  @override
  _AnimationHookState createState() => _AnimationHookState();
}

class _AnimationHookState extends HookState<Animation<double>, _AnimationHook> {
  late AnimationController controller;
  late Animation<double> animation;
  
  @override
  void initHook() {
    controller = AnimationController(
      vsync: useAnimationController().vsync,
      duration: hook.duration,
    );
    animation = Tween<double>(begin: 0.0, end: 1.0).animate(controller);
    controller.forward();
  }
  
  @override
  Animation<double> build(BuildContext context) => animation;
  
  @override
  void dispose() {
    controller.dispose();
    super.dispose();
  }
}

// Using multiple hooks together
class AnimatedCounterWithHooks extends HookWidget {
  @override
  Widget build(BuildContext context) {
    final counter = useState(0);
    final animation = useAnimation();
    
    // Similar to useEffect in React
    useEffect(() {
      print('Counter changed to ${counter.value}');
      return null; // cleanup function (optional)
    }, [counter.value]); // dependencies
    
    return Scaffold(
      appBar: AppBar(title: Text('Animated Hooks')),
      body: Center(
        child: ScaleTransition(
          scale: animation,
          child: Text(
            'Count: ${counter.value}',
            style: Theme.of(context).textTheme.headlineMedium,
          ),
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () => counter.value++,
        child: Icon(Icons.add),
      ),
    );
  }
}
```

#### Resources:
- [Flutter Hooks Package](https://pub.dev/packages/flutter_hooks)
- [Flutter Hooks Introduction](https://medium.com/@dan_abramov/making-sense-of-react-hooks-fdbde8803889)
- [Custom Hooks Examples](https://github.com/rrousselGit/flutter_hooks/blob/master/example/lib/main.dart)
- [Hooks vs StatefulWidget](https://blog.gskinner.com/archives/2020/09/flutter-state-management-with-hooks.html)

[Return to top](#flutter-56-days-learning-path) 