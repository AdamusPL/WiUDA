FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .
COPY requirements_test.txt .

RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --no-cache-dir -r requirements_test.txt

COPY *.py .
COPY ./utils .
COPY ./templates .
COPY ./static .

EXPOSE 8000

CMD ["python", "app.py"]
