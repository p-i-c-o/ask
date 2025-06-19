# ask
simple gemini wrapper for the terminal

## Installation + Setup
### Python Dependencies:
- `google-genai`

### Installation Script
```bash
git clone https://github.com/p-i-c-o/ask
cd ask
sudo chmod +x ./ask
sudo cp ask /usr/bin/ask
pip install -q -U google-genai
```

### API
Get your Gemini API Key from [Google AI Studio](https://aistudio.google.com/apikey).

Add the following to your .bashrc
```bash
export GOOGLE_API_KEY="YOUR_KEY_HERE"
```

## Usage
`-o`: Tell the program you are piping a command output _into_ the program.

`-s`: Ask the program to suggest commands that could help with your endeavour.

`-i <file>`: Input a file for the AI to analyse.\
Supported files: `PDF` `JavaScript` `Python` `TXT` `HTML` `CSS` `Markdown` `CSV` `XML` `RTF`

## Examples

### Explaining stuff
`root@thinkpad:~/ask$ cat * | ask -o "What is this github repo about?"`
```
This GitHub repository contains the source code for ask, a simple command-line interface (CLI) wrapper for the Google Gemini AI. It  
enables users to interact with the Gemini model directly from their terminal, supporting features like piping output from previous   
commands (-o), requesting suggested shell commands (-s), and providing file input for analysis (-i).
```

### Fixing stuff

`root@thinkpad:~$ sudo nginx -t 2>&1 | ask -o -s "Why am I getting an error? Any suggested fixes?"`
```
Error: Typo in Nginx configuration. serv_name is an unknown directive; it should be server_name.
The error is in /etc/nginx/sites-enabled/local on line 3.

Fixes:

 1 Edit /etc/nginx/sites-enabled/local.
 2 Change serv_name to server_name on line 3.
 3 Test Nginx config: sudo nginx -t.
 4 Reload Nginx: sudo systemctl reload nginx.

Suggested commands: cat -n /etc/nginx/sites-enabled/local sudo nginx -t 
```

### File Analysis

`root@thinkpad:~$ ask -i README.md "What is the ASK program?"`
```
ask is a simple command-line interface (CLI) wrapper for Google Gemini AI, allowing terminal interaction, command output piping, file
input, and command suggestions.
```