# syntax usage (node application with API)
#
# docker build -t goals-node .
# docker run --name mongodb -v data:/data/db --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=max -e MONGO_INITDB_ROOT_PASSWORD=secret mongo
# docker run --name goals-backend -v /Users/steven/development/backend:/app -v logs:/app/logs -v /app/node_modules --rm -d -p 80:80 -e MONGODB_USERNAME=max --network goals-net goals-node
#
# mongodb://host.docker.internal:27017/course-goals
# if network
# mongodb://mongodb:27017/course-goals
# if username and password was set, use
# mongodb://max:secret@mongodb:27017/course-goals?authSource=admin
# `mongodb://${process.env.MONGODB_USERNAME}:{process:env.MONGODB_PASSWORD}@mongodb:27017/course-goals?authSource=admin`
# 
# Build Dockerfile
# docker build -t goals-node .

FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret

CMD [ "node", "app.js" ]

# if use nodemon devDepencies
# change to command of
# CMD [ "npm", "start" ]