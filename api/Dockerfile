FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./
COPY nx.json ./
COPY tsconfig.base.json ./

# Install dependencies
RUN npm ci --only=production

# Copy source code
COPY api/ ./api/
COPY libs/ ./libs/

# Build the application
RUN npm run build:api

EXPOSE 3333

CMD ["node", "dist/api/main.js"]