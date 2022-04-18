##########################
## Builder Container
##########################
FROM node:17.9.0-alpine3.14 as builder

WORKDIR /storybook-tutorial-for-react

COPY package.json package-lock.json ./

RUN npm i --no-progress

COPY . .

RUN npm run build

##########################
## Application Container
##########################
FROM node:17.9.0-alpine3.14

WORKDIR /storybook-tutorial-for-react

COPY --from=builder /storybook-tutorial-for-react ./

CMD ["npm", "run", "start"]
