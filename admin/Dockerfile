FROM nginx
RUN rm -rf /usr/share/nginx/html/index.html
COPY index.html .
ENV VITE_BACKEND_URL = "http://localhost:4000"
USER nginx
CMD ["nginx", "-g", "daemon off;"]
