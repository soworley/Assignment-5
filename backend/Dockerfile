cd backened
npm install
npm start
# Use Node 18 Alpine image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all backend files
COPY . .

# Create directory for SQLite database
RUN mkdir -p /app/data

# Expose backend port
EXPOSE 5000

# Start the app
CMD ["npm", "start"]
