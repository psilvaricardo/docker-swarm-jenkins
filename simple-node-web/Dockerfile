# Use an existing docker image as a base
# By the time of writting any newer versions beyond alpine 14 are giving some issues
FROM node:14-alpine

# Specifying a working directory for our app will prevent any issues between the filesystem 
# inside the docker image and all the files and folders required by our application.
# A good practice is to set the WORKDIR to a location that is writable by the app user inside the container. 
WORKDIR /usr/src/simpleweb

# Copy all the required files into the docker image
# for the first parameter, it is relative to the pwd where the docker build was executed
COPY ./package.json ./
RUN npm install

# This way, in case we make any change on our application's file, we don't have to rebuild everything.
# This will be improved later.
COPY ./ ./

# default command
CMD [ "npm", "start" ]
