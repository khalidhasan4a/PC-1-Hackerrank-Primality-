ID : IT24013


# HackerRank Java Solutions - PC#1 ICT 21 Batch


1. Prime Checker
2. Java Primality Test

---

## 1. Prime Checker

### Problem
`Prime` naame ekta class banate hobe, jar moddhe shudhu ekta method `checkPrime` thakbe. Method ta one ba tar beshi integer argument nibe ebong shudhu prime number gulo print korbe. Method overloading use kora jabe na. `BufferedReader br=new BufferedReader(new InputStreamReader(in));` line e compile error ashbe, seta fix korte hobe.

### Approach
- Overloading charai sob dhoroner call handle korar jonno **varargs** (`int... nums`) use kora hoyeche.
- `in` er compile error fix korte file er sobar upore `import static java.lang.System.*;` deya hoyeche.
- Prime check korte `2` theke `sqrt(n)` porjonto loop chalano hoyeche.
- Prime na thakle blank line print hoy.

### Code

```java
import static java.lang.System.*;
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
import java.lang.reflect.*;

class Prime {
    public void checkPrime(int... nums) {
        StringBuilder sb = new StringBuilder();
        for (int n : nums) {
            if (isPrime(n)) {
                sb.append(n).append(" ");
            }
        }
        System.out.println(sb.toString());
    }

    private boolean isPrime(int n) {
        if (n < 2) return false;
        for (int i = 2; (long) i * i <= n; i++) {
            if (n % i == 0) return false;
        }
        return true;
    }
}

public class Solution {

    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(in));
            int n1 = Integer.parseInt(br.readLine());
            int n2 = Integer.parseInt(br.readLine());
            int n3 = Integer.parseInt(br.readLine());
            int n4 = Integer.parseInt(br.readLine());
            int n5 = Integer.parseInt(br.readLine());
            Prime ob = new Prime();
            ob.checkPrime(n1);
            ob.checkPrime(n1, n2);
            ob.checkPrime(n1, n2, n3);
            ob.checkPrime(n1, n2, n3, n4, n5);
            Method[] methods = Prime.class.getDeclaredMethods();
            Set<String> set = new HashSet<>();
            boolean overload = false;
            for (int i = 0; i < methods.length; i++) {
                if (set.contains(methods[i].getName())) {
                    overload = true;
                    break;
                }
                set.add(methods[i].getName());
            }
            if (overload) {
                throw new Exception("Overloading not allowed");
            }
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

### Sample

```
Input:      Output:
2           2 
1           2 
3           2 3 
4           2 3 5 
5
```

### Screenshots

![Prime Checker - Leaderboard](Screenshot/Prime%20Checker.png)

![Prime Checker - All test cases passed](Screenshot/Screenshot%202026-10-31%20125529.png)

---

## 2. Java Primality Test

### Problem


### Code

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        String n = bufferedReader.readLine();

        bufferedReader.close();

        BigInteger num = new BigInteger(n.trim());
        if (num.isProbablePrime(100)) {
            System.out.println("prime");
        } else {
            System.out.println("not prime");
        }
    }
}
```

### Sample

```
Input:  13
Output: prime
```

### Screenshots

![Java Primality Test - Leaderboard](Screenshot/Java%20Primality%20Test.png)

![Java Primality Test - All test cases passed](Screenshot/Screenshot%202026-10-31%20125934.png)
