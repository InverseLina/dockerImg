Some useful docker images, now contains:
* jdk
* mysql
* nginx
* tomcat
* jenkins
* postgres

...

more images are adding. 

_Comment:_ take a look for README.md under each image folder for details.

## some useful command

* Start a system service

  ```
	systemctl start XXX
  ```

* Attach to a docker container

  ```
	docker exec -t -i container_id /bin/bash
  ```

* Exit from container

  ```
	exit
  ```