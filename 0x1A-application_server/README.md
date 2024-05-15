# Deployment to development envuronment
- installing python3 and pip
```
sudo apt update
sudo apt install python3
sudo apt install python3-pip
```
- install flask

```
pip3 install Flask
```

- clone the project

- run the application inside the application root directoryy

```
python3 -m web_flask.0-hello_route
```
- install gUnicorn

```
pip install gunicorn

```
- run the application with gunicorn

```
gunicorn --bind 0.0.0.0:5000 web_flask.0-hello_route:app
```

### How it works
- The application server served the application on a port
- The web server listen for http request
- The web server is configure to proxy the request to the location where application server served the backend files
```
 location /airbnb-onepage/ {
        include proxy_params;
    proxy_pass http://localhost:5000/;
    }
```
- When /airbnb-onepage/ is visited, goto http://localhost:5000/;

