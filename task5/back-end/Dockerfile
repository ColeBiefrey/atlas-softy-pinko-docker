# use latest Ubuntu image
FROM ubuntu:latest

# update slash upgrade system
RUN apt-get update && apt-get upgrade -y

# install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# remove EXTERNALLY-MANAGED if necessary to avoid errors
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# install flask using pip3
RUN pip3 install flask && pip3 install flask-cors

# set working directory to /app
WORKDIR /app

# copy Python script to container
COPY ./api.py /app/api.py

# expose port 5252
EXPOSE 5252

# run Flask application
CMD ["python3", "api.py"]