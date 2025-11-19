# Use official node LTS base image
FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Copy package files and install dependencies first (cache layer)
COPY package.json package-lock.json* ./
RUN npm ci --only=production || npm install --only=production

# Copy app code
COPY . .

# Expose port
EXPOSE 3000

# Default start command
CMD ["node", "index.js"]