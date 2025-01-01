# Shell Scripting Basics

## What is a Shell Script?
A **shell script** is a text file containing a sequence of commands for a Unix/Linux shell (e.g., `sh`, `bash`, or `zsh`). It is used to automate tasks like file management, system monitoring, or software installation. Shell scripts save time and reduce the possibility of human error.

---

## How Do You Write a Simple Shell Script to Print "Hello, World"?
1. Open a text editor and write the following code:
   ```bash
   #!/bin/bash
   echo "Hello, World"
   ```
2. Save the file with a `.sh` extension, e.g., `hello.sh`.

---

## How Do You Make a Shell Script Executable?
1. Use the `chmod` command to change the script's permissions:
   ```bash
   chmod +x hello.sh
   ```
2. Run the script:
   ```bash
   ./hello.sh
   ```

---

## What is the Difference Between `sh`, `bash`, and `zsh`?
- **`sh`**: The original Bourne shell, lightweight and basic. It lacks many modern features.
- **`bash`**: The Bourne Again Shell, an enhanced version of `sh`, widely used and supports advanced scripting features.
- **`zsh`**: A feature-rich shell with enhanced customization, powerful plugins, and extended functionalities compared to `bash`.

---

## How Do You Create a Variable in a Shell Script?
Variables are created by assigning values without spaces:
```bash
name="Ajinkya"
echo "Hello, $name"
```

---

## How Do You Read Input from a User in a Shell Script?
Use the `read` command to get user input:
```bash
#!/bin/bash
read -p "Enter your name: " name
echo "Welcome, $name!"
```

---

## What is the Purpose of the `#!` (Shebang) at the Beginning of a Shell Script?
The **shebang** specifies the interpreter that should execute the script. For example:
```bash
#!/bin/bash
```
This tells the system to use the `bash` shell to execute the script.

---

## How Do You Use Comments in a Shell Script?
Comments start with `#` and are ignored by the shell:
```bash
#!/bin/bash
# This script prints a message
echo "Hello, World"
```

---

## What is the Difference Between Single and Double Quotes in Shell Scripting?
- **Single Quotes (`'`)**: Preserve the literal value of all enclosed characters.
  ```bash
  echo 'This is $literal'
  # Output: This is $literal
  ```
- **Double Quotes (`"`)**: Allow variable and command substitution.
  ```bash
  name="Ajinkya"
  echo "Hello, $name"
  # Output: Hello, Ajinkya
  ```

---

## How Do You Use Arithmetic Operations in a Shell Script?
Use `$((expression))` for arithmetic:
```bash
#!/bin/bash
x=5
y=3
sum=$((x + y))
echo "Sum: $sum"
```

---

## How Do You Use the `if` Statement in a Shell Script?
The `if` statement is used to conditionally execute code:

### Example 1: Simple Condition
```bash
#!/bin/bash
if [ $1 -gt 0 ]; then
  echo "Positive number"
fi
```

### Example 2: Using `else`
```bash
#!/bin/bash
if [ $1 -eq 0 ]; then
  echo "Zero"
else
  echo "Non-zero"
fi
```

### Example 3: Using `elif`
```bash
#!/bin/bash
if [ $1 -gt 0 ]; then
  echo "Positive"
elif [ $1 -lt 0 ]; then
  echo "Negative"
else
  echo "Zero"
fi
```

### Example 4: File Check
```bash
#!/bin/bash
if [ -f "$1" ]; then
  echo "File exists"
else
  echo "File does not exist"
fi
```

### Example 5: Nested `if`
```bash
#!/bin/bash
if [ $1 -gt 0 ]; then
  if [ $1 -lt 10 ]; then
    echo "Single digit"
  fi
fi
```

---

## How Do You Use the `case` Statement in a Shell Script?
The `case` statement is used for multi-way branching:

### Example 1: Simple Case
```bash
#!/bin/bash
case $1 in
  1) echo "One" ;;
  2) echo "Two" ;;
  *) echo "Other" ;;
esac
```

### Example 2: Pattern Matching
```bash
#!/bin/bash
case $1 in
  [a-z]*) echo "Lowercase" ;;
  [A-Z]*) echo "Uppercase" ;;
  *) echo "Other" ;;
esac
```

### Example 3: File Extension Check
```bash
#!/bin/bash
case $1 in
  *.sh) echo "Shell script" ;;
  *.txt) echo "Text file" ;;
  *) echo "Unknown file type" ;;
esac
```

### Example 4: Multiple Matches
```bash
#!/bin/bash
case $1 in
  1|2|3) echo "Low" ;;
  4|5|6) echo "Medium" ;;
  *) echo "High" ;;
esac
```

### Example 5: No Match
```bash
#!/bin/bash
case $1 in
  1) echo "One" ;;
  2) echo "Two" ;;
  *) ;; # Do nothing
esac
```

---

## How Do You Use the `for` Loop in a Shell Script?
The `for` loop is used for iterating over a range or list:

### Example 1: Simple List
```bash
#!/bin/bash
for item in 1 2 3; do
  echo $item
done
```

### Example 2: Range with `{}`
```bash
#!/bin/bash
for i in {1..5}; do
  echo $i
done
```

### Example 3: Files in Directory
```bash
#!/bin/bash
for file in *.sh; do
  echo "Script: $file"
done
```

### Example 4: Command Substitution
```bash
#!/bin/bash
for user in $(cat users.txt); do
  echo "Hello, $user"
done
```

### Example 5: With `seq`
```bash
#!/bin/bash
for i in $(seq 1 5); do
  echo $i
done
```

---

## How Do You Use the `while` Loop in a Shell Script?
The `while` loop executes as long as a condition is true:

### Example 1: Countdown
```bash
#!/bin/bash
count=5
while [ $count -gt 0 ]; do
  echo $count
  count=$((count - 1))
done
```

### Example 2: Read File Line by Line
```bash
#!/bin/bash
while IFS= read -r line; do
  echo $line
done < file.txt
```

### Example 3: User Input
```bash
#!/bin/bash
input=""
while [ "$input" != "exit" ]; do
  read -p "Enter command: " input
  echo "You entered: $input"
done
```

### Example 4: Infinite Loop
```bash
#!/bin/bash
while true; do
  echo "Running"
  sleep 1
done
```

### Example 5: With Logical Conditions
```bash
#!/bin/bash
x=0
while [ $x -lt 5 ] && [ $x -ge 0 ]; do
  echo $x
  x=$((x + 1))
done
```

---

## How Do You Use the `until` Loop in a Shell Script?
The `until` loop executes until a condition becomes true:

### Example 1: Increment
```bash
#!/bin/bash
x=0
until [ $x -ge 5 ]; do
  echo $x
  x=$((x + 1))
done
```

### Example 2: Read File Until End
```bash
#!/bin/bash
until ! read -r line; do
  echo $line
done < file.txt
```

### Example 3: User Input
```bash
#!/bin/bash
input=""
until [ "$input" == "exit" ]; do
  read -p "Enter command: " input
  echo "You entered: $input"
done
```

### Example 4: Countdown
```bash
#!/bin/bash
count=5
until [ $count -eq 0 ]; do

