# syntax=docker/dockerfile:1
FROM python:3.10.3-alpine3.15
WORKDIR /code
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
# hadolint ignore=DL3018
RUN apk add --no-cache gcc musl-dev linux-headers
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt
EXPOSE 5000
COPY app.py app.py
CMD ["flask", "run"]