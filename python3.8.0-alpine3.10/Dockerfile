FROM python:3.8.0-alpine3.10
LABEL  maintainer "matsumoto.kodai"

WORKDIR /usr/src/app

RUN apk add pcre pcre-dev&& \
    apk add --virtual .build-deps gcc build-base linux-headers && \
    pip install --no-cache-dir uwsgi && \
    apk --purge del .build-deps

EXPOSE 8000

CMD [ "uwsgi", "--ini", "./uwsgi.ini" ]
