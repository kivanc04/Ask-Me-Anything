# Ask-Me-Anything

When you click it, it gives you feedback as ‘Ask Again Later’, ‘Yes’, ‘No’, or ‘I Have No Idea’.

import 'package:flutter/material.dart';
import 'dart:math';

void main() {
  return runApp(
    MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.blue,
        appBar: AppBar(
          backgroundColor: Colors.blue.shade900,
          title: Text('Ask Me Anything'),
        ),
        body: Ball(),
      ),
    ),
  );
}

class BallPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container();
  }
}

class Ball extends StatefulWidget {
  @override
  State<Ball> createState() => _BallState();
}

class _BallState extends State<Ball> {
  int BallNumber = 1;
  @override
  Widget build(BuildContext context) {
    return Center(
      child: Row(
        children: <Widget>[
          Expanded(
            child: TextButton(
              child: Image.asset('images/ball$BallNumber.png'),
              onPressed: () {
                setState(() {
                  BallNumber = Random().nextInt(5) + 1;
                  print(BallNumber);
                });
              },
            ),
          ),
        ],
      ),
    );
  }
}
