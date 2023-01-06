# docker build -t goals-react .
# docker run --name goals-frontend -v /Users/steven/development/frontend/src:/app/src --rm -p 80:80 -d --network goals-net goals-node
#
# All http://localhost/... needs to change to http://goals-backend/... if run in separate container

FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD [ "npm", "start" ]