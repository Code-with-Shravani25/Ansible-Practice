
### Meaning of Each Field
- **Minute:** `*` → every minute  
- **Hour:** `*` → every hour  
- **Day of Month:** `*` → every day  
- **Month:** `*` → every month  
- **Weekday:** `*` → every day of the week  
---

## 🧪 Check Cron Jobs
To check your cron jobs:
```
sudo crontab -l
```

---

# 🔁 Output Redirection Cheat Sheet
#  0 = stdin (input to the command)
# 1 = stdout (normal output)
# 2 = stderr (error output)
## 1️⃣ Redirect STDOUT & STDERR to Same File (Overwrite)
```
command > file.log 2>&1
```
- `>` → overwrite stdout  
- `2>&1` → send stderr into stdout  

---

## 2️⃣ Redirect STDOUT & STDERR to Same File (Append)
```
command >> file.log 2>&1
```
- `>>` → append  
- Both stdout + stderr go to same file  

---

## 3️⃣ Redirect STDOUT and STDERR to Separate Files
```
command > out.txt 2> err.txt
```
- stdout → `out.txt`  
- stderr → `err.txt`  

---

# 📂 Examples in Cron Jobs

## ✔️ Log everything (overwrite)
```
* * * * * /path/to/script.sh > /var/log/myscript.log 2>&1
```

## ✔️ Log everything (append)
```
* * * * * /path/to/script.sh >> /var/log/myscript.log 2>&1
```

## ✔️ Separate logs
```
* * * * * /path/to/script.sh > /var/log/out.log 2> /var/log/err.log
```

---


