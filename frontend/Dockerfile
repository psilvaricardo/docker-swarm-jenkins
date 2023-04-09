FROM node:16-alpine as webapp

WORKDIR '/frontend/'

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
WORKDIR '/usr/src/frontend'
RUN ls -ltra
EXPOSE 80
COPY --from=webapp /frontend/build /usr/share/nginx/html
