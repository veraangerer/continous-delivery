# continous-delivery

``npm init hello-world``
``touch index.js``

## add this code to index.js

``const express = require('express')
const app = express()

app.get('/', (req, res) => res.send('Hello World!'))

app.listen(3000, () => console.log('Example app listening on port 3000!'))``

``npm install express --save``

## add start script to package.json

## create Dockerfile and .dockerignore to ignore node_modules/
``touch Dockerfile``

add this to dockerfile: 
``
FROM mhart/alpine-node:9
WORKDIR /app
COPY package.json package-lock.json /app/
RUN npm install --production
COPY index.js /app/
CMD [ "npm", "start" ]
``

``touch .dockerignore``

add node_modules/ to .dockerignore

## build docker image
``docker build -t hello-world .``

## list all docker images available
``docker images``

## run docker image
``docker run hello-world``

## send hello world to browser
``docker run -p3000:3000 - hello-world``
