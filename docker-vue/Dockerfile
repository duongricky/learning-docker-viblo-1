# FROM node:13-alpine as build-stage
# WORKDIR /app
# COPY . .
# RUN npm install
# CMD ["npm", "run", "serve"]

# FROM nginx:1.17-alpine as production-stage
# COPY --from=build-stage /app/dist /usr/share/nginx/html

# CMD ["nginx", "-g", "daemon off;"]

FROM node:12.18-alpine
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "run", "serve"]