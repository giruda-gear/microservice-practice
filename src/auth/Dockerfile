FROM python:3.12-slim-bullseye

RUN apt-get update \
  && apt-get install -y pkg-config \
  --no-install-recommends --no-install-suggests \
  build-essential default-libmysqlclient-dev \
  && pip install --no-cache-dir --upgrade pip

WORKDIR /app
COPY ./requirements.txt /app
RUN pip install --no-cache-dir --requirement /app/requirements.txt
COPY . /app

EXPOSE 5001

CMD ["python3", "server.py"]