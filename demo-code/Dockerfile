FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

# ddtrace-run auto-instruments Django for APM traces without code changes.
CMD ["ddtrace-run", "python", "manage.py", "runserver", "0.0.0.0:8000"]
