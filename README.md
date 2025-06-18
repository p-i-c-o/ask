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

## Example

``` 
root@thinkpad:~/ask$ cat * | ask -o "What is this github repo about?"
This GitHub repository is for ask, a simple command-line interface (CLI) wrapper for the Google Gemini AI. It allows 
users to interact with the Gemini model directly from their terminal, providing options to include the output of     
previous commands as context (-o) and to request suggestions for shell commands related to their query (-s). 