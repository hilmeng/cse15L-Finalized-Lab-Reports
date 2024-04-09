# Lab 1

## `cd` command

No arguments:
```
Gabriels-MacBook-Pro-2:lecture1 gabe$ cd
Gabriels-MacBook-Pro-2:~ gabe$ 
```
Absolute path of `/Users/gabe/Desktop/cse15L/`.
This returned nothing because I provided no directory to change into, thus I didn't move anywhere, however it did not give me an error.

Directory as an argument:
```
Gabriels-MacBook-Pro-2:lecture1 gabe$ cd messages/
Gabriels-MacBook-Pro-2:messages gabe$ ls
en-us.txt       fr.txt
es-mx.txt       zh-cn.txt
Gabriels-MacBook-Pro-2:messages gabe$ 
```
Absolute path of `/Users/gabe/Desktop/cse15L/lecture1/messages/`.
Here I provided the messages directory as an argument which allowed me to move into it, and I also displayed it's contents with `ls`. It did not give me an error.

File as an argument:
```
Gabriels-MacBook-Pro-2:messages gabe$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
Gabriels-MacBook-Pro-2:messages gabe$
```
Absolute path of `/Users/gabe/Desktop/cse15L/lecture1/messages/en-us.txt`. Here I got an error messages saying "Not a directory" because I tried to move into a .txt file which I cannot do with cd.

## `ls` command

No arguments:
```
Gabriels-MacBook-Pro-2:cse15L gabe$ ls
lab1.java       lecture1
Gabriels-MacBook-Pro-2:cse15L gabe$
```
Absolute path of `/Users/gabe/Desktop/cse15L/`. Using `ls` without providing any arguments listed out the contents of my current working directory. It did not give me an error.

Directory as an argument:
```
Gabriels-MacBook-Pro-2:cse15L gabe$ ls lecture1/
Hello.class     README
Hello.java      messages
Gabriels-MacBook-Pro-2:cse15L gabe$
```
Absolute path of `/Users/gabe/Desktop/cse15L/`. Here I used `ls` on a directory that was in my current working directory. This did not give me any errors and spilled out the contents of the directory that I passed in as an argument.

File as an argument:
```
Gabriels-MacBook-Pro-2:messages gabe$ ls en-us.txt 
en-us.txt
Gabriels-MacBook-Pro-2:messages gabe$
```
Absolute path of `/Users/gabe/Desktop/cse15L/lecture1/messages/`. Here the `ls` command was used with the file `en-us.txt` passed in as an argument. I got no errors but it simply retured the file name back to me.

## `cat` command

No arguments:
```
Gabriels-MacBook-Pro-2:cse15L gabe$ cat

```
Absolute path of `/Users/gabe/Desktop/cse15L/`. When using `cat` with no arguments nothing happens and the terminal waits indefinitely for user input. It's not an error, but just nothing happens.

Directory as an argument:
```
Gabriels-MacBook-Pro-2:cse15L gabe$ cat lecture1/
cat: lecture1/: Is a directory
```
Absolute path of `/Users/gabe/Desktop/cse15L/`. When I used `cat` on a directory it gave me the error message that `lecture1` was a directory, and `cat` isn't meant to be used on those.

File as an argument:
```
Gabriels-MacBook-Pro-2:messages gabe$ cat en-us.txt 
Hello World!
Gabriels-MacBook-Pro-2:messages gabe$
```
Absolute path of `/Users/gabe/Desktop/cse15L/lecture1/messages`. When I used cat on the file is spilled out it's context. This is not an error and is it's intended usage.


