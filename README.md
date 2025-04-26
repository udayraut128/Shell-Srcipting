# Shell-Srcipting
This repository is a complete collection of Shell scripts designed to automate tasks, manage systems, and enhance productivity on Linux and Unix-based systems. It covers scripts ranging from basic to advanced levels, providing a strong foundation for anyone looking to master shell scripting.



Of course! 🔥  
Here’s a **detailed explanation of all topics from Module 1**, **without skipping anything**, and also **with examples**.  
(You can directly use this for making notes or tutorials!)

---

# 🧩 Module 1: Beginner Level (Detailed Shell Scripting Notes)

---

## 1. 🔥 Introduction to Shell and Shell Scripting

- **What is a Shell?**  
  Shell is a command-line interpreter that lets users interact with the operating system.  
  Example Shells: `bash`, `sh`, `zsh`, `ksh`, etc.

- **What is Shell Scripting?**  
  Shell scripting is writing a series of commands in a file to automate tasks. The file is called a **Shell Script**.

- **Why use Shell Scripting?**  
  - Automate repetitive tasks.
  - System administration tasks (backups, updates).
  - Simplify DevOps processes.
  - Easy way to combine Linux commands.

---

## 2. 🔥 Environment Setup

- **Check Shell Version:**  
  ```bash
  echo $SHELL
  bash --version
  ```

- **Create your first shell script:**  
  1. Open terminal.
  2. Create a file:  
     ```bash
     nano hello.sh
     ```
  3. Add script content:
     ```bash
     #!/bin/bash
     echo "Hello, Shell Scripting!"
     ```
  4. Make the script executable:
     ```bash
     chmod +x hello.sh
     ```
  5. Run the script:
     ```bash
     ./hello.sh
     ```
---

## 3. 🔥 Basic Shell Script Syntax

- **Shebang Line:**  
  At the top of every script:
  ```bash
  #!/bin/bash
  ```

- **Adding Comments:**  
  ```bash
  # This is a comment
  echo "Hello"  # Comment beside command
  ```

- **Best Practice:**  
  - Use meaningful comments.
  - Keep scripts readable and neat.

---

## 4. 🔥 Basic Commands in Shell

- **Display Text:**  
  ```bash
  echo "Welcome!"
  printf "Welcome!\n"
  ```

- **Take User Input:**  
  ```bash
  read name
  echo "Hello, $name"
  ```

- **Use Common Linux Commands:**  
  ```bash
  pwd     # Print current directory
  ls -l   # List files in long format
  cd /home/user  # Change directory
  ```

---

## 5. 🔥 Variables and Data Types

- **Define and Use Variables:**  
  ```bash
  name="John"
  echo "Hello $name"
  ```

- **Special Variables:**  
  - `$0` → Script name  
  - `$1`, `$2`, etc. → Arguments  
  - `$@` → All arguments  
  - `$#` → Number of arguments

  Example:
  ```bash
  echo "Script Name: $0"
  echo "First Argument: $1"
  echo "Total Arguments: $#"
  ```

- **Environment Variables Example:**  
  ```bash
  echo $HOME
  echo $USER
  ```

---

## 6. 🔥 Operators in Shell

- **Arithmetic Operators:**
  ```bash
  a=5
  b=3
  echo $((a+b))  # 8
  ```

- **Relational Operators Example:**
  ```bash
  if [ $a -gt $b ]; then
    echo "$a is greater than $b"
  fi
  ```

- **Logical Operators:**
  ```bash
  if [ $a -gt 0 ] && [ $b -gt 0 ]; then
    echo "Both are positive"
  fi
  ```

---

## 7. 🔥 Conditional Statements

- **if Statement:**
  ```bash
  if [ $a -gt 10 ]
  then
    echo "Greater than 10"
  fi
  ```

- **if-else Statement:**
  ```bash
  if [ $a -gt 10 ]
  then
    echo "Greater than 10"
  else
    echo "Less than or equal to 10"
  fi
  ```

- **if-elif-else Statement:**
  ```bash
  if [ $a -gt 10 ]
  then
    echo "Greater than 10"
  elif [ $a -eq 10 ]
  then
    echo "Equal to 10"
  else
    echo "Less than 10"
  fi
  ```

- **Nested if Example:**
  ```bash
  if [ $a -gt 0 ]
  then
    if [ $b -gt 0 ]
    then
      echo "Both are positive"
    fi
  fi
  ```

---

## 8. 🔥 Loops

- **for Loop:**
  ```bash
  for i in 1 2 3 4 5
  do
    echo "Number: $i"
  done
  ```

- **while Loop:**
  ```bash
  count=1
  while [ $count -le 5 ]
  do
    echo "Count: $count"
    ((count++))
  done
  ```

- **until Loop:**
  ```bash
  count=1
  until [ $count -gt 5 ]
  do
    echo "Until Count: $count"
    ((count++))
  done
  ```

- **break Example:**
  ```bash
  for i in 1 2 3 4 5
  do
    if [ $i -eq 3 ]; then
      break
    fi
    echo $i
  done
  ```

- **continue Example:**
  ```bash
  for i in 1 2 3 4 5
  do
    if [ $i -eq 3 ]; then
      continue
    fi
    echo $i
  done
  ```

---

## 9. 🔥 Working with Input and Output

- **Redirect Output to File:**
  ```bash
  echo "Saving this text" > file.txt
  echo "Adding more text" >> file.txt
  ```

- **Read From File:**
  ```bash
  while read line
  do
    echo $line
  done < file.txt
  ```

- **Error Handling Example:**
  ```bash
  mkdir new_folder || echo "Failed to create folder"
  ```

- **Exit Status Check:**
  ```bash
  cp file1.txt file2.txt
  echo $?
  ```

---

## 10. 🔥 Best Practices

- **Consistent Naming:**  
  Use meaningful names: `backup_script.sh`, `install_app.sh`

- **Always add permission:**  
  ```bash
  chmod +x script.sh
  ```

- **Use `/bin/bash` Shebang:**  
  At the start:
  ```bash
  #!/bin/bash
  ```

- **Add comments in the code:**  
  Explain tricky parts for future maintenance.

- **Test Scripts before running in production:**  
  Avoid mistakes that can harm the system.

---

# ✅ After this Module 1:

- You can **write**, **edit**, **run**, and **debug basic scripts**.  
- You understand **conditions, loops, variables**, and **user inputs**.  
- You can **automate small tasks** in your system!

---
 



Of course!  
Here’s a **detailed but clear explanation** of your **Intermediate Shell Scripting Topics**:

---

# 🟡 Intermediate Shell Scripting (Detailed)

---

## 1. Functions in Shell Scripts

### ➔ Defining and Calling Functions
- **Definition**: A function groups reusable code blocks.
- **Syntax**:
  ```bash
  my_function() {
    echo "This is a function"
  }

  my_function  # Calling the function
  ```

### ➔ Passing Arguments to Functions
- Use `$1`, `$2`, etc. inside the function.
- **Example**:
  ```bash
  greet() {
    echo "Hello, $1!"
  }

  greet "Uday"   # Output: Hello, Uday!
  ```

---

## 2. Command Line Arguments (`$1`, `$2`, `$@`, `$#`)

| Symbol | Meaning |
|:------|:--------|
| `$1`, `$2` | First and second arguments |
| `$@` | All arguments (individually) |
| `$*` | All arguments (as a single string) |
| `$#` | Total number of arguments |

**Example**:
```bash
echo "First argument: $1"
echo "Total arguments: $#"
```

---

## 3. Shift Operator in Arguments

- `shift` command shifts arguments to the left.
- Useful to **loop through all arguments**.

**Example**:
```bash
while [ $# -gt 0 ]; do
  echo "Argument: $1"
  shift
done
```
*(Every `shift` drops `$1` and moves `$2` to `$1`, and so on.)*

---

## 4. Arrays in Bash

### ➔ Creating, Accessing, and Looping Arrays
- **Create**:
  ```bash
  fruits=("apple" "banana" "cherry")
  ```
- **Access**:
  ```bash
  echo "${fruits[0]}"  # apple
  ```
- **Loop**:
  ```bash
  for fruit in "${fruits[@]}"; do
    echo "$fruit"
  done
  ```

---

## 5. String Manipulation

### ➔ Operations:
| Operation | Syntax | Example |
|:----------|:-------|:--------|
| Length | `${#str}` | `echo ${#name}` |
| Substring | `${str:start:length}` | `echo ${name:0:4}` |
| Replace text | `${str/old/new}` | `echo ${name/old/new}` |
| Remove part | `${str#pattern}` or `${str##pattern}` | Remove prefix |

**Example**:
```bash
str="HelloWorld"
echo "${#str}"           # 10
echo "${str:0:5}"         # Hello
echo "${str/World/Everyone}"  # HelloEveryone
```

---

## 6. Working with Files

### ➔ Reading Files Line by Line
```bash
while read line; do
  echo "$line"
done < filename.txt
```

### ➔ Append and Write to Files
- Overwrite (`>`) vs. Append (`>>`):
  ```bash
  echo "New line" > file.txt      # overwrite
  echo "Another line" >> file.txt # append
  ```

---

## 7. Redirection Operators

| Operator | Purpose |
|:---------|:--------|
| `>` | Redirect output (overwrite file) |
| `>>` | Redirect output (append to file) |
| `<` | Read input from file |
| `2>` | Redirect error output |
| `&>` | Redirect both output and error |
| `/dev/null` | Discard output |

**Example**:
```bash
ls > list.txt
ls wrongfile 2> errors.txt
ls /home &> all_output.txt
ls /nosuchdir > /dev/null
```

---

## 8. Pipes and Filters

| Command | Usage |
|:--------|:------|
| `|` | Pipe output to next command |
| `grep` | Search text |
| `sort` | Sort lines |
| `uniq` | Remove duplicate lines |
| `wc` | Count lines, words, characters |
| `cut` | Cut specific columns |
| `awk` | Powerful text processing |
| `sed` | Stream editor (substitution) |

**Example**:
```bash
cat file.txt | grep "hello" | sort | uniq
```

---

## 9. Scheduling Scripts: Using Cron Jobs

- **Edit crontab**:
  ```bash
  crontab -e
  ```
- **Syntax**:
  ```
  * * * * * /path/to/script.sh
  ```
  *(minute hour day month day-of-week command)*

- **Example (Run every day at 5 AM)**:
  ```bash
  0 5 * * * /home/user/backup.sh
  ```

---

## 10. Trap Command

- Handle signals like **CTRL+C (SIGINT)** or **Script Exit (SIGTERM)**.
- **Example**:
  ```bash
  trap "echo 'Interrupt received. Exiting...'; exit" SIGINT
  while true; do
    echo "Running..."
    sleep 2
  done
  ```

---

## 11. Debugging Shell Scripts

### ➔ Using `bash -x`
- Run script in debug mode:
  ```bash
  bash -x script.sh
  ```

### ➔ Using `set -x` and `set +x` inside script
- Turn on/off debugging within a script.
- **Example**:
  ```bash
  echo "Before Debugging"

  set -x
  echo "Debugging this line"
  set +x

  echo "After Debugging"
  ```

---
 


 Here’s a detailed breakdown of **Advanced Shell Scripting Topics** for you:

---

# 🟠 **Advanced Shell Scripting (Detailed)**

---

## 1. Shell Script Arguments Validation
- **Purpose**: Ensures correct input by the user.
- **Example**:
  ```bash
  if [ $# -ne 2 ]; then
    echo "Usage: $0 <arg1> <arg2>"
    exit 1
  fi
  ```
- Validates if there are exactly 2 arguments, otherwise displays an error and exits.

---

## 2. Interactive Scripts (with menus)
- **Purpose**: Create interactive menus for the user.
- **Example**:
  ```bash
  PS3="Choose an option: "
  select option in "Option 1" "Option 2" "Exit"; do
    case $option in
      "Option 1") echo "You chose Option 1";;
      "Option 2") echo "You chose Option 2";;
      "Exit") echo "Exiting..."; break;;
      *) echo "Invalid option";;
    esac
  done
  ```
- The `select` command creates a menu, and `case` handles user input.

---

## 3. Logging in Scripts (timestamps, logs)
- **Purpose**: Log script outputs to a file with timestamps.
- **Example**:
  ```bash
  echo "$(date '+%Y-%m-%d %H:%M:%S') - Started script" >> script.log
  ```
- Logs the timestamp of when the script started to a file.

---

## 4. Color Output in Terminal
- **Purpose**: Add color to terminal output for better visibility.
- **Example**:
  ```bash
  echo -e "\e[31mThis is red text\e[0m"
  ```
- Color codes can be applied for various effects (e.g., red `31`, green `32`).

---

## 5. Regular Expressions in Shell
- **Purpose**: Perform pattern matching and searching within strings.
- **Example**:
  ```bash
  echo "123abc" | grep -E '^[0-9]+[a-z]+$'
  ```
- Uses `grep` with regular expressions to match strings that start with digits and are followed by letters.

---

## 6. Process Management

### ➔ `ps`, `kill`, `killall`, `jobs`, `bg`, `fg`
- **ps**: View active processes.
  ```bash
  ps aux
  ```
- **kill**: Kill a specific process by PID.
  ```bash
  kill 12345
  ```
- **killall**: Kill processes by name.
  ```bash
  killall firefox
  ```
- **jobs**: List background jobs.
  ```bash
  jobs
  ```
- **bg**: Move a job to the background.
  ```bash
  bg 1
  ```
- **fg**: Bring a background job to the foreground.
  ```bash
  fg 1
  ```

---

## 7. Background and Foreground Processes
- **Background (`&`)**:
  ```bash
  my_script.sh &
  ```
- **Foreground**: Run normally.
  ```bash
  my_script.sh
  ```

---

## 8. Networking Commands in Shell

- **curl**: Fetch data from a URL.
  ```bash
  curl http://example.com
  ```
- **wget**: Download files.
  ```bash
  wget http://example.com/file.tar
  ```
- **ftp**: File transfer protocol.
  ```bash
  ftp ftp.example.com
  ```
- **scp**: Secure copy files over SSH.
  ```bash
  scp file.txt user@remote:/path/
  ```
- **ssh scripting**: Automate SSH commands.
  ```bash
  ssh user@host 'ls -l'
  ```

---

## 9. Creating Daemon Scripts
- **Purpose**: Run scripts in the background as services (like system services).
- **Example**:
  ```bash
  nohup my_script.sh &
  ```

---

## 10. Parallel Execution in Shell
- **Purpose**: Execute multiple commands simultaneously.
- **Example**:
  ```bash
  command1 & command2 &
  wait
  ```
- Executes `command1` and `command2` in parallel.

---

## 11. Multithreading Basics (using `&` and `wait`)
- **Purpose**: Simulate multithreading in shell scripting by using background processes and `wait`.
- **Example**:
  ```bash
  process1 &
  process2 &
  wait
  ```

---

## 12. Secure Shell Scripting

### ➔ Avoid Hardcoding Passwords
- **Best Practice**: Don’t store passwords directly in scripts. Use environment variables or `.env` files.
  ```bash
  export PASSWORD="my_secure_password"
  ```

### ➔ Using `.env` Files
- **Example**:
  - `.env` file:
    ```
    DB_USER=root
    DB_PASS=secret
    ```
  - Load in script:
    ```bash
    source .env
    ```

---

## 13. Dynamic Menus with `select`
- **Purpose**: Build dynamic menus.
- **Example**:
  ```bash
  select opt in "Start" "Stop" "Restart"; do
    case $opt in
      "Start") echo "Starting...";;
      "Stop") echo "Stopping...";;
      "Restart") echo "Restarting...";;
      *) echo "Invalid option";;
    esac
  done
  ```

---

## 14. Automating Backups with Shell
- **Purpose**: Automate file or database backups.
- **Example**:
  ```bash
  tar -czf /backups/backup_$(date +%F).tar.gz /home/user
  ```

---

## 15. File Compression Scripts (`tar`, `gzip`, `zip`)
- **tar**: Archive files.
  ```bash
  tar -cvf archive.tar folder/
  ```
- **gzip**: Compress files.
  ```bash
  gzip file.txt
  ```
- **zip**: Create zip files.
  ```bash
  zip archive.zip file1.txt file2.txt
  ```

---

## 16. Parsing JSON in Shell (with `jq`)
- **Purpose**: Extract and manipulate JSON data.
- **Example**:
  ```bash
  cat file.json | jq '.key'
  ```

---

## 17. Database Scripting (MySQL Queries)
- **Purpose**: Automate database queries from shell.
- **Example**:
  ```bash
  mysql -u root -p -e "SELECT * FROM users"
  ```

---

## 18. Monitoring System Resources
- **Commands**: `top`, `htop`, `df`, `du`, `free`, `uptime`
- **Example**:
  ```bash
  top     # Monitor processes
  df -h   # Disk usage
  free -h # Memory usage
  ```

---

## 19. Writing Installers with Shell Scripts
- **Purpose**: Create installation scripts.
- **Example**:
  ```bash
  #!/bin/bash
  echo "Installing package..."
  sudo apt-get install package-name
  ```

---

## 20. Building API Requests via Shell
- **Purpose**: Interact with REST APIs using `curl`.
- **Example**:
  ```bash
  curl -X GET "https://api.example.com/data" -H "Authorization: Bearer token"
  ```

---

 