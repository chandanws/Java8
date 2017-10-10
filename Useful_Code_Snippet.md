
[How to write on GitHub](https://help.github.com/categories/writing-on-github/)

- ### Converting a string to a stream using char()
```java
public static void main(String[] args) {
        "hey duke".chars().forEach(c -> System.out.println((char)c));
}
```
#### the parallel version doesn't preserv the order
```java
public static void main(String[] args) {
        "hey duke".chars().parallel().forEach(c -> System.out.println((char)c));
}
```

- ### 
```java
```
