Full Quran text and Surah details

## Getting Started

To use this plugin, add `quran` as a [dependency in your pubspec.yaml file](https://flutter.io/platform-plugins/).

**Functions:**

* **`getSurahName(int surahNumber)`** - Get Surah Name by surah number
* **`getSurahNameEnglish(int surahNumber)`** - Get Surah English Title by surah number
* **`getAyaCount(int surahNumber)`** - Get Aya Count by surah number
* **`getPlaceOfRevelation(int surahNumber)`** - Get Place of Revelation (Makkah / Madinah)
* **`getVerse(int surahNumber, int verseNumber)`** - Get Verse (text) by surah number and verse number
* **`getTotalAyaCount()`** - Get total aya count
* **`getTotalSurahCount()`** - Get total surah count


## Example
![example](https://raw.githubusercontent.com/aqeelshamz/quran/main/images/1.png)

```dart
import 'package:flutter/material.dart';
import 'package:quran/quran.dart';

void main(){
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(
        title: Text("Quran Demo"),
      ),
      body: SafeArea(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text("Surah: ${getSurahName(1)}"),
            Text("English title: ${getSurahNameEnglish(1)}"),
            Text("Aya: ${getAyaCount(1)}"),
            Text("Place of Revelation: ${getPlaceOfRevelation(1)}"),
            Text("Verse 1: ${getVerse(1, 1)}")
          ],
        ),
      ),
    ),
  ));
}
```

![example2](https://raw.githubusercontent.com/aqeelshamz/quran/main/images/2.png)

```dart
import 'package:flutter/material.dart';
import 'package:quran/quran.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(
        title: Text("Quran Demo"),
      ),
      body: SafeArea(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text("Surah: ${getSurahName(1)}"),
            Text("English title: ${getSurahNameEnglish(1)}"),
            Text("Aya: ${getAyaCount(1)}"),
            Text("Place of Revelation: ${getPlaceOfRevelation(1)}"),
            Text("Verses: "),
            Expanded(
              child: ListView.builder(
                itemCount: getAyaCount(1),
                itemBuilder: (context, index) {
                  return Text("${index+1}. ${getVerse(1, index + 1)}");
                },
              ),
            ),
          ],
        ),
      ),
    ),
  ));
}
```
