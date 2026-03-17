---
title: "Modernizing the IBM i: From Green Screen to Node.js Web Interface"
date: 2026-02-26T15:34:30-04:00
categories:
  - blog
tags:
  - Jekyll
  - update
---
Modernizing the IBM i: From Green Screen to Node.js Web Interface
📖 The Case Study: Solving a Real-World Business Pain Point

The Problem: Our Credit Controller, working remotely, was spending hours "menu-hopping" in a traditional 5250 Green Screen session. They had to gather data from multiple screens just to copy-paste it into a customer's web portal. It was slow, error-prone, and frustrating.

The Solution: Instead of "replacing" the system, we modernized the delivery. We used Node.js running natively on the IBM i to fetch the data and serve it through a clean, responsive web interface.
🛠️ The Architecture: How It’s Built

Based on the project structure (seen in the file explorer), here is how the application is organized:

    server.js: The heart of the application. This is our Express.js server that handles routing and requests.

    db.js: The database connector. This is where we use the idb-p or itoolkit to talk to DB2 for i.

    views/: Contains our .ejs templates. This is where the "Product Summary" UI lives.

    public/: Stores our CSS (to give it that cool retro-modern green look) and any client-side JavaScript.

    package.json: Manages our dependencies (Express, Nodemon, etc.).

    core: The binary/logic layer that ensures the Node.js environment communicates correctly with the IBM i OS.

🚀 Step-by-Step: For New Learners

If you want to replicate this "Eureka" moment, follow these core steps:
1. Set Up Your Environment

First, ensure Node.js is installed on your IBM i. You can verify this via SSH:
Bash

node -v
npm -v

Tip: Ensure /QOpenSys/pkgs/bin is in your PATH!
2. Initialize and Install Express

Create your project folder and install the web framework:
Bash

npm init -y
npm install express ejs

3. Connect to DB2

In your db.js, use the IBM i database connectors to fetch your "Product Summary" data.
JavaScript

// Example logic
const db = require('idb-p');
const conn = new db.DbConn();
conn.conn("*LOCAL");
// SQL: SELECT DESCRIPTION, NUMBER FROM PRODUCT_TABLE

4. Create the "Retro-Modern" UI

Using HTML and CSS in your .ejs files, you can replicate the familiarity of the Green Screen while adding the power of a web browser (like search bars, scroll wheels, and easy copy-paste).
🖼️ The Result: Product Summary Web Portal

![Insert your Product Summary Snapshot Here]

    The Impact: The Credit Controller now has a single URL to visit. No more nested menus. No more 5250 login for simple data checks. Just the data they need, instantly accessible and easy to copy.