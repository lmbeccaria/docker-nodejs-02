# First phase
FROM node:alpine as builder
WORKDIR	'/app'
COPY ./package.json ./
RUN npm install -g react-scripts --unsafe-perm=true --allow-root
RUN npm install --unsafe-perm=true --allow-root
COPY . .
RUN npm run build

# 2nd Phase. Expose port 3000 and copy everything from 1st phase
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
