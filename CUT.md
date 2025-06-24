---

The `cut` command is used to extract sections from lines of text files or input streams. It's commonly used for handling structured data like CSVs, logs, and system files.

---

## 📌 **Syntax**

```bash
cut [OPTION]... [FILE]...

```

- If no file is given, `cut` reads from **standard input (stdin)**.

---

## 🧪 **Sample File: `users.csv`**

```
id,firstname,lastname,email
100,Belinda,Lorenz,Belinda.Lorenz@yopmail.com
101,Miquela,Cornelia,Miquela.Cornelia@yopmail.com
102,Kellen,Melony,Kellen.Melony@yopmail.com
103,Aurore,Boycey,Aurore.Boycey@yopmail.com
104,Juliane,Nerita,Juliane.Nerita@yopmail.com
105,Amii,Arne,Amii.Arne@yopmail.com
106,Konstance,Fredi,Konstance.Fredi@yopmail.com
107,Sybille,Lory,Sybille.Lory@yopmail.com
108,Susette,Kenney,Susette.Kenney@yopmail.com
109,Gretal,Howlyn,Gretal.Howlyn@yopmail.com
110,Joelly,Sacken,Joelly.Sacken@yopmail.com
111,Kristan,Xerxes,Kristan.Xerxes@yopmail.com
112,Orelia,Erminia,Orelia.Erminia@yopmail.com
113,Lynde,Malvino,Lynde.Malvino@yopmail.com
114,Marguerite,Vittoria,Marguerite.Vittoria@yopmail.com
115,Josephine,Dom,Josephine.Dom@yopmail.com
116,Dede,Blase,Dede.Blase@yopmail.com
117,Romona,Ricki,Romona.Ricki@yopmail.com
118,Dulce,Bebe,Dulce.Bebe@yopmail.com

```

---

## ✂️ **Cut Options & Usage**

### 🔹 Extract by Byte (`b`)

```bash
cut -b 1-5 filename.txt

```

👉 Extracts **bytes 1 to 5** from each line.

---

### 🔹 Extract by Character (`c`)

```bash
cut -c 1-10 filename.txt

```

👉 Extracts **characters 1 to 10** from each line.

---

### 🔹 Extract by Field (`f`) and Delimiter (`d`)

```bash
cut -d':' -f1 /etc/passwd

```

👉 Extracts the **first field** using `:` as delimiter.

```bash
cut -d, -f1,3-5 data.csv

```

👉 Extracts **fields 1 and 3 to 5** using comma delimiter.

---

## 🔁 **With Pipe**

```bash
cat file.txt | cut -d' ' -f2

```

👉 Extracts the **second word** from each line (delimiter = space).

---

### 🛑 **Skip Lines Without Delimiter (`-only-delimited`)**

```bash
cut -d':' --only-delimited -f1 file.txt

```

👉 Skips lines that do not contain the `:` delimiter.

---

## 🧾 **Examples with `users.csv`**

```bash
cat users.csv                            # Show entire file
cut -d, -f1 users.csv                    # ID column
cut -d, -f2 users.csv                    # First Name
cut -d, -f3 users.csv                    # Last Name
cut -d, -f1,2,3 users.csv                # ID, First Name, Last Name
cut -d, -f1-3 users.csv                  # Same using range
cut -d, -f1,4 users.csv                  # ID and Email
cut -d, -f1,4 users.csv > my-csv2.csv    # Save to new file

```

---

## 📄 **Text File with Space: `users.txt`**

```
id firstname lastname email
100 Belinda Lorenz Belinda.Lorenz@yopmail.com
101 Miquela Cornelia Miquela.Cornelia@yopmail.com
102 Kellen Melony Kellen.Melony@yopmail.com
103 Aurore Boycey Aurore.Boycey@yopmail.com
104 Juliane Nerita Juliane.Nerita@yopmail.com
105 Amii Arne Amii.Arne@yopmail.com
106 Konstance Fredi Konstance.Fredi@yopmail.com
107 Sybille Lory Sybille.Lory@yopmail.com
108 Susette Kenney Susette.Kenney@yopmail.com
109 Gretal Howlyn Gretal.Howlyn@yopmail.com
110 Joelly Sacken Joelly.Sacken@yopmail.com
111 Kristan Xerxes Kristan.Xerxes@yopmail.com
112 Orelia Erminia Orelia.Erminia@yopmail.com
113 Lynde Malvino Lynde.Malvino@yopmail.com
114 Marguerite Vittoria Marguerite.Vittoria@yopmail.com
115 Josephine Dom Josephine.Dom@yopmail.com
116 Dede Blase Dede.Blase@yopmail.com
117 Romona Ricki Romona.Ricki@yopmail.com
118 Dulce Bebe Dulce.Bebe@yopmail.com

```

### 🔹 Examples:

```bash
cat users.txt                        # View file
cut -f1 users.txt                    # ID (tab is default delimiter)
cut -d' ' -f1-3 users.txt            # ID, First Name, Last Name

```

---

## 🔐 **System File: `/etc/passwd`**

### 🔹 Extract fields from system file:

```bash
cut -d':' -f1 /etc/passwd             # Only usernames
cut -d':' -f1,6,7 /etc/passwd         # Username, Home, Shell
cut -d':' -f1-7 /etc/passwd           # All fields
cut -d':' -f1,2,3,4 /etc/passwd       # First four fields
cut -d':' -f1,5,6,7 /etc/passwd       # Specific fields
cat /etc/passwd | cut -d':' -f1       # Using pipe

```

---

## 📁 **Other Structured Files: `db.txt`, `ib.txt`**

### 🔹 Examples:

```bash
cut -f1 -d. ib.txt                    # Field 1, dot-delimited
cut -f2 -d"," db.txt                  # Field 2, comma-delimited
cut -f1,2 -d, db.txt                  # Fields 1 & 2
cut -f1,3 -d, db.txt                  # Fields 1 & 3
cut -f1-3 -d, db.txt                  # Fields 1 to 3
cut -f1-2,4 -d, db.txt                # Fields 1, 2, and 4

```

---

## 🌐 **Network Information Extraction with `ifconfig`**

```bash
ifconfig | cut -d' ' -f1              # First field from each line
ifconfig | cut -d' ' -f1-3            # First 3 fields
ifconfig | grep "inet" | cut -d' ' -f10   # IP Address (10th field)
ifconfig | grep "ether" | cut -d' ' -f10  # MAC Address (10th field)
ifconfig | grep "netmask" | cut -d' ' -f13 # Netmask (13th field)
ifconfig | grep "mtu" | cut -d' ' -f1     # MTU info (1st field)

```

---

## ✅ **Summary: When to Use `cut`**

| Use Case | Command Example |
| --- | --- |
| Extract first column (CSV) | `cut -d, -f1 file.csv` |
| Skip lines without delimiter | `cut -d: --only-delimited -f1 file.txt` |
| Extract range of fields | `cut -d, -f2-4 file.csv` |
| Use with pipes | `cat file.txt | cut -d' ' -f2` |
| Extract from system files | `cut -d: -f1 /etc/passwd` |
| Save output to file | `cut -d, -f1,2 file.csv > output.csv` |

---
