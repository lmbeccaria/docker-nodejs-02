FROM node:alpine
WORKDIR	"/app"
COPY ./package.json	./
RUN npm install -g react-scripts --unsafe-perm=true --allow-root
RUN npm install --unsafe-perm=true --allow-root
COPY . .
CMD	["npm", "run", "start"]
