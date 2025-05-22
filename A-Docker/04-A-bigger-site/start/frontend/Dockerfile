FROM node:alpine AS final

ENV NODE_ENV=production
ENV PORT=3000

WORKDIR /app

COPY package.json .

# at build time:
# set the current directory to `/app` or any convinient name
# copy the manifest file: package.json into this directory
# from a shell, run `npm install`
# copy the content into place
# let traffic flow in on port 3000
# set the environment variable `BACKEND` to `http://backend:5000`

COPY . .

EXPOSE 3000

ENV BACKEND=http://backend:5000

CMD ["npm", "start"]
