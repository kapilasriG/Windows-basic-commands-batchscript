# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
```
 mkdir my-folder

```

![alt text](<Screenshot 2026-05-19 110622.png>)

Create the file Rose.txt

## COMMAND AND OUTPUT

```
type nul > Rose.txt

```

![alt text](<Screenshot 2026-05-19 111422.png>)

Remove the directory "my-folder"

## COMMAND AND OUTPUT

```
rmdir my-folder

```
![alt text](<Screenshot 2026-05-19 111239.png>)

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt 

```
echo Hello World > hello.txt
copy hello.txt hello1.txt

```
![alt text](<Screenshot 2026-05-19 111617.png>)

## COMMAND AND OUTPUT

Remove the file hello1.txt

```
del hello1.txt

```
![alt text](<Screenshot 2026-05-19 111910.png>)

## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory

```
dir hello1.txt

```
![alt text](<Screenshot 2026-05-19 112037.png>)

## COMMAND AND OUTPUT

List out all the associated file extensions 

```
assoc

```
![alt text](<Screenshot 2026-05-19 112154.png>)

## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt

```
fc hello.txt Rose.txt

```
![alt text](<Screenshot 2026-05-19 112254.png>)

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```

@echo off
set name=John
echo Hello, %name%
pause

```

## OUTPUT

![alt text](<Screenshot 2026-05-19 112513.png>)


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

```
@echo off

:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==0 (
    echo The number is Even
) else (
    echo The number is Odd
)

:ASK
set /p choice=Do you want to continue (Y/N)? 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Enter Y or N.
goto ASK

:END
echo Thank you
pause

```


## OUTPUT

![alt text](image-1-1.png)

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```
@echo off

for /L %%i in (1,1,5) do (
    echo Number: %%i
)

pause

```

## OUTPUT

![alt text](<Screenshot 2026-05-19 113155.png>)


Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```

@echo off

if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)

pause

```

## OUTPUT

![alt text](<Screenshot 2026-05-19 113406.png>)

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.


```
@echo off

:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit

set /p choice=Enter your choice: 

if %choice%==1 goto HELLO
if %choice%==2 goto CREATE
if %choice%==3 goto EXIT

echo Invalid choice
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully
pause
goto MENU

:EXIT
echo Goodbye
pause
exit

```

## OUTPUT

![alt text](<Screenshot 2026-05-19 113611.png>)

# RESULT:
The commands/batch files are executed successfully.

