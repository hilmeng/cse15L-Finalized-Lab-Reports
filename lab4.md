# Lab Report 4: Vim

## Step 4: Logging into ieng6

Image: step 4

I typed `ssh<space>ghlimen@ieng6.ucsd.edu<enter>` to log into the ieng6 machine from my computers terminal.

## Step 5: Cloning the github repo

Image: step 5

I typed `git<space>clone<space>git@github.com:hilmeng/lab7.git<enter>` to clone the github repo into my current working directory. I also made sure to select the `ssh` url from github.

## Step 6: Showing test failures

Image: step 6

I first typed `cd<space>lab7<enter>` to get into the `lab7<enter>` directory, then typed `ls<enter>` to get the name of the bash file. Finally, I typed `bash<space>test.sh<enter>` to run the test, which showed that there were two tests that ran, with one failure.

## Step 7: Fixing the tests

Image: step 7

I first need to start editing the `.java` file, so I typed `vim<space>ListExamples.java<enter>` to start editing the file. Once I was inside `vim`, I then had to move my cursor to where the bug in the file was. I then proceeded to `<click>` on the space before the 1 in `index1` and typed `i<backspace>2<escape>:wq<enter>` to change the 1 in `index1` to 2, so the final change was `index1 --> index2`. I then typed `<escape>:wq<enter>` to leave insert mode and save my changes before exiting `vim`. 

## Step 8: Veifying the changes worked

Image: step 8

After exiting vim as shown in the previous step, I then typed `bash<space>test.sh<enter>` to verify that my changes worked. I was able to see that they indeed did work from the output message of the test.

## Step 9: Commiting and pushing changes

Image: step 9

After verifying that my changes were correct, I then typed `git<space>add<space>.<enter>` to add my file changes. Then I typed `git<space>status<enter>` to check and verify the status and that everything was working properly, where I could then commmit my changes and leave a message by typing `git<space>commit<space>-m<space>"Debugged<space>ListExamples.java"<enter>`. After that I tryped `git<space>push<enter>`, where I could then get my verification message that my changes were successfully pushed out to my github repo.
