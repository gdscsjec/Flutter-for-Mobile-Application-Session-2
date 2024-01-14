# Flutter-for-Mobile-Application-Session-2

We will set-up a clean project to work on the topic "Spotify-Clone" using flutter.

**Command to create the flutter project:**<br>
**_flutter create project-name_**

```bash
flutter create spotify-clone
cd spotify-clone
code .
```

**Change organisation name:**
<br>
To set the package name for your application, then we need to change the organization name.

Navigate to android > app > build.gradle folder

<li>Locate <b>android</b>:

![locate android](images\organization_name.png)

<li>Change namespace "com.your_name.project_name"

![change name](images\name_change.png)

**To start our project:**

Navigate to root > lib > main.dart

<ul>
<li>To create the Splash screen, create a new folder called layout in the lib folder:
<br>

<li>Somewhat path looks like: spotify-clone > lib > layouts > splashscreen.dart

<li>Type stful and hit enter to create a stateful widget.
<li>Name the class as Splash
</ul>

```dart
import 'package:flutter/material.dart';
import 'package:ia/screens/home.dart';

class Splash extends StatefulWidget {
  const Splash({super.key});

  @override
  State<Splash> createState() => _SplashState();
}

class _SplashState extends State<Splash> {
  @override
  void initState() {
    super.initState();
    navToHome();
  }

  navToHome() async {
    await Future.delayed(const Duration(milliseconds: 2000), () {});
    Navigator.pushReplacement(
        context, MaterialPageRoute(builder: (context) => const Home()));
  }

  @override
  Widget build(BuildContext context) {
    return const Scaffold(
        backgroundColor: Color(0xFF393646),
        body: Center(
          child: Image(image: AssetImage('assets/splash.png')),
        ));
  }
}
```

- Install **Thunder Client Extension** using VScode extension section or click
  [here](vscode:extension/rangav.vscode-thunder-client) to download.

<ul>
<li>Creating the Input field to hold the value to search a song
<br>
<li>Type stful and hit enter to create a stateful widget.
<li>Name the class as Home
</ul>

```dart
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';
import 'package:flutter/widgets.dart';

class Home extends StatefulWidget {
  const Home({super.key});

  @override
  State<Home> createState() => _HomeState();
}

class _HomeState extends State<Home> {
  @override
  Widget build(BuildContext context) {
    return  Scaffold(
      body: Center(
        child: Column(
          children: [
            TextField(onSubmitted: (value) => {
           },
              decoration: const InputDecoration(
                border: OutlineInputBorder(),
                labelText: 'Search Song',
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```
