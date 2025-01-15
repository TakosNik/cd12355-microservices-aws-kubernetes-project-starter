FROM python:3.10-slim-buster

WORKDIR /app

COPY . /app
COPY requirements.txt .

ENV DB_USERNAME=myuser
ENV DB_PASSWORD=${POSTGRES_PASSWORD}
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5432
ENV DB_NAME=mydatabase

RUN apt update -y
RUN apt install build-essential libpq-dev -y
RUN pip install --upgrade pip setuptools wheel

RUN pip install -r requirements.txt

EXPOSE 5153

CMD ["python", "app.py"]