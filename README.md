# Cool Bottom Bar

Inspired by

https://dribbble.com/shots/5925052-Google-Bottom-Bar-Navigation-Pattern

# Preview
https://youtu.be/CxQYiHvQ20s

<!--[![Preview](https://img.youtube.com/vi/CxQYiHvQ20s/0.jpg)](https://youtu.be/CxQYiHvQ20s "Everything Is AWESOME")-->

## Usage 

add to pubsec

`cool_bar: 0.0.1`

import 

`import 'package:flutter_app/CoolBottomBar.dart';`


## Example

```import 'package:flutter/material.dart';
import 'package:cool_bar/cool_bar.dart';
import 'package:flutter/material.dart';

class HomePage extends StatefulWidget {
  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  int selected = 0;

  List colors = [Colors.deepPurple, Colors.pink, Colors.yellow, Colors.cyan];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Cool Bar"),
        backgroundColor: colors[selected],
      ),
      body: AnimatedContainer(
        duration: Duration(milliseconds: 200),
        color: colors[selected],
      ),
      bottomNavigationBar: CoolBottomBar(
        items: <CoolBarItem>[
          CoolBarItem(
            icon: Icon(Icons.home),
            activeColor: Colors.deepPurple[700],
            backgroundColor: Colors.deepPurple[100],
            title: "Home",
          ),
          CoolBarItem(
            icon: Icon(Icons.favorite_border),
            activeColor: Colors.pink[700],
            backgroundColor: Colors.pink[100],
            title: "Likes",
          ),
          CoolBarItem(
            icon: Icon(Icons.search),
            activeColor: Colors.yellow[700],
            backgroundColor: Colors.yellow[100],
            title: "Search",
          ),
          CoolBarItem(
            icon: Icon(Icons.person),
            activeColor: Colors.cyan[700],
            backgroundColor: Colors.cyan[100],
            title: "Profile",
          )
        ],
        selectedIndex: selected,
        itemClicked: (int index) {
          setState(() {
            selected = index;
          });
        },
      ),
    );
  }
}
```