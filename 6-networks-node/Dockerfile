FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["node", "app.js"]

# 'mongodb://host.docker.internal:27017/swfavorites', // This will connect to host computer.
# 'mongodb://172.17.0.2:27017/swfavorites', // this connect to mongo container. "docker container inspect mongodb" use this to get mongo ip address.


# Create Network To Connect multiple container.
# docker network create {network_name} 
# docker run -d --name mongodb --network {network_name} mongo  // This will start mongo container on specified network.
# docker run -d --name {container_name} -d -rm -p 3000:3000 --network {network_name} . 
# 'mongodb://mongodb:27017/swfavorites', // this connect to mongo container. Code container and the mongo container should run under same network, then only is connect to mongodb container,
