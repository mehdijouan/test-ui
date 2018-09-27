FROM node:alpine

COPY package.json package-lock.json ./

RUN npm set progress=false && npm config set depth 0 && npm cache clean --force
## Storing node modules on a separate layer will prevent unnecessary npm installs at each build
RUN npm i && mkdir /usr/app && cp -R ./node_modules ./usr/app

# Create app directory
WORKDIR /usr/app
# Install app dependencies
COPY src/ ./src
COPY *.json ./
COPY .babelrc .
RUN npm run build
#Expose port and start application
EXPOSE 4000
CMD [ "node", "dist/server.js" ]
