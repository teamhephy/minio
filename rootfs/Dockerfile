FROM minio/mc:RELEASE.2019-02-06T20-26-56Z as mc

FROM minio/minio:RELEASE.2019-02-06T21-16-36Z

COPY --from=mc /usr/bin/mc /usr/bin/mc

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

CMD ["/bin/boot"]
