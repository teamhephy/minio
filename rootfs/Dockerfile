FROM minio/minio:RELEASE.2020-10-27T04-03-55Z

RUN wget https://dl.min.io/client/mc/release/linux-amd64/mc -O /bin/mc \
  && chmod +x /bin/mc

RUN adduser \
       -s /bin/sh \
       -D  \
       -h /home/minio \
       minio \
       minio

COPY . /

RUN mkdir /home/minio/.minio \
        && chown minio:minio /home/minio/.minio

USER minio

ENTRYPOINT ["/bin/boot"]
