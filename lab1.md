# Lab 1

## `cd` command

No Arguments:
```
Gabriels-MacBook-Pro-2:lecture1 gabe$ cd
Gabriels-MacBook-Pro-2:~ gabe$ 
```
Absolute path of **/Users/gabe/Desktop/cse15L/**.
This returned nothing because I provided no directory to change into, thus I didn't move anywhere

Directory as an argument:
```
Gabriels-MacBook-Pro-2:lecture1 gabe$ cd messages/
Gabriels-MacBook-Pro-2:messages gabe$ ls
en-us.txt       fr.txt
es-mx.txt       zh-cn.txt
Gabriels-MacBook-Pro-2:messages gabe$ 
```
Absolute path of **/Users/gabe/Desktop/cse15L/messages/**.
Here I provided the messages directory as an argument which allowed me to move into it, and I also displayed it's contents with `ls`.

File as an Argument:
```
Gabriels-MacBook-Pro-2:messages gabe$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
Gabriels-MacBook-Pro-2:messages gabe$
```
Absolute path of **/Users/gabe/Desktop/cse15L/messages/en-us.txt**. Here I got an error messages saying "Not a directory" because I tried to move into a .txt file which I cannot do with cd.

## `ls` command
