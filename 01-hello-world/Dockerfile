FROM mhart/alpine-node:9
WORKDIR /app
COPY package.json package-lock.json /app/
RUN npm install --production
COPY index.js /app/
CMD [ "npm", "start" ]
