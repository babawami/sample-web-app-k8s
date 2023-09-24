FROM nginx:latest

# Set the working directory in the container
WORKDIR /usr/share/nginx/html

# Remove the default Nginx welcome page
RUN rm -rf ./*

COPY index.html /usr/share/nginx/html/
COPY main.css /usr/share/nginx/html/
COPY main.js /usr/share/nginx/html/
COPY ./configs/config.json /usr/share/nginx/html/
EXPOSE 80

# Start Nginx when the container runs
CMD ["nginx", "-g", "daemon off;"]
