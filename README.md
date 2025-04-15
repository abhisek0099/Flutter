//Routing

import 'package:flutter/material.dart';
import 'package:nishapp/Screens/home_screen.dart';
import 'package:nishapp/Screens/profile_screein.dart';

void main() => runApp(
  MaterialApp(
    title: 'My First App',
    debugShowCheckedModeBanner: false,
    initialRoute: '/',
    routes: {
      '/':(context) => Home(),
      '/profile':(context) => Profile(),
    },
  ),
);


//home screen 

import 'package:flutter/material.dart';





class Home extends StatefulWidget {

  @override
  State<Home> createState() => _HomeState();
}

class _HomeState extends State<Home> {
  int _selectedItem = 0;
  void _onTapItem(int index){
    setState(() {
      _selectedItem = index;
    });
    if(index ==4){
      Navigator.pushNamed(context, '/profile');
    }
  }
  @override
  Widget build(BuildContext context) {
    return
      Scaffold(
        appBar: AppBar(
        title: Text(
        'Home', style: TextStyle(fontSize: 25),),
    centerTitle: true,
    ),
        body: Center(child: Text('Current Index -$_selectedItem',
          style: TextStyle(fontSize: 30),)
        ),
        bottomNavigationBar: BottomNavigationBar(type: BottomNavigationBarType.
        fixed,items: const<BottomNavigationBarItem>[
          BottomNavigationBarItem(
            icon: Icon(Icons.home),
            label: 'Home',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.search),
            label: 'Search',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.add_circle),
            label: 'Add',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.favorite),
            label: 'Favorite',
          ),
          BottomNavigationBarItem(
            icon: Icon(Icons.person_outline),
            label: 'Profile',
          ),
        ],
          currentIndex: _selectedItem,
          onTap: _onTapItem,
          selectedFontSize: 17,
          selectedItemColor: Colors.red,
        ),
      );
  }
}


//profile screen 
import 'package:flutter/material.dart';

class Profile extends StatelessWidget {


  @override
  Widget build(BuildContext context) {
    return Scaffold(appBar: AppBar(
      title: Text('Profile'),
    ),
      body: Center(
        child: Text('Profile page'),
      ),
    );
  }
}




