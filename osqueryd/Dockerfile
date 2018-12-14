FROM centos:7
MAINTAINER Dave Quick <dave.quick@oracle.com>
RUN rpm -ivh https://osquery-packages.s3.amazonaws.com/centos7/noarch/osquery-s3-centos7-repo-1-0.0.noarch.rpm && \
    yum install -y osquery

# Copy the default osquery.conf (However, a custom conf should be specified
# with `docker run -v osquery.conf:/etc/osquery/osquery.conf imagename`
# COPY osquery.example.conf /etc/osquery/osquery.conf

# Copy any custom query packs and such here to bake into the image.
CMD ["osqueryd", "--config_path=/etc/osquery/osquery.conf", "--verbose"]

