FROM node:18-alpine as builder
WORKDIR /next-app

# Copy both package.json and package-lock.json
COPY package.json package-lock.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:18-alpine as runner
WORKDIR /next-app
COPY --from=builder /next-app/package.json .
# Exclude package-lock.json from the final image
COPY --from=builder /next-app/next.config.mjs ./
COPY --from=builder /next-app/public ./public
COPY --from=builder /next-app/.next/standalone ./
COPY --from=builder /next-app/.next/static ./.next/static
EXPOSE 3000
ENTRYPOINT ["npm", "start"]