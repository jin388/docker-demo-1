FROM node:14-alpine AS builder
WORKDIR /opt/app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build api

FROM node:14-alpine
WORKDIR /opt/app
COPY package.json ./
RUN npm install --only=production
COPY --from=builder /opt/app/dist/apps/api ./dist
CMD ["node", "./dist/main.js"]