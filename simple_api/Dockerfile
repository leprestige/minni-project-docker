FROM python:3.11-slim

LABEL maintainer="Eric Tsafack"

COPY requirements.txt student_age.py /

RUN apt-get update && \
    apt-get install -y \
    gcc \
    g++ \
    build-essential \
    python3-dev \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip
RUN pip install -r /requirements.txt

VOLUME ["/data"]

EXPOSE 5000

CMD ["python3", "/student_age.py"]