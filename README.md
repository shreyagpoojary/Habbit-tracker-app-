# Habbit-tracker-app-
habit tracker app that allows users to create, manage, and track their daily habits. The app should be user-friendly and visually appealing, providing essential features for habit formation and tracking
Certainly! To run the Habit tracker app, you will need to follow a few steps:
- Download and install Android Studio on your computer.
- Download or clone [Habit tracker App](https://github.com/shreyagpoojary/habit tracker app) repository by using the link below:
```
git clone https://github.com/shreyagpoojary/habit tracker app
```
- Open Android Studio and select "Open an existing Android Studio project" from the welcome screen.
- Navigate to the directory where you cloned the Habit It app repository and select the project folder.
- Go to the project root and execute the following command in the console to get the required dependencies:
```
flutter pub get
```
- Once the project has finished loading, you can either connect your Android device to your computer using a USB cable or create an emulator in Android Studio.
- If you're using a physical device, make sure to enable USB debugging mode on your phone by going to "Developer options" in your phone's settings and toggling the "USB debugging" option.
- Select the device you want to run the app on by clicking on the device dropdown menu in Android Studio.
- Finally, Run the app.
```
flutter run
```
By following these steps, you should be able to run the Habit It app on your Android device or emulator without any issues. However, keep in mind that the exact process may vary depending on your specific setup and the version of Android Studio you are using.

To start the Habit Tracker project, follow these steps:

*Step 1: Set up a new Flutter project*

- Open your IDE (e.g., Android Studio, Visual Studio Code)
- Create a new Flutter project
- Name your project (e.g., "HabitTracker")

*Step 2: Add dependencies*

- In your `pubspec.yaml` file, add the following dependencies:
```
dependencies:
  flutter:
    sdk: flutter
  firebase_core: ^1.10.0
  firebase_auth: ^3.3.0
  cloud_firestore: ^3.1.0
```
- Run `flutter pub get` to install the dependencies

*Step 3: Create the Habit model*

- Create a new file `habits.dart`
- Add the following code:
```
class Habit {
  String name;
  bool completed;

  Habit({this.name, this.completed = false});
}
```
*Step 4: Create the Habit Tracker UI*

- Create a new file `habits_screen.dart`
- Add the following code:
```
import 'package:flutter/material.dart';

class HabitsScreen extends StatefulWidget {
  @override
  _HabitsScreenState createState() => _HabitsScreenState();
}

class _HabitsScreenState extends State<HabitsScreen> {
  List<Habit> _habits = [];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Habit Tracker'),
      ),
      body: ListView.builder(
        itemCount: _habits.length,
        itemBuilder: (context, index) {
          return ListTile(
            title: Text(_habits[index].name),
            trailing: Checkbox(
              value: _habits[index].completed,
              onChanged: (value) {
                setState(() {
                  _habits[index].completed = value;
                });
              },
            ),
          );
        },
      ),
    );
  }
}
```
*Step 5: Add habits to the UI*

- In the `habits_screen.dart` file, add a button to add new habits
- When the button is pressed, add a new habit to the `_habits` list
- Use the `setState` method to update the UI
