# 📘 Backend Revision – Day 2
```
Day 2 of my backend revision streak.
Today's topics: Modules, CommonJS, File System (fs), Path, OS, and a CLI Tool for System Info.
```
---
```
## 📂 Project Structure

backend-revision-day2/
│── system-info.js
│── examples/
│   ├── fs-example.js
│   ├── path-example.js
│   └── os-example.js
│── package.json
│── README.md
```
---

## 🧩 1. Node.js Modules (CommonJS)

Definition:
Modules are reusable pieces of code that help structure a Node.js project.

Types of Modules:

* Core Modules → fs, path, os
* Local Modules → your own files
* Third-Party Modules → npm packages

CommonJS Syntax:
```
Export: module.exports = { add }
Import: const { add } = require("./math")
```
---

## 📁 2. File System (fs Module)

Common functions:

* fs.readFile()
* fs.writeFile()
* fs.appendFile()
* fs.unlink()
* fs.mkdir()

Example (fs-example.js):
```
const fs = require("fs");
fs.writeFile("notes.txt", "Day 2 revision!", (err) => {
if (err) throw err;
console.log("File created!");
});
```
---

## 📁 3. Path Module
```
Example (path-example.js):

const path = require("path");
console.log(__dirname);
console.log(path.join(__dirname, "data", "demo.txt"));

```
---

## 💻 4. OS Module

Example (os-example.js):
```
const os = require("os");
console.log("OS Type:", os.type());
console.log("Total Memory:", os.totalmem());
console.log("Free Memory:", os.freemem());
```
---
```
# 🛠️ 5. CLI Tool – System Info

File: system-info.js

#!/usr/bin/env node
const os = require("os");
const path = require("path");

console.log("=== System Information ===");
console.log("OS Type:", os.type());
console.log("Platform:", os.platform());
console.log("CPU Cores:", os.cpus().length);
console.log("Total Memory:", (os.totalmem() / 1024 / 1024 / 1024).toFixed(2), "GB");
console.log("Free Memory:", (os.freemem() / 1024 / 1024 / 1024).toFixed(2), "GB");
console.log("Home Directory:", os.homedir());
console.log("Example File Path:", path.join(__dirname, "example.txt"));
```
---

## 🔧 Make It a CLI Command

1. Add inside package.json:

```
"bin": {
"sys-info": "./system-info.js"
}
```

2. Give execute permission (Mac/Linux):
   ```chmod +x system-info.js```

3. Link globally:
   ````npm link````

4. Run:
   ````sys-info````

---

# 🟢 Day 2 Completed

Topics Covered:
✔ Modules (CommonJS)
✔ fs Module
✔ path Module
✔ os Module
✔ CLI Tool

```
Streak Progress:
✔ Day 1 — Node + NPM + Setup
✔ Day 2 — Modules + FS + CLI Tool
⬜ Day 3 — Events, EventEmitter, Streams
⬜ Day 4 — MongoDB + Mongoose
⬜ Day 5 — JWT Authentication
```
---

# ⭐ Notes for Future Me

* Keep uploading daily
* Micro projects build deep understanding
* Consistency builds mastery

---

If you want, I can prepare **Day 3 Revision + Terminal-style README** same format.
