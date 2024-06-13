Application Deployment Project: AirBnB Clone
In this project, I configured and deployed an AirBnB clone application using Nginx, Gunicorn, and Upstart. The project involved setting up both development and production environments, creating Nginx configurations to proxy requests, and ensuring the application runs continuously with Upstart.

Tasks 
Set up Development with Python

Configured the file web_flask/0-hello_route.py to set up the development environment for the application.
Set up Production with Gunicorn

Installed and configured Gunicorn to serve the application in a production environment using the same file from Task 1.
Serve a Page with Nginx

Created 2-app_server-nginx_config, an Nginx configuration file to proxy requests on the route /airbnb-onepage/ to the Gunicorn app running on port 5000.
Add a Route with Query Parameters

Created 3-app_server-nginx_config, an Nginx configuration file to proxy requests on the route /airbnb-dynamic/number_odd_or_even/<int:num> to the Gunicorn app running on port 5000.
Serve the API

Configured the API from AirBnB_clone_v3 to run on Gunicorn.
Created 4-app_server-nginx_config, an Nginx configuration file to proxy requests on the AirBnB API to the corresponding Gunicorn app.
Serve the Complete AirBnB Clone

Configured the complete AirBnB application from AirBnB_clone_v4 to run on Gunicorn and be served through Nginx.
Created 5-app_server-nginx_config, an Nginx configuration file to serve the static assets from web_dynamic/static/ on the Gunicorn AirBnB app.
Deploy the Application

Created gunicorn.conf, an Upstart script to start a Gunicorn process bound to port 5003, serving the content from Task 6.
Configured the Gunicorn process to spawn three worker processes and log errors to /tmp/airbnb-error.log and access logs to /tmp/airbnb-access.log.
Ensure No Service Interruption

Created 4-reload_gunicorn_no_downtime, a bash script to gracefully reload Gunicorn without any downtime.
