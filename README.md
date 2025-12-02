# Day-2-Backend-Revise-
📘 Backend Revision – Day 2 Topics:  ✔ Modules (CommonJS) ✔ File System (fs) ✔ Path (path) ✔ OS Module (os) ✔ Build a CLI tool to show system info


🧩 1. What Are Modules in Node.js?
Interview-Ready Definition

“Modules in Node.js are reusable blocks of code that are isolated from other parts of the application. They help structure the code into smaller pieces using import/export.”

Types of Modules

Core Modules
→ Already built into Node
Example: fs, path, os, http, events

Local Modules
→ Created by you
Example: ./utils.js, ./math.js

Third-Party Modules
→ Installed through npm
Example: chalk, dotenv, express

🧱 2. CommonJS (CJS) Syntax

CJS is the default module system in Node (older but widely used).

Export
// math.js
function add(a, b) {
  return a + b;
}

module.exports = { add };

Import
const { add } = require("./math");
console.log(add(5, 10));

📂 3. fs Module (File System)
Common Functions
Purpose	Function
Read file	fs.readFile()
Write file	fs.writeFile()
Append	fs.appendFile()
Delete file	fs.unlink()
Create folder	fs.mkdir()
Example
const fs = require("fs");

fs.writeFile("notes.txt", "Day 2 revision started!", (err) => {
  if (err) throw err;
  console.log("File created");
});

📁 4. path Module
Why we use it?

To handle file paths properly (avoids errors on Windows/Linux).

Example
const path = require("path");

console.log(__filename);       
console.log(__dirname);        

const fullPath = path.join(__dirname, "src", "data.txt");
console.log(fullPath);

💻 5. os Module
Useful Functions
Purpose	Method
CPU info	os.cpus()
Free memory	os.freemem()
Total memory	os.totalmem()
Hostname	os.hostname()
OS Type	os.type()
Example
const os = require("os");

console.log("OS:", os.type());
console.log("Total Memory:", os.totalmem());
console.log("Free Memory:", os.freemem());

🛠️ 6. Build a CLI Tool to Show System Info

This will be your practical mini-project for Day 2.

Step 1 — Create file: system-info.js
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
console.log("File Path Example:", path.join(__dirname, "example.txt"));

Step 2 — Make it a CLI command

Add this in package.json:

"bin": {
  "sys-info": "./system-info.js"
}

Step 3 — Give execute permission

(Required on macOS/Linux)

chmod +x system-info.js

Step 4 — Install globally (for testing)
npm link

Step 5 — Run your CLI
sys-info


You will see complete system information on terminal.

🟩 Day 2 Completed!

You learned:
✔ CommonJS modules
✔ fs module
✔ path module
✔ os module
✔ Built your own CLI tool (professional-level practice)
