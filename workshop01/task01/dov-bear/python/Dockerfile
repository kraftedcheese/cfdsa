FROM python:3.9

LABEL name==dov-bear
ARG APP_DIR=/app
WORKDIR ${APP_DIR}
COPY ./ .

RUN python -m pip install -r requirements.txt

ENV PORT=5000 INSTANCE_NAME="ups_la_sir" INSTANCE_HASH="420420420"

EXPOSE ${PORT}

HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
    CMD curl -s -f http://localhost:${PORT}/healthz > /dev/null || exit 1

ENTRYPOINT python main.py