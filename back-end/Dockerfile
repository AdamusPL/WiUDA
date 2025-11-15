FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .
COPY requirements_test.txt .

RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --no-cache-dir -r requirements_test.txt

COPY *.py .
COPY ./resources .

EXPOSE 5000

CMD python app.py
# CMD ["python", "app.py"]
