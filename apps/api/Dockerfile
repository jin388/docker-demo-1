FROM node:14

WORKDIR /opt/app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build api

CMD ["node", "./dist/apps/api/main.js"]