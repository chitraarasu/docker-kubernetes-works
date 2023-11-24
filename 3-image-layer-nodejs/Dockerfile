FROM node:12

WORKDIR /app

COPY package.json /app 

RUN npm install

COPY . /app

EXPOSE 80

CMD ["node", "server.js"]


# Each command will execute as a layer format. so it will execute command only if something change on code level otherwise it use the cache file.
# It will execute all layer from particular starting point where it found the changes.

# docker --help
# docker run -p 3000:80 -d {image_id} // To run container in ditached mode.
# docker start {container_name} // Restart the container
# docker attach {container_name} // Attach to container if ditached. Attached mode used to see logs.
# docker logs {container_name} // To get log history
# docker logs -f {container-name} // Attach to container if ditached.
# docker start -a {container_name} // Restart with attached mode.


# docker rm {container_name} {container_name} {container_name} ...
# docker container prune

# docker images
# docker rmi {image_id} {image_id} {image_id} ...
# docker image prune
# docker image prune -a

# docker run -p 3000:80 -d -rm {image_id} // This command will automatically remove the container when we stop the process
# docker image inspect {image_id}


# Copy file

# docker cp dummy/. {container_name}:/test // copy file from local to container
# docker cp {container_name}:/test dummy // copy file from container to local

# Add custom name to container / image

# docker run -p 3000:80 -d -rm --name {custom_name} {image_id}
# docker build -t {image_name}:{tag_name_or_version} .
# docker run -p 3000:80 {image_name}:{tag_name_or_version}
# docket tag {repo_name}:{tag_name} {repo_name} // Rename image tag and repository