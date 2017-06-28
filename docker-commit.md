## Modify on container
Dockerfile allow us to build an image,

From that image we can run container,

Ok when container already run, modify on container by HAND, COMPLETELY MANUAL,

	How can we save these change?
docker commit as

	docker commit <container> <image-tag>

When container running, after modify on it, commit it by image-tag (use new image tag or can reuse the old-one)

## Example

	# Modify a new container
	docker run --name hw_container ubuntu:latest
	   touch /HelloWorld

	# Commit the changes you made in that container
	# to a new image
	docker commit hw_container hw_image

	# Remove the changed container
	docker rm -vf hw_container

	# Test the new image docker run --rm hw_image
	# ls -l /HelloWorld
	# Outputs:
	# -rw-r--r-- 1 root root 0 Apr 15 22:06
	# /HelloWorld