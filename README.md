# Logbook
A command-line utility for logging daily engineering activity.

<a href="https://asciinema.org/a/BaSr8PoS2huWpC3Xs25wPsNdW?autoplay=1"><img src="https://asciinema.org/a/BaSr8PoS2huWpC3Xs25wPsNdW.svg" width="500"/></a>

Thanks to James Routley for the inital idea, see his blog post [here](https://routley.io/tech/2017/11/23/logbook.html)

# Installation
```
cp lb /usr/local/bin/
```

# Usage
```
lb: a logbook utility
Usage:
    lb [<title> | <command>]

Commands:
    lb
        opens the latest logbook entry

    lb <title>
        creates a new entry in the logbook

    lb list
        lists the current logbook etries you've created, also annotates with [entry-number]s

    lb goto [entry-number]
        jumps to the specified logbook entry

    lb link [entry-number ...]
        provides links to the github/gitlab web pages where the entry can be found

    lb search [grep-options] PATTERN
        runs grep against your logbook entries

ENVIRONMENT VARIABLES:

    LOGBOOK_DIR
        specifies the directory in which to store the logbook

    EDITOR
        used by lb to determine which program to open your logbook with

```

# Examples
begin a new log entry
```
#> lb "Update the API to validate incoming requests"
```

Open the latest log entry
```
#> lb
```

list previous logbook headers
```
#> lb list
2018-10-22
        1.1 investigate bug in web service
2018-10-23
        2.1 What is Nomad?
        2.2 Determine best technology for large scale Key-Value stores
        2.3 what is JWT?
2018-10-24
        3.1 Figure out how to get credentials in AWS
        3.2 Find the root cause of the catastrophic failure last week
```

generate links
```
#> lb link 2.3 3.2
http://github.com/rushton/logbook/blob/master/2018-10-23.md#L297
http://github.com/rushton/logbook/blob/master/2018-10-24.md#L64
```

goto a given \<section\>.\<entry\> listed in `lb list`
```
lb goto 2.4
```

Change the editor to open logbooks with (default is `vi`)
```
#> export EDITOR=atom
#> lb
```

Change the default location where the logbook is stored
```
#> export LOGBOOK_DIR=/tmp/mylogbook/
#> lb
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
