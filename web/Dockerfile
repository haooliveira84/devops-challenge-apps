FROM node:10-alpine

RUN apk add --no-cache git

# Set environment variables
ENV USER_DIR=/usr/src/app
ENV NODE_ENV production
ENV HOST 0.0.0.0
ENV PORT 3000

RUN mkdir -p $USER_DIR
RUN chown node:node "$USER_DIR"

WORKDIR $USER_DIR

RUN yarn cache clean

COPY package*.json ./

RUN npm install

# Bundle app source
COPY . .

EXPOSE $PORT

CMD ["npm", "start"]
