# dev-tips
Tips and tricks to remember when developing software

## Unix Server Admin
* If you see an EACCESS error when you try to start Node on a server, it's usually because you didn't use `sudo` or because Node is already running. Using `sudo` is necessary because root privileges are required to expose ports below 1024. 
* To power off an Ubuntu server: `sudo shutdown -h now`

## Vim
* To remove blank lines (from Command mode): `:g/^$/d`, then `:x` to save and exit
