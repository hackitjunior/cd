FROM node:10.17.0-alpine
WORKDIR /api
COPY package*.json /api/
COPY . /api/
RUN npm install -g nodemon
CMD ["npm", "run","start:dev"]