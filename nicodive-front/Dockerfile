FROM node:lts-alpine as build-stage
WORKDIR /app
COPY . /app
ENV DOMAIN nicodive.net
RUN npm install
RUN npm run build
EXPOSE 3000
ENV HOST 0.0.0.0
CMD ["npm", "run", "start"]