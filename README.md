# 07.10.22
## 1. Who remembers back to their time in the schoolyard, when girls would take a flower and tear its petals, saying each of the following phrases each time a petal was torn:

"I love you"
"a little"
"a lot"
"passionately"
"madly"
"not at all"
If there are more than 6 petals, you start over with "I love you", "a little" and so on.

When the last petal was torn there were cries of excitement, dreams, surging thoughts and emotions.

Your goal in this kata is to determine which phrase the girls would say at the last petal for a flower of a given number of petals. The number of petals is always greater than 0.
___
### Мое рещение
```java

public class Sid {
public static String howMuchILoveYou(int nb_petals){

String[] arr ={"not at all", "I love you", "a little", "a lot", "passionately", "madly"};
return arr[nb_petals%6];
}
}

```

### Понравившееся решение
```java

import java.util.List;

class Sid {
static String howMuchILoveYou(int nb_petals) {
return List.of("not at all", "I love you", "a little", "a lot", "passionately", "madly").get(nb_petals % 6);
}
}
```
## 2 Our football team has finished the championship.

Our teams match results are recorded in a collection of strings. Each match is represented by a string in the format "x:y", where x us our teams score and y is our opponents score.

For example: ["3:1", "2:2", "0:1", ...]

Points are awarded for each match as follows:

if x > y: 3 points (win)
if x < y: 0 points (loss)
if x = y: 1 point (tie)
We need to write a function that takes this collection and returns the number of points our team (x) got in the championship by the rules given above.

Notes:

our team always plays 10 matches in the championship
0 <= x <= 4
0 <= y <= 4
### Мое рещение
```java

public class TotalPoints {

public static int points(String[] games) {
int win = 0;
int draw = 0;
for (int i = 0; i< games.length; i++) {
if (games[i].equals("4:0") || games[i].equals("4:1") || games[i].equals("4:2") || games[i].equals("4:3")) {
win++;
}
if (games[i].equals("3:0") || games[i].equals("3:1") || games[i].equals("3:2")) {
win++;
}
if (games[i].equals("2:0") || games[i].equals("2:1") || games[i].equals("1:0")) {
win++;
}
if (games[i].equals("4:4") || games[i].equals("3:3") || games[i].equals("2:2") || games[i].equals("1:1") || games[i].equals("0:0")) {
draw++;
}
}
```

### Понравившееся решение
```java

public class TotalPoints {

public static int points(String[] games) {
int points = 0;
for (String game : games) {
String[] scores = game.split(":");
int x = Integer.parseInt(scores[0]);
int y = Integer.parseInt(scores[1]);
if (x > y) {
points += 3;
} else if (x == y) {
points++;
}
}
return points;
}
}

``` 
