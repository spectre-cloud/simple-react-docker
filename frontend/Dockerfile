FROM node:alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build 

FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html 
# here the first image application results is been used
#80 is default nginx port
