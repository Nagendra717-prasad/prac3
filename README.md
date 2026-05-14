# prac3



docker –version 
docker info 
docker ps
docker ps –a 
docker images 
docker pull ubuntu 
docker run -it ubuntu 
docker stop <container_id>  
docker rm <container_id> 
docker rmi <image_id> 

create Dockerfile 

FROM ubuntu:latest
RUN apt-get update && apt-get install -y curl
CMD ["bash"]

ren Dockerfile.txt Dockerfile

docker build -t <image_name>  .
docker pull ubuntu 
docker run -it ubuntu
exit

docker pull alpine 
docker run -it alpine 
exit

docker pull centos:7
docker pull debian 
docker pull fedora 

from flask import Flask 
app = Flask(__name__) 

@app.route('/') 
def hello_world(): 
    return 'Hello, Docker!' 

if __name__ == '__main__': 
    app.run(host='0.0.0.0', port=8080)

FROM python:3.8-slim
WORKDIR /app
COPY app.py .
RUN pip install flask
EXPOSE 8080
CMD ["python", "app.py"]

docker build -t flask-app .
docker run -p 8080:8080 flask-app

http://localhost:8080/

docker tag flask-app nagendra2005/python-flask-app1
docker push nagendra2005/python-flask-app1
docker pull nagendra2005/python-flask-app1
docker run -p 8080:8080 nagendra2005/python-flask-app1

http://localhost:8080/
