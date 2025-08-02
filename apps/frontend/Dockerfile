FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./
COPY nx.json ./
COPY tsconfig.base.json ./

# Install all dependencies
RUN npm ci

# Copy source code
COPY apps/frontend/ ./apps/frontend/
COPY libs/ ./libs/

# Development mode - use nx serve for hot reload
EXPOSE 4200

CMD ["npm", "run", "serve:frontend"]