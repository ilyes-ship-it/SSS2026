FROM node:26-alpine
RUN apk add --no-cache git
WORKDIR /src
RUN git clone https://github.com/mmenapace/SomeBankingApp .
WORKDIR /src/frontend
RUN sed -i "s#http://127.0.0.1:8000#/api#" src/app/core/services/bank.services.ts
RUN npm install
CMD ["npx", "ng", "serve", "--host", "0.0.0.0"]