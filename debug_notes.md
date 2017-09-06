### 5/23/17 Debugging Docker

I was getting the error below when starting Docker. I fixed it by doing this in the terminal:

`/Applications/Docker.app/Contents/MacOS/Docker --uninstall`

#### Error:

```
Docker for Mac: version: 17.03.1-ce-mac12 (d1db12684)
macOS: version 10.11.6 (build: 15G1217)
logs: /tmp/DE2FC0FC-4B8E-4B3D-BB60-5FD2AC12ED0E/20170523-063423.tar.gz
failure: Docker.qcow2 missing: the VM has never been started
[OK]     vmnetd
[OK]     dns
[ERROR]  driver.amd64-linux
         com.docker.driver.amd64-linux -db is not running
[OK]     virtualization VT-X
[OK]     app
[ERROR]  moby
         /Users/alexnitta/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/console-ring does not exist
[OK]     system
[OK]     moby-syslog
[ERROR]  db
         Connection refused (ECONNREFUSED) connecting to /Users/alexnitta/Library/Containers/com.docker.docker/Data/s40: check if service is running
         com.docker.db is not running
[OK]     env
[OK]     virtualization kern.hv_support
[ERROR]  slirp
         Unexpected error ((Failure
  "Error connecting socket to 9p endpoint unix:/Users/alexnitta/Library/Containers/com.docker.docker/Data/s51: Unix.Unix_error(Unix.ECONNREFUSED, \"connect\", \"\")")) connecting to /Users/alexnitta/Library/Containers/com.docker.docker/Data/s51
         com.docker.slirp is not running
         slirp check failed with: (Failure
  "Error connecting socket to 9p endpoint unix:/Users/alexnitta/Library/Containers/com.docker.docker/Data/s52: Unix.Unix_error(Unix.ECONNREFUSED, \"connect\", \"\")")
[ERROR]  osxfs
         com.docker.osxfs is not running
[OK]     moby-console
[OK]     logs
[ERROR]  docker-cli
         Connection refused (ECONNREFUSED) connecting to /var/run/docker.sock: check if service is running
         Connection refused (ECONNREFUSED) connecting to /Users/alexnitta/Library/Containers/com.docker.docker/Data/s60: check if service is running
         docker ps failed
[OK]     menubar
[ERROR]  disk
         Docker.qcow2 missing: the VM has never been started
```
