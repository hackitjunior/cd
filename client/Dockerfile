FROM node:12.14.0-alpine
WORKDIR /client
COPY . /client/
RUN npm install
RUN npm install -g @angular/cli@8.3.20
EXPOSE 80
CMD ["ng","serve","--host", "0.0.0.0"]