# pull the Node.js Docker image
FROM node

# create the directory inside the container
WORKDIR /usr/src/app

# copy the package.json files from local machine to the workdir in container
COPY package*.json ./

ADD start.sh /

RUN chmod +x /start.sh

# run npm install in our local machine
RUN npm install pm2 -g
RUN npm install

# copy the generated modules and all other files to the container
COPY . .

# our app is running on port 5000 within the container, so need to expose it
EXPOSE 7000-8000

# the command that starts our app
CMD ["./start.sh"]