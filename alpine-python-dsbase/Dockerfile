FROM python:3.6.4-alpine3.7

MAINTAINER Ryan White <ryan.white4@canada.ca>

RUN apk add --update gcc \
                     g++ \
                     libc-dev \
                     libstdc++ \
                     gfortran \
                     libgfortran \
                     openblas-dev && rm -rf /var/cache/apk/*


RUN pip install numpy && \
    pip install pandas && \
    pip install scipy



