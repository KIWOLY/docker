FROM node:20-alpine

# 1. Create non-root user (security best practice)
RUN addgroup app && adduser -S -G app app

# 2. Set working directory
WORKDIR /app

# 3. Copy package files first (for Docker cache)
COPY package*.json ./

# 4. Install dependencies
RUN npm install

# 5. Copy rest of the project files
COPY . .

# 6. Give ownership to non-root user
RUN chown -R app:app /app

# 7. Switch to non-root user
USER app

# 8. Expose Vite dev port
EXPOSE 5173

# 9. Start React dev server
CMD ["npm", "run", "dev"]
