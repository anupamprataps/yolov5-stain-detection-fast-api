FROM tiangolo/uvicorn-gunicorn:python3.9-slim

LABEL maintainer="team-RC"
RUN apt-get update && apt-get install -y
RUN apt-get install libgl1 -y

RUN mkdir /yolov5-fastapi

COPY yolov5/requirements.txt /yolov5-fastapi

COPY . /yolov5-fastapi

WORKDIR /yolov5-fastapi

RUN pip install -r requirements.txt

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]