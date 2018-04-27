# Logbook
A command-line utility for logging daily engineering activity.

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
