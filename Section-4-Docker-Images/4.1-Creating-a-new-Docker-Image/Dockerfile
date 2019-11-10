FROM ubuntu
RUN apt-get update
RUN apt-get install python -y
RUN apt-get install python-pip -y
RUN pip install flask
COPY app.py /opt/app.py
EXPOSE 8888
ENTRYPOINT FLASK_APP=/opt/app.py flask run --host=0.0.0.0