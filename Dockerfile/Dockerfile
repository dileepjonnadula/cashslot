FROM python:3.12-slim
WORKDIR /srv
COPY cashslot-source.zip /tmp/cashslot-source.zip
RUN python -c "import zipfile; zipfile.ZipFile('/tmp/cashslot-source.zip').extractall('/srv')"
RUN pip install --no-cache-dir -r requirements.txt
RUN useradd -m svc && chown -R svc /srv
USER svc
EXPOSE 8000
CMD ["sh", "-c", "uvicorn app.main:app --host 0.0.0.0 --port ${PORT:-8000} --workers ${WEB_CONCURRENCY:-1}"]
