# Logbook
A command-line utility for logging daily engineering activity.

<a href="https://asciinema.org/a/09iijMGsLwNtPrhO69TMAB7RA" target="_blank"><img src="https://asciinema.org/a/09iijMGsLwNtPrhO69TMAB7RA.png" /></a>

Thanks to James Routley for the inital idea, see his blog post [here](https://routley.io/tech/2017/11/23/logbook.html)

# Installation
```
cp lb /usr/local/bin/
```

# Usage
begin a new log entry
```
lb "Update the API to validate incoming requests"
```

Open the latest log entry
```
lb
```

Change the editor to open logbooks with (default is `vi`)
```
export EDITOR=atom
lb
```

Change the default location where the logbook is stored
```
export LOGBOOK_DIR=/tmp/mylogbook/
lb
```

# Markdown server
Sometimes you want to share your logbook with others, the project comes with a server for sharing links to your log entries.

## Installation
```
pip install -r requirements.txt
```
## Usage
```
./start_server
```

goto [http://localhost:8000](http://localhost:8000)
