# dev-tips
Tips and tricks to remember when developing software.

## Git
* Delete a local branch: `git branch -d <branchname>`
* Delete the remote branch: `git branch -dr <remote>/<branchname>`
  * Example: `git branch -dr origin/myawesomebranch`
* Temporarily save changes, revert to the previous commit, and apply changes in a new branch: `git stash` then `git stash branch <branchname>`
* Add the new commit to the previous one without changing the commit message: `git commit --amend --no-edit`
* Remove untracked files from current branch: (to preview changes) `git clean -f -n` (to actually delete files) `git clean -f`
* Preview changes before you pull: `git fetch` then `git diff origin/<branchname>`
* Fetch a remote branch into a new local branch: `git fetch <remote> <rbranch>:<lbranch>`, then `git checkout <lbranch>`
* Interactively remove commits: `git rebase -i HEAD~N`, where N is the number of prior commits you want to review
* Show a list of files affected by a commit: `git show --pretty="" --name-only e2a7b36`
* Show the diff between two branches: `git diff <branch_1>..<branch_2>`
* Show the diff between a specific file on two branches: `git diff <branch_1>..<branch_2> -- <filename>`
* Show the file names that changed between two branches: `git diff --name-only <branch_1>..<branch_2>`

## Sublime RegEx
* Finds variable definitions like `BIG_TEXT =` : `([A-Z\_]+)\s?=\s?\d+`
* Finds two more more lines like `BIG_TEXT = 0`, as well as indented versions : `(^(\s{4})?([A-Z\_]+)\s*=\s*\d+\n){2,}`
* Finds a given import from a given module, even if other imports are included: `import[\w\s,\{]+takeEvery[\w\s,\}]+from 'redux-saga'`

## Vim
* To remove blank lines (from Command mode): `:g/^$/d`, then `:x` to save and exit
* Go to a specific line number: `<line_number>G`
* Go to the last line: `G`
* Search and replace examples
  * `:%s/\(^ERROR)\(\w\+\)/\1_\2/` search for lines beginning with ERROR, followed by one or more alphanumeric ('word') characters. Insert an underscore between the ERROR and the word characters.
    * `^ERROR` and `\w\+` are set up as backreferences with the `\(` before and `\)` after each one. The last portion, `/\1_\2/`, inserts an underscore between the first backreference `\1` and the second backreference `\2`.
  * `:%s/\("[^",]\+\),\([^"]\+"\)/\1\\,\2/` search for commas appearing between double quotation marks and escape the commas with a preceding backslash.
    * In the first parentheses, we match the opening double quotes then any number of characters that are not a comma. That is the meaning of `\("[^",]\+\)`. In the second parentheses, we match any number of characters that are not a double quote, and the closing double quote with `\([^"]\+"\)`. Finally, `/\1\\,\2/` inserts a `\\,` (escaped backslash and comma) between each of the backreferences, `\1` and `\2`.

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

## Mac OS
* Prevent computer from sleeping: `pmset noidle`, then `CTRL-C` to cancel. [Wikipedia] (https://en.wikipedia.org/wiki/Pmset)

## Server Admin
* If you see an EACCESS error when you try to start Node on a server, it's usually because you didn't use `sudo` or because Node is already running. Using `sudo` is necessary because root privileges are required to expose ports below 1024.
* To power off an Ubuntu server: `sudo shutdown -h now`
