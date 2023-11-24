FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD [ "npm", "start" ]

# Build backend image 
# docker build -t goals-front-image .

# Start backend container
# docker run -v $(PWD)/src:/app/src -it -p 3000:3000 --rm --network goals-net --name goals-front-cont goals-front-image