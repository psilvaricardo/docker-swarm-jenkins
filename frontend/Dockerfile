
FROM node:16-alpine as webapp

WORKDIR /usr/src/frontend

COPY ./package.json ./

RUN npm install

COPY . .

# Starts up a PRODUCTION server
CMD [ "npm", "run", "build" ]


FROM nginx

WORKDIR /usr/src/frontend

EXPOSE 80

COPY --from=webapp /usr/src/frontend/build /usr/share/nginx/html
