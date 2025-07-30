# Use latest LTS Node.js (for vite dev server)
FROM node:22-alpine

# Set working directory
WORKDIR /usr/src/frontend

# Install all dependencies
COPY package*.json ./
RUN pnpm install

# Copy remaining files
COPY . .

# Expose Vite dev server port
EXPOSE 5173

# Start Vite in dev mode
CMD ["npm", "run", "dev"]
