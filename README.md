# 📘 Backend Revision – Day 2

Day 2 of my backend revision streak.  
Today's topics: **Modules, CommonJS, File System (fs), Path module, OS module, and a CLI Tool for System Info**.

---

## 📂 Project Structure

backend-revision-day2/
│── system-info.js
│── examples/
│ ├── fs-example.js
│ ├── path-example.js
│ └── os-example.js
│── package.json
│── README.md

yaml
Copy code

---

## 🧩 1. Node.js Modules (CommonJS)

### ✔ Definition  
Modules are reusable pieces of code used to structure a Node.js application.

### ✔ Module Types  
- **Core Modules:** fs, path, os, http  
- **Local Modules:** your own created files  
- **Third-Party Modules:** installed using npm (chalk, express, etc.)

### ✔ CommonJS Syntax  
**Export**
```js
module.exports = { add };
Import

js
Copy code
const { add } = require("./math");

```
📁 2. File System (fs Module)
Commonly used functions:

fs.readFile()

fs.writeFile()

fs.appendFile()

fs.unlink()

fs.mkdir()

Example (fs-example.js)
js
Copy code
const fs = require("fs");

fs.writeFile("notes.txt", "Day 2 revision!", (err) => {
  if (err) throw err;
  console.log("File created!");
});

### 📁 3. Path Module
Example (path-example.js)
js
Copy code
const path = require("path");

console.log(__dirname);
console.log(path.join(__dirname, "data", "demo.txt"));
### 💻 4. OS Module
Example (os-example.js)
js
Copy code
const os = require("os");

console.log("OS Type:", os.type());
console.log("Total Memory:", os.totalmem());
console.log("Free Memory:", os.freemem());
🛠️ 5. CLI Tool – System Info
A custom CLI tool that prints your system information directly in the terminal.

system-info.js
js
Copy code
#!/usr/bin/env node
const os = require("os");
const path = require("path");

console.log("=== System Information ===");
console.log("OS Type:", os.type());
console.log("Platform:", os.platform());
console.log("CPU Cores:", os.cpus().length);
console.log(
  "Total Memory:",
  (os.totalmem() / 1024 / 1024 / 1024).toFixed(2),
  "GB"
);
console.log(
  "Free Memory:",
  (os.freemem() / 1024 / 1024 / 1024).toFixed(2),
  "GB"
);
console.log("Home Directory:", os.homedir());
console.log("Example File Path:", path.join(__dirname, "example.txt"));
🔧 Make It Work as a CLI Command
Step 1: Add this to package.json
json
Copy code
"bin": {
  "sys-info": "./system-info.js"
}
Step 2: Provide execute permission (Mac/Linux)
perl
Copy code
chmod +x system-info.js
Step 3: Link globally
bash
Copy code
npm link
Step 4: Run your CLI
pgsql
Copy code
sys-info
🟢 Day 2 Completed
Topics Covered

✔ Modules (CommonJS)

✔ fs Module

✔ path Module

✔ os Module

✔ CLI Tool

Streak Progress

✔ Day 1 — Node + NPM + Setup

✔ Day 2 — Modules + FS + CLI Tool
