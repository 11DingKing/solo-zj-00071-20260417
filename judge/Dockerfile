FROM node:16-alpine

WORKDIR /app

RUN apk update && apk add --no-cache \
    g++ \
    gcc \
    openjdk11 \
    python3 \
    bash \
    coreutils \
    && rm -rf /var/cache/apk/*

ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk
ENV PATH="$JAVA_HOME/bin:${PATH}"

COPY package*.json ./

RUN npm install

COPY . .

RUN mkdir -p /app/submissions

EXPOSE 8081

CMD ["npm", "start"]
