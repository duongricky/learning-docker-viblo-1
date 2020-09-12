FROM node:12.18-alpine

WORKDIR /app

RUN npm install -g pm2

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install --production --silent

COPY . .

# ----- Nếu UID:GID là 1000:1000
# USER node
# RUN chown -R node:node /app
# ----- Nếu không thì
RUN addgroup -g 20 appgroup
RUN adduser -D -u 501 appuser -G appgroup
RUN chown -R appuser:appgroup /app
USER appuser
# ---------------------------------------

CMD ["pm2-runtime", "ecosystem.config.js", "--env", "production"]