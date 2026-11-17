FROM node:26-alpine
RUN apk add --no-cache git
WORKDIR /src
RUN git clone https://github.com/mmenapace/SomeBankingApp .
WORKDIR /src/frontend
RUN npm install
CMD ["npx", "ng", "serve", "--host", "0.0.0.0"]