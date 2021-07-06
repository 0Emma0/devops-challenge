FROM python:3.7.11-stretch

ENV PYTHONUNBUFFERED 1
#ENV SECRET_KEY=PfhE*M+H#4H=M^%@

WORKDIR /app

COPY requirements.txt .

RUN apt update && apt install -y gcc \
&& pip install -r requirements.txt

COPY . .

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]