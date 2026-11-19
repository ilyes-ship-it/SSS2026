FROM python:3.11-slim
RUN apt-get update && apt-get install -y --no-install-recommends git \
    && rm -rf /var/lib/apt/lists/*
WORKDIR /src
RUN git clone https://github.com/mmenapace/SomeBankingApp .
WORKDIR /src/backend
RUN pip install --no-cache-dir \
    fastapi \
    sqlalchemy \
    uvicorn
CMD ["python", "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]