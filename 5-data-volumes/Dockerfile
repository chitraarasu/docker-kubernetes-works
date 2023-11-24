FROM node

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . .

# Read this env dec after rest of the command
# We can use declate the arg value. You can i add this line anywhere but it will re-run every cmd after this line if the value assing on build time.
ARG DEFAULT_PORT=80 

# we can also assing value on build time
# docker build -t {image_name}:{tag_name} --build-arg DEFAULT_PORT=8000 .


# Read this env dec after rest of the command
# We can use declate the env value
ENV PORT=$DEFAULT_PORT  

# Specifying env value on run time. we can use --env or -e
# docker run -d -p 3000:8000 --env PORT 8000 --rm --name feedback-node -v feedback:/app/feedback -v $(PWD):/app:ro -v /app/node_modules feedback-app:volumes

# Specifying env file on run time.
# docker run -d -p 3000:8000 --env-file ./.env --rm --name feedback-node -v feedback:/app/feedback -v $(PWD):/app:ro -v /app/node_modules feedback-app:volumes


EXPOSE $PORT

# VOLUME [ "/app/feedback" ] // this will create anonymous volue it will be deleted once container stopped.

CMD [ "npm", "start" ] 
# this code will get execute only on run time.

# docker build -t {repo_name}:{tag_name} .
# docker run -d -p 3000:80 --rm --name {custom_container_name} -v {volume_name}:/app/feedback {repo_name}:{tag_name}

# docker volumes ls
# docker volume rm {vol_name}

# Bind Mounts

# This will listen for changes on code. It will reflect the changes immediately on output.
# docker run -d -p 3000:80 --rm --name feedback-node -v feedback:/app/feedback -v $(PWD):/app -v /app/node_modules feedback-app:volumes

# Read Only Binds - This binds method reflect the changes from local to container and vice versa. To prevent writing on local, we need to use :ro read only.
# docker run -d -p 3000:80 --rm --name feedback-node -v feedback:/app/feedback -v $(PWD):/app:ro -v /app/node_modules feedback-app:volumes