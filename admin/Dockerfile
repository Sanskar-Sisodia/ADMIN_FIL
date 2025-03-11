# Use official Node.js LTS image
FROM node:20

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first (for better caching)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install && npm install webpack@5 webpack-cli@5 --save-dev

# Copy the rest of the application files
COPY . .

# Build the Next.js project
RUN NODE_OPTIONS="--max-old-space-size=8192" npm run build

# Expose port 3000 for Next.js
EXPOSE 3000

# Start the Next.js server
CMD ["npm", "start"]
