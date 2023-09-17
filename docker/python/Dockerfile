FROM python:3.10

ENV PYTHONUNBUFFERED 1

WORKDIR /app

COPY . /app

RUN pip install --upgrade pip

RUN  pip install --upgrade setuptools

RUN pip install -r requirements.txt

CMD ["./docker/python/wait-for-it.sh", "postgres_db:5432", "--", "gunicorn", "--bind", "0.0.0.0:8000", "Blog_main.wsgi"]



RUN apt-get update && apt-get install -y netcat-openbsd

ENTRYPOINT ["./docker/python/entrypoint.sh"]