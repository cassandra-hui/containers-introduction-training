


# DOCKER_DEFAULT_PLATFORM=linux/amd64
# docker build -t deseq2 .


FROM rocker/r2u:jammy

RUN install2.r \
    DESeq2 \
    optparse \
    apeglm \
    IHW \
    limma \
    data.table \
    ggrepel \
    pheatmap \
    stringr

COPY test_deseq2.R /opt 

ENV PATH=/opt:$PATH

# note that if you want to be able to combine the two
# both ENTRYPOINT and CMD need to written in the exec form
ENTRYPOINT ["test_deseq2.R"]

# default option (if positional arguments are not specified)
CMD ["--rows", "100"]