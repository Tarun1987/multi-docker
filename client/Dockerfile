# Specify base image
FROM node:alpine as builder

# set working directory
WORKDIR '/app'

# copy package json file to working directory
COPY ./package.json ./

# run npm install
RUN npm install

# Copy other files than package.json
COPY . .

#build files inside the container
RUN npm run build

# Using multi step docker builds
FROM nginx

# Expose port 3000 from nginx
EXPOSE 3000

# Copy default configuration to nginx container folder
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# copy files from above build image to nginx folder
COPY --from=builder /app/build /usr/share/nginx/html
