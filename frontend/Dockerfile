FROM nginx
RUN rm -rf /usr/share/nginx/html/index.html
COPY index.html .
ENV VITE_BACKEND_URL = "http://localhost:4000"\
VITE_RAZORPAY_KEY_ID = 'rzp_test_RxMg6BmfjIIwlZ'
USER nginx
CMD ["nginx", "-g", "daemon off;"]
