FROM python:3.12

ENV PYTHONDONTWRITEBYECOODE=1   
ENV PYTHONUNMUFFERED=1  

WORKDIR /code  

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt 

COPY . .

RUN python manage.py collectstatic --noinput

CMD ["gunicorn", "django_docker.wsgi:application","--config", "gunicorn.conf.py"]