FROM node:22.17-slim AS builder
WORKDIR /app
COPY package.json package-lock.json ./
COPY pkgs/my-lib-1.0.0.tgz ./pkgs/my-lib-1.0.0.tgz
RUN npm install -S ./pkgs/my-lib-1.0.0.tgz
RUN npm install
COPY index.js .



FROM node:22.17-slim
WORKDIR /app
COPY --from=builder /app /app
CMD ["node", "index.js"]
