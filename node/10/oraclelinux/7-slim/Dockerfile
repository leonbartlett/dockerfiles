FROM oraclelinux:7-slim

LABEL maintainer="Linux Team <linuxgroup@atradius.com>"

RUN  curl -o /etc/yum.repos.d/public-yum-ol7.repo https://yum.oracle.com/public-yum-ol7.repo && \
     yum-config-manager --enable ol7_developer_nodejs10 ol7_oracle_instantclient && \
     yum -y install nodejs node-oracledb-node10  && \
     rm -rf /var/cache/yum && \
     echo /usr/lib/oracle/18.3/client64/lib > /etc/ld.so.conf.d/oracle-instantclient18.3.conf && \
     ldconfig

ENV PATH=$PATH:/usr/lib/oracle/18.3/client64/bin

CMD [ "node" ]
