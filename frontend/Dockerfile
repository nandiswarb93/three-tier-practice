# FROM nginx
# RUN rm -rf /usr/share/nginx/html/index.html
# COPY index.html .
# ENV VITE_BACKEND_URL = "http://localhost:4000"\
#     VITE_RAZORPAY_KEY_ID = "rzp_test_RxMg6BmfjIIwlZ"
# USER nginx
# CMD ["nginx", "-g", "daemon off;"]


# Stage 1: Build the React application
FROM node:22-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build


# Stage 2: Serve the production files using Nginx
FROM nginx:alpine

COPY --from=builder /app/dist/ /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]