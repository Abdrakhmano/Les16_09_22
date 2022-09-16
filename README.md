### Task №1(8kyu):

Complete the solution so that it reverses the string passed into it.

[Task_link](https://www.codewars.com/kata/5168bb5dfe9a00b126000018/train/java)

#### Solution

~~~ Java

public class Kata {

public static String solution(String str) {
    var i = 0;
    var j = str.length() - 1;
    var result = "";
    while(i <= j){
        result = str.charAt(i) + result;
        i++;
    }
    return result;
    }
}
~~~

#### Fav Solution

~~~ Java
public class Kata {

  public static String solution(String str) {
      //didn't choose StringBuilder because it's not thread-safe
        return new StringBuffer(str).reverse().toString();
  }

}
~~~

### Task №2(7kuy)

Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before,
or after the addition.

The binary number returned should be a string.

Examples:(Input1, Input2 --> Output (explanation)))

[Task_link](https://www.codewars.com/kata/551f37452ff852b7bd000139)

#### Solution
~~~ Java
public class Kata{
  
  public static String binaryAddition(int a, int b){
    int result = a + b;
    var binary = "";
    
    while (result != 0)
      {
        binary = Integer.toString(result % 2) + binary;
        result = result / 2;
    }
    if(result == 1)
      {
      binary = "1" + binary;
}
    return binary;
  }
}
~~~

#### Fav Solution
~~~ Java
public class Kata{
  
  public static String binaryAddition(int a, int b){
    StringBuilder res = new StringBuilder();
    int c = 0;
    while((a | b | c) != 0) {
      res.append((a ^ b ^ c) & 1);
      c += (a & 1) + (b & 1);
      c >>= 1;
      a >>= 1;
      b >>= 1;
    }
    return res.reverse().toString();
  }
}
~~~

#### Comment:
I liked that when solving tasks, I remembered how to convert numbers from decimal to binary.