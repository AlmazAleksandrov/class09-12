### Task 7kyu:

Given two Arrays in which values are the power of each soldier, return true if you survive the attack or false if you perish.

[Task link](https://www.codewars.com/kata/634d0f7c562caa0016debac5/train/java)

#### Solution:
```
import java.util.Arrays;

public class Kumite{
  public static boolean block(int[] attackers, int[] defenders){
    int survivorsCount = 0;

    int lengthDiff = attackers.length - defenders.length;

    for ( int i = 0; i < Math.min(attackers.length, defenders.length); i++) {
        if (attackers[i] - defenders[i] < 0) {
            survivorsCount += 1;
        } else if (attackers[i] - defenders[i] > 0){
            survivorsCount -= 1;
        }
    }

    if (lengthDiff < 0) {
        survivorsCount += Math.abs(lengthDiff);
    } else {
        survivorsCount -= lengthDiff;
    }

    int damage = Arrays.stream(attackers).sum() - Arrays.stream(defenders).sum();

    if (survivorsCount < 0) {
        return false;
    } else if (survivorsCount > 0) {
        return true;
    } else if (damage > 0){
        return false;
    }

    return true;
  }
}
```

#### Fav solution:
```
import static java.util.stream.IntStream.of;

interface Kumite {
  static boolean block(int[] attackers, int[] defenders) {
    int survived = defenders.length - attackers.length;
    for (int i = 0; i < Math.min(defenders.length, attackers.length); i++) {
      survived += Math.signum(defenders[i] - attackers[i]);
    }
    return survived > 0 || survived == 0 && of(defenders).sum() >= of(attackers).sum();
  }
}
```

#### Comment:
I have been trying to solve the problem for a very long time. It should be 6Kyu imo.


### Task 7kyu:

You are given an input (n) which represents the amount of lines you are given,
your job is to figure out what is the maximum amount of perpendicular bisectors you can make using these lines.

[Task link](https://www.codewars.com/kata/6391fe3f322221003db3bad6/java)

#### Solution:
```
public class Perpendicular {
  public static int maxBisectors(int n) {
    return (int) Math.pow((double) n/2, 2);
  }
}
```

#### Fav solution:
```
public class Perpendicular {
  public static int maxBisectors(int n) {
    return (int) Math.pow((double) n/2, 2);
  }
}
```

#### Comment:
After the previous task, this task is about nothing.
