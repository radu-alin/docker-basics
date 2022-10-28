FROM node:gallium

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . . 

EXPOSE 8080

ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret

RUN adduser node root

# set proper permissions
RUN chown -R node /app
RUN chmod -R 775 /app
RUN chown -R node:root /app

#specify the user under which pm2 will run. see https://github.com/keymetrics/docker-pm2/issues/21#issuecomment-678784048
USER node

# CMD ["node", "app.js"]
CMD ["npm", "start"]





