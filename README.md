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
