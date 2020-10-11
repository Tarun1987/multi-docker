# Specify base image
FROM node:alpine

# set working directory
WORKDIR '/app'

# copy package json file to working directory
COPY ./package.json ./

# run npm install
RUN npm install

# Copy other files than package.json
COPY . .

#run some command
CMD [ "npm", "run", "start" ]
