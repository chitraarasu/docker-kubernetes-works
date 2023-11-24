FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=123456

CMD [ "npm", "start" ]


# Create network
# docker network create goals-net

# Start mongo container. /db required for mongodb, please refer doc for more details.
# docker run -d --rm --network goals-net --name mdb -v data:/data/db -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=123456 mongo  

# Build backend image 
# docker build -t goals-back-image .

# Start backend container
# docker run -d -v $(PWD):/app -v logs:/app/logs -v /app/node_modules -p 80:80 --rm --network goals-net --name goals-back-cont goals-back-image
# docker run -e MONGODB_USERNAME=admin -e MONGODB_PASSWORD=123456 -d -v $(PWD):/app -v logs:/app/logs -v /app/node_modules -p 80:80 --rm --network goals-net --name goals-back-cont goals-back-image