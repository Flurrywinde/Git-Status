# Recursive Git Status Summarizer

## Original Description
Ever wanted to get the status of repos in multiple sub directories? Yeah, me too. So I knocked this up.

Show Status is awesome. If you tell it a directory to look in, it'll scan through all the sub dirs looking for a .git directory. When it finds one it'll look to see if there are any changes and let you know. It can also push and pull to/from a remote location (like github.com) (but only if there are no changes.) Contact mike@mikepearce.net for any support.

## Flurrywinde's Mods
* Made it show what changes you have:
	* Unstaged modified files
	* Staged files
	* Unpushed commits
	* Untracked files
* Recurse the entire folder tree looking for git projects. (The original version only looks one level down.)
* Switched to termcolor for ANSI colors. I had to do this so `watch -d show_status` wouldn't turn black&white (ugly!).
* Removed the path, leaving only the basename folder. This makes the columns skinnier, so if you have it in a tmux pane, you can save room.
* Removed extra spaces in the columns for more skinniness.
* Fixed a bug where sometimes the script would report no changes when there really were some.
* Notify you if there is no remote. (I forget to attach to a remote and like to know when that happens.)

## Screenshot
![Watch show_status in tmux](/gitstatusall.png?raw=true "Real-time Git Status Summary in a tmux pane")

## Installation
**Copy show_status to `~/bin`:**

%> cp show_status ~/bin (or /usr/local/bin)

**Give it execute permissions:**

%> chmod +x ~/bin/show_status

## Usage
**Usage:** show_status [options]

Given no parameters, look in current folder and sub-folders for git projects, and display a colorful summary of each one's git status.

**Options:**
  -h, --help            show this help message and exit
  -d DIRNAME, --dir=DIRNAME
                        The directory to parse sub dirs from
  -v, --verbose         Show the full detail of git status
  -r REMOTE, --remote=REMOTE
                        Push to the master (remotename:branchname)
  -p PULL, --pull=PULL  Pull from the master (remotename:branchname)

## Warranties/Guarantees
None, you're on your own. If you'd like some help, mail me on mike@mikepearce.net
