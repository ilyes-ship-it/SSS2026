FROM node:26-alpine
WORKDIR /webapp
COPY package*.json ./
RUN npm install
COPY . .
CMD ["npx", "ng", "serve", "--host", "0.0.0.0"]