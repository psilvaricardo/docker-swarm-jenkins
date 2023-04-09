FROM base AS builder
WORKDIR /usr/src/frontend

FROM node:16-alpine as webapp

COPY ./package.json ./

RUN npm install

COPY . .

# changing the ownership of the node_modules directory to the same 
# user running the npm command to avoid permission issues
#RUN chown -R node:node /usr/src/frontend/node_modules
#USER node

# Starts up a PRODUCTION server
CMD [ "npm", "run", "build" ]


FROM nginx
RUN ls -la
EXPOSE 80
COPY --from=webapp /build /usr/share/nginx/html
