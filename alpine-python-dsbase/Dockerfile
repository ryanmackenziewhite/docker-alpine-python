FROM python:3.6.4-alpine3.7

MAINTAINER Ryan White <ryan.white4@canada.ca>

RUN apk add --update gcc \
                     g++ \
                     libc-dev \
                     libstdc++ \
                     gfortran \
                     libgfortran \
                     openblas-dev && rm -rf /var/cache/apk/*

RUN pip install --upgrade pip 

RUN pip install numpy && \
    pip install pandas && \
    pip install scipy

RUN pip install cython    

RUN apk add --update freetype-dev \
                     libpng && rm -rf /var/cache/apk/*

RUN pip install ipython && \
    pip install matplotlib && \
    pip install seaborn

RUN pip install scikit-learn && \
    pip install statsmodels


