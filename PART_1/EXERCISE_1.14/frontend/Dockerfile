FROM node:16.20

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./

RUN npm install

# Bundle app source
COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm run build
RUN npm install -g serve

EXPOSE 5000
CMD ["serve", "-s", "-l", "5000", "build"]
