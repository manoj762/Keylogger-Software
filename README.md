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