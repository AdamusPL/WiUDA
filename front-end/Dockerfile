# ADD YOUR OWN DOCKERFILE
#frontend
FROM node:20 AS build-frontend
WORKDIR /frontend
COPY frontend/package*.json ./
RUN npm install
COPY frontend/ .
RUN npm run build

#backend
FROM python:3.11-slim
WORKDIR /app

COPY backend/requirements.txt .
RUN pip install -r requirements.txt

COPY backend/ .
COPY --from=build-frontend /frontend/build ./static/

EXPOSE 5000
CMD ["python", "app.py"]