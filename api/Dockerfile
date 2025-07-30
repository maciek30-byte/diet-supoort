# Use latest LTS version of Node (currently 22)
FROM node:22-alpine

# Set working directory
WORKDIR /usr/src/api

# Install all dependencies (including dev)
COPY package*.json ./
RUN pnpm install

# Copy the rest of the code
COPY . .

# Expose port (Express default)
EXPOSE 3000

# Run in dev mode
CMD ["npm", "run", "dev"]
