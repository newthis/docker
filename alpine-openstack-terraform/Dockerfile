# 1)
# docker run --rm -it alpine:3.8 ash
# ...

# 2)
# docker build -t daggerok/devops .
# docker run --rm -it daggerok/devops
# ...

FROM alpine:3.8
RUN apk add --upgrade --no-cache ca-certificates \
                                 wget \
 && apk add --upgrade --no-cache musl-dev \
                                 libffi-dev \
                                 openssl-dev \
                                 readline-dev \
 && apk add --upgrade --no-cache gcc \
                                 py2-cffi \
                                 python-dev \
                                 python2-tkinter \
                                 py2-netifaces \
                                 py-setuptools \
                                 py2-pip \
 && pip install --upgrade pip \
 && pip install --upgrade python-openstackclient \
 && apk add --upgrade --no-cache git terraform \
 && apk del --purge --no-cache ca-certificates \
                               wget \
                               musl-dev \
                               libffi-dev \
                               python-dev \
                               openssl-dev \
                               readline-dev \
                               py-setuptools \
                               py2-cffi \
                               py2-netifaces \
                               python2-tkinter \
                               gcc \
                               py2-pip \
 && rm -rf /var/cache/apk/*
CMD /bin/ash
