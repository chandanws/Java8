
[How to write on GitHub](https://help.github.com/categories/writing-on-github/)

- ### Converting a string to a stream using char()
```java
public static void main(String[] args) {
        "hi github".chars().forEach(c -> System.out.println((char)c));
}
```
#### the parallel version doesn't preserv the order
```java
public static void main(String[] args) {
        "hi github".chars().parallel().forEach(c -> System.out.println((char)c));
}
```
- ### Reading a file into String
```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

    public static void main(String[] args) throws IOException {
        String content = new String(Files.readAllBytes(Paths.get("text.txt")));
    }
```
- ### A stream of random numbers
```java
import java.util.stream.Stream;
    
    public static void main(String[] args) throws IOException {
        randomStream(100).limit(50).forEach(System.out::println);
    }
    
    public static Stream<Long> randomStream(int range) {
        return Stream.generate(Math::random).map(n -> n*range).map(Math::round);
    }
```
- ### Collectors.groupingBy
```java
public class Student {

    private int roll;
    private String department;

    public Developer(int roll, String department) {
        this.roll = roll;
        this.department = department;
    }

    public int getRoll() {
        return roll;
    }

    public String getDepartment() {
        return department;
    }
    
   }
   
   @Test
   public void groupByDepartment() {
        List<Student> team = Arrays.asList(
                        new Student(1, "Computer Science"),
                        new Student(2, "Electrical"),
                        new Student(5, "Electrical"),
                        new Student(10, "Instrumentation"));
        Map<String, Student> groupOfStudentByDepartment = team.stream().collect(Collectors.groupingBy(Student::getDepartment));
        System.out.println(groupOfStudentByDepartment);
   }
   @Test
   public void groupDepartmentByAvgerageRoll() {
        List<Student> team = Arrays.asList(
                        new Student(1, "Computer Science"),
                        new Student(2, "Electrical"),
                        new Student(5, "Electrical"),
                        new Student(10, "Instrumentation"));
        Map<String, Double> groupDepartmentByAvgerageRoll = team.stream().collect(Collectors.groupingBy(Student::getDepartment),
                                                                                Collectors.averagingInt(Student::getRoll));
        System.out.println(groupOfStudentByDepartment);
   }
```





#### Inspired by (http://archive.adam-bien.com/) blog
