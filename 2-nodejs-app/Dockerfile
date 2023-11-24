FROM node

WORKDIR /app

COPY . /app

RUN npm install

EXPOSE 80

CMD [ "node", "server.js" ]


# docker ps
# docker ps -a
# docker rm {name}
# docker build .
# docker run -p 3000:{port} {name}
# docker stop {name}