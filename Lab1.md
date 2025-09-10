# 🐧 Linux Basic Commands – Quick Reference  

Welcome to your **Linux command cheat sheet**!  
This guide covers the most common commands you’ll use while working in the terminal, with examples, explanations, and tips.  


---

## ✅ 1. Navigation Commands  

### 📍 `pwd` – Print Working Directory  
Shows the **current location** in the filesystem.  

```bash
>> pwd
```
``` 
/c/Users/Rishabh/OneDrive/Desktop/Linux_lab
```

# 🐧 Linux Basic Commands  



## ✅ 1. Navigation Commands  

### 📍 `pwd` – Print Working Directory  
Shows the current location in the filesystem.  

```bash
pwd
```

**Output example:**

```
/Users/Rishabh/projects
```



### 📂 `ls` – List Directory Contents

Lists files and folders in the current directory.

```bash
ls
```

**Output example:**

```
file1.txt   notes.md   Pictures/
```

#### 🔧 Common Flags

* **`ls -l`** → Detailed list (permissions, size, date)
* **`ls -a`** → Shows hidden files (those starting with `.`)
* **`ls -la`** → Combined

```bash
ls -la
```

**Sample Output:**

```
drwxr-xr-x   5 rishabh staff   160 Aug 26 11:00 .
drwxr-xr-x  12 rishabh staff   384 Aug 25 15:20 ..
-rw-r--r--   1 rishabh staff   214 Aug 26 09:10 file1.txt
-rw-r--r--   1 rishabh staff   512 Aug 25 18:22 notes.md
drwxr-xr-x   3 rishabh staff    96 Aug 24 14:00 Pictures
```

---

### 🚪 `cd` – Change Directory

Moves into a directory.

```bash
cd folder_name
```

**Examples:**

```bash
cd Documents        # Go to Documents
cd ..               # Go up one level
cd /                # Go to root
cd ~                # Go to home directory
```

---

## ✅ 2. File and Directory Management

### 📁 `mkdir` – Make Directory

Creates a new folder.

```bash
mkdir new_folder
```

---

### 📄 `touch` – Create File

Creates an empty file.

```bash
touch file.txt
```

---

### 📋 `cp` – Copy Files or Directories

Copies files or folders.

```bash
cp source.txt destination.txt
```

**Copy folder:**

```bash
cp -r folder1 folder2
```

---

### ✏️ `mv` – Move or Rename Files

```bash
mv oldname.txt newname.txt
mv file.txt ~/Documents/     # Move file
```

---

### 🗑️ `rm` – Remove Files

Deletes files or folders.

```bash
rm file.txt          # Delete file
rm -r folder_name    # Delete folder (recursively)
```

⚠️ **Be careful!** There is no undo.

---

## ✅ 3. File Viewing & Editing

### 📜 `cat` – View File Contents

Displays file content in the terminal.

```bash
cat file.txt
```

---

### ✍️ `nano` – Edit Files in Terminal

A basic terminal-based text editor.

```bash
nano file.txt
```

* `CTRL + O` → Save
* `CTRL + X` → Exit

---

### 🧹 `clear` – Clears the Terminal

```bash
clear
```

Shortcut: `CTRL + L`

---

## ✅ 4. System Commands

### 💬 `echo` – Print Text

```bash
echo "Hello, World!"
```

---

### 👤 `whoami` – Show Current User

```bash
whoami
```

---

### 📖 `man` – Manual for Any Command

```bash
man ls
```

Use `q` to quit the manual.

---

## ✅ 5. Searching and Finding

### 🔍 `find` – Locate Files

```bash
find . -name "*.txt"
```

Finds all `.txt` files in current folder and subfolders.

---

### 🔎 `grep` – Search Inside Files

```bash
grep "hello" file.txt
```

Searches for the word `hello` inside `file.txt`.

---

## ✅ 6. Helpful Shortcuts

| ⌨️ Shortcut | 🚀 Action                   |
| ----------- | --------------------------- |
| `Tab`       | Auto-complete files/folders |
| `↑ / ↓`     | Browse command history      |
| `CTRL + C`  | Stop a running command      |
| `CTRL + L`  | Clear screen                |

---

## ✅ 7. Bonus: Chaining Commands

Run multiple commands together:

```bash
mkdir test && cd test && touch hello.txt
```

* `&&` → Run next command **only if previous succeeds**
* `;` → Run next command **regardless of success**

---

```
```

# Sudo and Admin managment commands


## ✅ 1. **`sudo` – Run Commands as Administrator**

`sudo` (SuperUser DO) allows you to run commands with root privileges.

```bash
sudo command
```

Example:

```bash
sudo apt update      # Run package update as admin
sudo reboot          # Reboot system
```

You'll usually be prompted to enter your password.

---

## ✅ 2. **User Management (Linux/macOS only)**

### 👤 `adduser` – Create a New User

```bash
sudo adduser newusername
```

You’ll be prompted to set a password and user info.

### 🔑 `passwd` – Change User Password

```bash
sudo passwd newusername
```

---

### 👥 `usermod` – Modify User Account

Add a user to a group:

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG sudo alice     # Give 'alice' sudo access
```

---

### ❌ `deluser` – Delete a User

```bash
sudo deluser username
```

To remove the user's home directory:

```bash
sudo deluser --remove-home username
```

---

## ✅ 3. **File Permissions with `chmod` and `chown`**

### 🔐 `chmod` – Change File Permissions

Basic syntax:

```bash
chmod [permissions] file
```

#### Common Usage:

```bash
chmod 755 script.sh     # Owner: read/write/execute; others: read/execute
chmod +x file.sh        # Add execute permission
chmod -x file.sh        # Remove execute permission
```

### 🔢 What Do Numbers Mean?

| Number | Permission             |
| ------ | ---------------------- |
| 7      | read + write + execute |
| 6      | read + write           |
| 5      | read + execute         |
| 4      | read only              |
| 0      | no permission          |

Example:

```bash
chmod 644 file.txt
# Owner: read/write, Group: read, Others: read
```

---

### 👑 `chown` – Change File Owner

```bash
sudo chown user:group file
```

Example:

```bash
sudo chown alice:alice myfile.txt
```

---

## ✅ 4. **Disk Usage & System Info**

### 💽 `df` – Disk Space Usage

```bash
df -h
```

Shows mounted partitions with human-readable sizes.

---

### 📁 `du` – Directory Size

```bash
du -sh folder_name
```

---

### 🖥️ `top` – Live System Processes

```bash
top
```

Press `q` to quit.

Alternative: `htop` (better UI, needs to be installed)

---

## ✅ 5. **Networking Commands**

### 🌐 `ping` – Check Network Connectivity

```bash
ping google.com
```

Press `CTRL + C` to stop.

---

### 📶 `ifconfig` or `ip a` – Show IP Address & Network Info

```bash
ip a
```

```bash
ifconfig   # May require sudo or installation
```

---

### 🔍 `netstat` – Show Active Network Connections

```bash
netstat -tuln
```

Or use:

```bash
ss -tuln   # Faster alternative
```

---

## ✅ 6. **Package Management**

### For **Ubuntu/Debian (APT)**:

```bash
sudo apt update            # Refresh package list
sudo apt upgrade           # Upgrade installed packages
sudo apt install git       # Install a package
sudo apt remove git        # Uninstall a package
```

---

### For **macOS (Homebrew)**:

```bash
brew install git
```

---

## ✅ 7. **Process Management**

### 🔎 `ps` – Show Running Processes

```bash
ps aux
```

### 🔫 `kill` – Kill a Process

```bash
kill <PID>
```

Example:

```bash
kill 12345
```

Force kill:

```bash
kill -9 12345
```

---

## ✅ 8. **Shutdown and Reboot**

```bash
sudo shutdown now        # Immediate shutdown
sudo shutdown -r now     # Immediate reboot
```

# 🖥️ Our First Shell Script  

---

## ✅ 1. Creating Your First Script  

### ✍️ Step 1: Open a terminal and create a file  
```bash
nano hello.sh
````

---

### ✍️ Step 2: Add the following content

```bash
#!/bin/bash
# This is a simple shell script

echo "Hello, World!"
```

* **`#!/bin/bash`** → Called a **shebang**, tells the system which shell to use.
* **`echo`** → Prints text to the screen.
* **`#`** → Marks a comment.

---

### 💾 Step 3: Save and exit

In **nano** editor:

* `CTRL + O` → Save
* `CTRL + X` → Exit

---

### 🔑 Step 4: Make it executable

```bash
chmod +x hello.sh
```

---

### ▶️ Step 5: Run it

```bash
./hello.sh
```

**✅ Output:**

```
Hello, World!
```

---

## ✅ 2. Variables in Shell

You can store and use variables in scripts.

```bash
#!/bin/bash

name="Rishabh"
age=21

echo "My name is $name"
echo "I am $age years old"
```

⚠️ **Note:** No spaces around `=` when assigning values.

---

## ✅ 3. Taking User Input

```bash
#!/bin/bash

echo "Enter your name:"
read username

echo "Hello, $username! Welcome to shell scripting."
```

* **`read`** → Takes input from the user.
* **`$username`** → Retrieves the value stored.

---

## ✅ 4. Conditional Statements (if-else)

```bash
#!/bin/bash

echo "Enter a number:"
read num

if [ $num -gt 10 ]
then
    echo "The number is greater than 10"
else
    echo "The number is 10 or smaller"
fi
```

* **`-gt`** → Greater than
* **`-lt`** → Less than
* **`-eq`** → Equal

---

```
```


# 🔐 File Permissions with `chmod` and `chown`  
 

---

## ✅ 1. Understanding File Permissions in Linux  

Each file or directory in Linux has three permission groups:  

- **Owner (u)** → The user who created the file  
- **Group (g)** → A group of users who may share access  
- **Others (o)** → Everyone else  

### 🔑 Permission Types  
- **r** → Read (numeric value = 4)  
- **w** → Write (numeric value = 2)  
- **x** → Execute (numeric value = 1)  

### 📜 Permission Layout Example  

From `ls -l`:  
```

-rwxr-xr--

````

**Breakdown:**  
- `-` → Regular file (`d` = directory, `l` = symlink, etc.)  
- `rwx` → Owner has read, write, execute  
- `r-x` → Group has read, execute  
- `r--` → Others have read only  

---

## ✅ 2. `chmod` – Change File Permissions  

### 📌 Syntax  
```bash
chmod [options] mode filename
````

Modes can be set in **numeric (octal)** or **symbolic** form.

---

### 🔢 (A) Numeric (Octal) Method

Each permission is represented as a number:

* Read = **4**
* Write = **2**
* Execute = **1**

**Sum values to assign permissions:**

* `7 = rwx`
* `6 = rw-`
* `5 = r-x`
* `4 = r--`
* `0 = ---`

**Example:**

```bash
chmod 755 script.sh
```

Meaning:

* Owner: 7 → `rwx`
* Group: 5 → `r-x`
* Others: 5 → `r-x`

---

### ✍️ (B) Symbolic Method

Use `u` (user/owner), `g` (group), `o` (others), `a` (all).
Operators:

* `+` → Add permission
* `-` → Remove permission
* `=` → Assign exact permission

**Examples:**

```bash
chmod u+x script.sh     # Add execute for owner
chmod g-w notes.txt     # Remove write from group
chmod o=r file.txt      # Set others to read only
chmod a+r report.txt    # Everyone gets read access
```

---

### 🔄 (C) Recursive Changes

```bash
chmod -R 755 /mydir
```

* `-R` → Applies changes recursively to all files/subdirectories.

---

## ✅ 3. `chown` – Change File Ownership

### 📌 Syntax

```bash
chown [options] new_owner:new_group filename
```

**Examples:**

```bash
chown rishabh file.txt          # Change owner to user 'rishabh'
chown rishabh:dev file.txt      # Change owner to 'rishabh' and group to 'dev'
chown :dev file.txt             # Change only group to 'dev'
chown -R rishabh:dev /project   # Recursive ownership change
```

---

## ✅ 4. Putting It All Together

### 📂 Example Scenario

```bash
touch project.sh
ls -l project.sh
```

**Output:**

```
-rw-r--r-- 1 rishabh dev 0 Aug 19 12:00 project.sh
```

Now apply changes:

```bash
chmod 700 project.sh        # Only owner has rwx
chmod u+x,g-w project.sh    # Add execute for user, remove write for group
chown root:admin project.sh # Change owner to root and group to admin
```

---

## ✅ 5. Quick Reference Table

| Numeric | Permission | Meaning      |
| ------- | ---------- | ------------ |
| 0       | ---        | No access    |
| 1       | --x        | Execute only |
| 2       | -w-        | Write only   |
| 3       | -wx        | Write + Exec |
| 4       | r--        | Read only    |
| 5       | r-x        | Read + Exec  |
| 6       | rw-        | Read + Write |
| 7       | rwx        | Full access  |

---

✅ **Key Tip**: Use **numeric values** for quick settings (e.g., 755, 644) and **symbolic form** for fine adjustments (`u+x`, `g-w`).

---

```
```