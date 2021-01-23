```java
//string is a non-primitive data type in java
String str1 = "Hello World";
//here JVM performs string pool check as string literal goes in string pool which uses cache
String str2=new String("Hello World");
//here JVM does not perform string pool check 
//new String object goes in heap memory(Heap is a section of memory which contains Objects and may also contain reference variables.)
str1==str2 // will return false
```
![alt text](https://cdn.journaldev.com/wp-content/uploads/2012/11/String-Pool-Java1.png)
### Why Strings are immytable in Java?
Java has a string pool so a string object is likely to have one or many references. If several references point to same String without even knowing it, it would be bad if one of the refernces modified its value.
<br>
**Note -> String Object is immutable but its refernce variable is'nt.**
<br>
# Know your String Library:
<br>


