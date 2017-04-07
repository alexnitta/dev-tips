# dev-tips
Tips and tricks to remember when developing software

## Unix Server Admin
* If you see an EACCESS error when you try to start Node on a server, it's usually because you didn't use `sudo` or because Node is already running. Using `sudo` is necessary because root privileges are required to expose ports below 1024.
* To power off an Ubuntu server: `sudo shutdown -h now`

## Vim
* To remove blank lines (from Command mode): `:g/^$/d`, then `:x` to save and exit
* Go to a specific line number: `<line_number>G`
* Go to the last line: `G`

## Git
* Delete a local branch: `git br -d <branchname>`
* Delete the remote branch: `git br -dr <remote>/<branchname>`
  * Example: `git br -dr origin/myawesomebranch`
* Remporary save changes, revert to the previous commit, and apply changes in a new branch: `git stash` then `git stash branch <branchname>`
* Add the new commit to the previous one without changing the commit message: `git commit --amend --no-edit`
* Remove untracked files from current branch: (to preview changes) `git clean -f -n` (to actually delete files) `git clean -f`
* Preview changes before you pull: `git fetch` then `git diff origin/<branchname>`

## Local Filesystem
* Create a symlink: `ln -s <target_path> <symlink_path>`
* Count the number of files or directories in the current directory: `ls -1 | wc -l`
* View numerical permissions of files in current directory: `stat -c '%a %n' *`
* Search for a file by filename: `find <path> -name <filename>`
* Search for a string within a file: `grep <string> <filename>`
* Search for a string within all files in a directory and subdirectories: `grep -r <string> <directory>`
* See the difference between two directories of files, with visual diff of each line: `diff -bur <dir1/> <dir2/>`
* See a list of the files that are different between two directories: `diff -qr <dir_one> <dir_two> | sort`

## Python
* Check if a virtual environment is active: `pip -V` - the path will be in the project folder if a venv is running

## RegEx
* Finds variable definitions like `BIG_TEXT =` : `([A-Z\_]+)\s?=\s?\d+`
* Finds two more more lines like `BIG_TEXT = 0`, as well as indented versions : `(^(\s{4})?([A-Z\_]+)\s*=\s*\d+\n){2,}`

## Mac OS
* Prevent computer from sleeping: `pmset noidle`, then `CTRL-C` to cancel. [Wikipedia] (https://en.wikipedia.org/wiki/Pmset)
