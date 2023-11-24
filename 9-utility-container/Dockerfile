FROM node:14-alpine 
# This is light weight node for util container

WORKDIR /app

ENTRYPOINT [ "npm" ]  
# this endpoint will be automatically added before the node command. By mistage if we executed some cmd to delete something on container means it will reflected on host machine too, so to prevent that we are declaring this endpoint.

# docker build -t node_utils .

# docker run -it -v $(PWD):/app node_utils npm init   
# this command bind the code on host maching and container code as same. With this you can execute any node cmd without installing node on host machine.

# docker run -it -v $(PWD):/app node_utils install /// After adding entry point no need to add npm in cmd.   
