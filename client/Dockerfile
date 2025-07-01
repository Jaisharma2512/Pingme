#Building the React app first
From node:18 AS builder

#Making default work directory
WORKDIR /app
COPY . .
RUN yarn install
RUN yarn build

#RuNNING with NGINX
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]