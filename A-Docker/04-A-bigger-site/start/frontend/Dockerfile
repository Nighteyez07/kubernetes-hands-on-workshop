FROM node:alpine

ENV NODE_ENV=production
ENV PORT=3000

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

ENV BACKEND=http://backend:5000

CMD ["npm", "start"]
