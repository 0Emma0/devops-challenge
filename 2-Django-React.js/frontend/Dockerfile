FROM node:12.19.0-alpine
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
ENV ENDPOINT=http://localhost:8000/api/requests-loan/
COPY package*.json ./
RUN npm install
COPY . ./
EXPOSE 3000
CMD ["npm", "start"]
