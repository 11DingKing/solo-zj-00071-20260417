FROM node:16

WORKDIR /app

RUN apt-get update && apt-get install -y \
    g++ \
    gcc \
    openjdk-11-jdk \
    python3 \
    && rm -rf /var/lib/apt/lists/*

COPY package*.json ./

RUN npm install

COPY . .

RUN mkdir -p /app/submissions

EXPOSE 8081

CMD ["npm", "start"]
