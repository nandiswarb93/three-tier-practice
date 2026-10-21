# FROM nginx
# RUN rm -rf /usr/share/nginx/html/index.html
# COPY index.html .
# ENV VITE_BACKEND_URL = "http://54.147.125.97:4000"
# USER nginx
# CMD ["nginx", "-g", "daemon off;"]


FROM node:20-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]