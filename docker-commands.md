## Docker Commands

### List of Commands
```
touch Dockerfile			# Create docker file
docker --version			# View docker version
docker info				# All information of docker
docker run <docker_name>		# Run docker image
docker run -d -p 4000:80 <docker_name>	# Run docker image with port number
docker image ls				# View docker images list
docker images				# View docker images list
docker build -t <dockr_img_name>	# Build docker with specific name
docker-machine ip			# Find docker machine default running ip [ http://192.168.99.100:4000/ ]
docker container ls 			# View container list
docker container stop <container_hash>	# Stop execution of container
```

```
docker build -t friendlyhello .  	# Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  	# Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello  # Same thing, but in detached mode
docker container ls                     # List all running containers
docker container ls -a             	# List all containers, even those not running
docker container stop <hash>           	# Gracefully stop the specified container
docker container kill <hash>         	# Force shutdown of the specified container
docker container rm <hash>        	# Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                      # List all images on this machine
docker image rm <image id>            	# Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             		# Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag 	# Upload tagged image to registry
docker run username/repository:tag 	# Run image from a registry
```

