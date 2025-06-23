text editor 



# 📂 **`cat` Command in Linux (Text Viewing Tool)**

The `cat` command (**concatenate**) is a powerful utility used to **view, combine, create, or append text files** in Linux.

---

## 📄 **1. Display File Contents**

| Description | Command |
| --- | --- |
| Show contents of a file | `cat filename.txt` |
| Show system file contents | `cat /etc/passwd` |
| Show contents of multiple files | `cat file1.txt file2.txt` |
| Multiple files in one command | `cat /etc/passwd /etc/shadow /etc/group /etc/gshadow` |
| Using semicolons (separate commands) | `cat /etc/passwd; cat /etc/shadow` |

---

## 📚 **2. Combine Files and Save to a New File**

| Description | Command |
| --- | --- |
| Combine and save to a new file | `cat file1.txt file2.txt > combined.txt` |
| Combine system files into one | `cat /etc/hostname /etc/hosts /etc/os-release > 1.txt` |
| Combine all `.conf` files | `cat /etc/*.conf > all-conf.txt` |

---

## 🖊️ **3. Append to an Existing File**

| Description | Command |
| --- | --- |
| Append interactively (type and press `CTRL+D` to save) | `cat >> test.txt` |
| Append a file to another | `cat list.txt >> t1.txt` |
| Append system file content to another file | `cat /etc/hosts >> 1.txt` |

---

## 🆕 **4. Create a New File Using `cat`**

| Description | Command |
| --- | --- |
| Create file by typing (press `CTRL+D` to finish) | `cat > test.txt` |
| Create file using **Here Document** |  |

```bash
cat << EOF > notes.txt
Line 1
Line 2
EOF

```

---

## 🔢 **5. Display with Line Numbers or Symbols**

| Description | Command |
| --- | --- |
| Show content with line numbers | `cat -n test.txt` |
| Line numbers + line end `$` symbols | `cat -ne a4.txt` |
| Show `$` at line ends only | `cat -e test.txt` |

---

## 📜 **6. Use with Paging Tools**

| Description | Command |
| --- | --- |
| Page-by-page using `more` | `cat test.txt |
| Page-by-page using `less` | `cat test.txt |

---

## 💡 **Tip: `CTRL+C` Behavior in Linux**

> If multiple files or commands are running, pressing CTRL+C stops only the currently running (foreground) file or command, not the previous or background ones.
> 

---

---

# 📝 **Nano Command in Linux**

The `nano` command is a **simple, user-friendly, terminal-based text editor** used to **create and edit text files**. It’s ideal for **beginners** due to its intuitive interface and helpful on-screen shortcuts.

---

## 📦 **Install Nano Editor**

### ✅ For RHEL / CentOS / Fedora:

```bash
yum install nano

```

### ✅ For Debian / Ubuntu:

```bash
sudo apt install nano

```

---

## 📂 **Open Nano Editor**

| Action | Command |
| --- | --- |
| Open nano without a file | `nano` |
| Open or create a file named `armour.txt` | `nano armour.txt` |

> 🔹 If the file doesn’t exist, it will be created automatically.
> 

---

## 🧭 **Basic Navigation & Editing**

- Use **arrow keys** to move the cursor.
- Simply **type to insert or edit** text.

---

## 🎹 **Common Shortcut Keys in Nano**

| Shortcut | Action |
| --- | --- |
| `Ctrl + O` | Save (Write Out) |
| `Ctrl + X` | Exit nano |
| `Ctrl + K` | Cut current line |
| `Ctrl + U` | Paste last cut |
| `Ctrl + W` | Search text |
| `Ctrl + G` | Help (displays all shortcuts) |

---

## 🔄 **Example Workflow**

1️⃣ Open or create a file:

```bash
nano notes.txt

```

2️⃣ Type your content.

3️⃣ Save the file:

Press `Ctrl + O` → Hit `Enter` to confirm the filename.

4️⃣ Exit nano:

Press `Ctrl + X`.

---

---

# 🧠 **Vim Command – Professional Notes**

Vim (Vi IMproved) is a powerful, widely-used text editor on Unix/Linux systems.

It enhances the classic `vi` editor and is preferred for scripting, configuration, and programming.

🔸 **Vi = Visual Editor**

🔸 **Vim is not WYSIWYG** (What You See Is What You Get)

🔸 Used extensively in system admin, DevOps, and programming.

---

## 🚀 Launching Vim

| Action | Command |
| --- | --- |
| Open Vim editor | `vim` |
| Open/create a file | `vim filename` |
| Open Vim help menu | `:help` |
| Vim tutorial (practice tool) | `vimtutor` |
| Run shell command (e.g., `ls`) | `:!ls` or `:!pwd` or `:!id` |

---

## 🔄 Vim Modes

| Mode | Purpose | How to Enter |
| --- | --- | --- |
| Command Mode | Navigate, delete, copy, etc. | Default on start |
| Insert Mode | Insert text | `i` or `Insert` |
| Visual Mode | Select text visually | `v` |
| Replace Mode | Replace characters | `R` |
| Command-Line Mode | Execute commands like save, quit, replace, etc. | `:` |

---

## 🔢 Line Numbers

| Action | Command |
| --- | --- |
| Enable line numbers | `:set number` or `:set nu` |
| Disable line numbers | `:set nonumber` |

---

## 🧪 Sample File: `testfile.txt`

```bash
vim testfile.txt

```

Paste the following sample content for practice:

```
1 Hello, this is AI-generated content. for test AI
2 AI is changing the world.
3 Armour Infosec specializes in AI and Cyber Security.
4 AI is powerful.
5 This line is blank below:
6
7
8 Change /bin/bash to /sbin/nolog for restricted users.
9 Some users still use /bin/bash.
10 Change bash to sh if needed.
11 Line Numbering helps in editing.
12
13 This file is for testing search and replace in Vim.
14 Another AI-powered sentence. AI
15
16 End of AI content.

```

---

## 🔍 Search and Replace in Vim

| Action | Command |
| --- | --- |
| Replace all `AI` with `Artificial Intelligence` | `:%s/AI/Artificial Intelligence/g` |
| Replace `bash` with `sh` with confirmation | `:%s/bash/sh/gc` |
| Replace `/bin/bash` with `/sbin/nologin` | `:%s/\/bin\/bash/\/sbin\/nologin/g` |
| Replace `AI` with `ML` (line 3 to 6) | `:3,6s/AI/ML/g` |
| Remove extra blank lines | `:g/^$/d` |
| Replace in current line | `:s/AI/Artificial Intelligence/` |
| Replace from line 1 to 32 | `:1,32s/AI/Artificial/` |
| Replace `nologin` with `bash` globally | `:%s/nologin/bash/g` |
| Case-insensitive replace `Bash` to `sh` | `:%s/Bash/sh/gi` |
| Replace between lines 56–65 (typo fix) | `:56,65s/bash/bash/g` |
| Revert shell change | `:%s/\/sbin\/nologin/\/bin\/bash/g` |
| Clear search highlights | `:nohl` |

---

## 🧭 Cursor Movement (Command Mode)

| Action | Key |
| --- | --- |
| Move left | `h` |
| Move down | `j` |
| Move up | `k` |
| Move right | `l` |

---

## 🗑️ Deleting in Vim

### 🔸 Characters

| Action | Command |
| --- | --- |
| Delete 1 character | `x` |
| Delete 10 characters | `10x` |
| Delete character before cursor | `X` |

### 🔸 Words

| Action | Command |
| --- | --- |
| Delete 1 word | `dw` |
| Delete 10 words | `10dw` |

### 🔸 Lines

| Action | Command |
| --- | --- |
| Delete 1 line | `dd` |
| Delete 10 lines | `10dd` |
| Delete from cursor to end | `D` |

---

## 🔁 Replacing Text

### 🔸 Characters & Words

| Action | Command |
| --- | --- |
| Replace 1 character | `r` |
| Replace 3 characters | `3r` |
| Change 1 word | `cw` |
| Change 3 words | `3cw` |

### 🔸 Lines

| Action | Command |
| --- | --- |
| Change from cursor to end line | `C` |
| Change 3 lines | `3C` |

---

## ➕ Inserting & Joining Lines

| Action | Command |
| --- | --- |
| Insert blank line below | `o` |
| Insert blank line above | `O` |
| Join 2 lines | `J` |
| Join 3 lines | `3J` |

---

## 📋 Copy & Paste Lines

| Action | Command |
| --- | --- |
| Copy line | `yy` |
| Paste line | `p` |

---

## 🎮 Practice Vim in a Fun Way

Play Vim Game Online:

🌐 [https://vim-adventures.com](https://vim-adventures.com/)

---
