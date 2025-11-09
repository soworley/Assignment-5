# Build stage
FROM node:18-alpine AS build
WORKDIR /app

# Copy package files and install deps
COPY package*.json ./
RUN npm install

# Copy source and build production assets
COPY . .
RUN npm run build

# Production stage using nginx
FROM nginx:alpine
# Copy built files from the build stage to nginx www dir.
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

# Run nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
