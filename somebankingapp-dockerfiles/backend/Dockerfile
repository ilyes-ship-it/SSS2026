FROM python:3.11-slim
WORKDIR /webapp
RUN pip install --no-cache-dir \
    fastapi \
    sqlalchemy \
    uvicorn
COPY . .
CMD ["python", "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]