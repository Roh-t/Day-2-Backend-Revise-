# Day-2-Backend-Revise-
📘 Backend Revision – Day 2 Topics:  ✔ Modules (CommonJS) ✔ File System (fs) ✔ Path (path) ✔ OS Module (os) ✔ Build a CLI tool to show system info

# 📘 Backend Revision – Day 2

Day 2 of my backend revision streak.  
Today's goal: **Modules, File System, CommonJS, fs, path, os, and a CLI Tool for System Info.**

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

### 📌 Definition  
Modules are reusable pieces of code that we import/export to structure a project.

### 📌 Types of Modules  
- **Core modules** → fs, path, os, http  
- **Local modules** → custom files  
- **Third-party modules** → installed via npm  

### 📌 CommonJS Syntax  
**Export**
```js
module.exports = { add };
Import

js
Copy code
const { add } = require("./math");
📁 2. fs Module (File System)
Common operations:

js
Copy code
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
📁 3. path Module
Example (path-example.js)
js
Copy code
const path = require("path");

console.log(__dirname);
console.log(path.join(__dirname, "data", "demo.txt"));
💻 4. os Module
Example (os-example.js)
js
Copy code
const os = require("os");

console.log("OS Type:", os.type());
console.log("Total Memory:", os.totalmem());
console.log("Free Memory:", os.freemem());
🛠️ 5. CLI Tool – System Info
Created a custom CLI tool to print system information.

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
console.log("Total Memory:", (os.totalmem() / 1024 / 1024 / 1024).toFixed(2), "GB");
console.log("Free Memory:", (os.freemem() / 1024 / 1024 / 1024).toFixed(2), "GB");
console.log("Home Directory:", os.homedir());
console.log("Example File Path:", path.join(__dirname, "example.txt"));
🔧 Make it a CLI Command
Add inside package.json:

json
Copy code
"bin": {
  "sys-info": "./system-info.js"
}
Give permission (macOS/Linux):

perl
Copy code
chmod +x system-info.js
Link globally:

bash
Copy code
npm link
Run CLI:

pgsql
Copy code
sys-info
🟢 Day 2 Completed!
