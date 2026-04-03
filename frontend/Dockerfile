# ---------- Build Stage ----------
FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# ---------- Runtime Stage ----------
FROM node:20-alpine

WORKDIR /app

COPY --from=builder /app/dist ./dist

EXPOSE 5173

CMD ["npx", "serve", "-s", "dist", "-l", "5173"]
