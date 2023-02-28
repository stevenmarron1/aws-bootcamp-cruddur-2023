FROM python:3.10-slim-buster

WORKDIR /backend-flask
# Outside container -> Inside Container
# This contains the libraries you want to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install PY libraries used for the app
RUN pip3 install -r requirements.txt

#Outside Container -> Inside Container
# . means everything in the current dir
#.- first period /backend-flask (outside container)
# . - second period /backend-flask (inside container)
COPY . .
# Set Environment Variables
# Inside conatiner and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# Command
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]