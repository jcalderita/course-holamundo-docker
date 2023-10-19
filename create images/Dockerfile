FROM node:20.5.0-alpine3.18
RUN npm install -g pnpm
RUN addgroup react && adduser -S -G react react
USER react
WORKDIR /app/
RUN mkdir datos
COPY --chown=react package*.json .
RUN pnpm install
COPY --chown=react . .
ENV API=https://apiv1.miweb.com
EXPOSE 5173
CMD [ "pnpm", "run", "dev" ]