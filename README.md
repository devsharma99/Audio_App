import 'package:flutter/material.dart';
import 'package:audioplayers/audioplayers.dart';
import 'package:audioplayers/audio_cache.dart';

void main() => runApp(MyApp());

var EmailButton = Icon(Icons.email);
var AccountButton = Icon(Icons.account_circle);

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('Assets App'),
          backgroundColor: Colors.amber,
          actions: <Widget>[
            EmailButton,
            AccountButton,
          ],
        ),
        body: Center(
          child: Container(
            width: 300,
            height: 300,
            decoration: BoxDecoration(
              borderRadius: BorderRadius.circular(20),
            ),
            child: Card(
                color: Colors.amber,
                child: Column(
                  children: <Widget>[
                    Card(
                      margin: EdgeInsets.all(30),
                      child: Image.asset('images/dev_photo.jpeg'),
                    ),
                    Card(
                      color: Colors.blue,
                      child: RaisedButton(onPressed: () {
                        var audio = AudioCache();
                        audio.play('ringtone1.mp3');
                      }),
                    ),
                  ],
                )),
          ),
        ),
      ),
    );
  }
}
