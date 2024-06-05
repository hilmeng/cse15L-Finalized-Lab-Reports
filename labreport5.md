# Lab Report 5


## Part 1

### Original Post
Student:
Hello,
I'm having a problem with my Java program that uses a bash script. When I try to run my Java file, it should call the Bash script, but it's giving me an error:
```
Exception in thread "main" java.io.IOException: Cannot run program "./my_script.sh": error=2, No such file or directory
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1128)
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1071)
    at MyClass.runScript(MyClass.java:25)
    at MyClass.main(MyClass.java:12)
Caused by: java.io.IOException: error=2, No such file or directory
    at java.base/java.lang.ProcessImpl.forkAndExec(Native Method)
    at java.base/java.lang.ProcessImpl.<init>(ProcessImpl.java:313)
    at java.base/java.lang.ProcessImpl.start(ProcessImpl.java:239)
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1110)
    ... 3 more
```
Here is also the content of my Java file:
```
import java.io.IOException;

public class MyClass {
    public static void main(String[] args) {
        MyClass myClass = new MyClass();
        myClass.runScript();
    }

    public void runScript() {
        ProcessBuilder processBuilder = new ProcessBuilder("./my_script.sh");
        try {
            processBuilder.start();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

And here is my Bash script:
```
#!/bin/bash
echo "Hello from the script!"
```

I'm not sure what to do but I think it has to do with when I try and call the file from my Bash script.

### TA Response

TA:
Hello! It looks like your java program can't find the `my_script.sh` file. From looking at your code I can see that path you are using is `(`"./my_script.sh"`)` which assumes the script is in the same directory as where the Java program is being executed, which doesn't seem to be the case here. Try modifying your `runScript` method to specify the correcct path. It could be like something like `ProcessBuilder processBuilder = new ProcessBuilder("scripts/my_script.sh");`. Try the modification and let me know if it helps.

### Student Response After Feedback

Student:
I've changed the path in `ProcessBuilder` like you said, and this is now my script:
```
public void runScript() {
    ProcessBuilder processBuilder = new ProcessBuilder("scripts/my_script.sh");
    try {
        processBuilder.start();
    } catch (IOException e) {
        e.printStackTrace();
    }
}
```
However now I am receiving this error:
```
Exception in thread "main" java.io.IOException: Cannot run program "scripts/my_script.sh": error=13, Permission denied
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1128)
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1071)
    at MyClass.runScript(MyClass.java:25)
    at MyClass.main(MyClass.java:12)
Caused by: java.io.IOException: error=13, Permission denied
    at java.base/java.lang.ProcessImpl.forkAndExec(Native Method)
    at java.base/java.lang.ProcessImpl.<init>(ProcessImpl.java:313)
    at java.base/java.lang.ProcessImpl.start(ProcessImpl.java:239)
    at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1110)
    ... 3 more
```

### TA Response To Student Changes

TA:
We are on the right track, it just looks like your script doesnt have execute permissions. Run `chmod +x scripts/my_script.sh` and let me know if that fixes it.

### Last Student Response

Student:
It worked! Thanks so much.

### Recap

File/Directory structure:
```
/my_project
  ├── src
  │   └── MyClass.java
  └── scripts
      └── my_script.sh
```

Contents of java file before bug fixes:
```
import java.io.IOException;

public class MyClass {
    public static void main(String[] args) {
        MyClass myClass = new MyClass();
        myClass.runScript();
    }

    public void runScript() {
        ProcessBuilder processBuilder = new ProcessBuilder("./my_script.sh");
        try {
            processBuilder.start();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
Contents of bash file before fixes:
```
#!/bin/bash
echo "Hello from the script!"
```
Commands to trigger the bug:
```
javac src/MyClass.java
java -cp src MyClass
```
Description of what edit was made to fix the bug:
- Updated the `ProcessBuilder` path in `MyClass.java` to `scripts/my_script.sh`.
- Added execute permissions to the script with `chmod +x scripts/my_script.sh`.

## Part 2

Something cool that I learned about in the latter half of the labs was how to use `jdb`. I found it to be a really helpful program and enjoyed using it for various tasks in this class as well as sometimes using it to help me with my PAs in CSE12. It made debugging things a lot easier and helped me understand how other java programs ran better because I was able to trace the program easily to understand how they worked.

  
