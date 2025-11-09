FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package metadata and install dependencies
COPY package*.json ./
RUN npm install --production

# Copy application source
COPY . .

# Ensure directory for SQLite DB exists and persistable
RUN mkdir -p /app/data
VOLUME ["/app/data"]

# Expose backend port
EXPOSE 5000

ENV NODE_ENV=production

# Start the application
CMD ["npm", "start"]
