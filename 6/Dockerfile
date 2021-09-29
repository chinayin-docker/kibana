#
#--------------------------------------------------------------------------
# kibana 6.8
#--------------------------------------------------------------------------
#

ARG ES_VERSION=6.8.19
FROM kibana:${ES_VERSION}
LABEL maintainer="chinayin <whereismoney@qq.com>"

USER root

ARG CHANGE_SOURCE=true
ENV CHANGE_SOURCE ${CHANGE_SOURCE}
ARG TZ=Asia/Shanghai
ENV TZ ${TZ}
RUN if [ ${CHANGE_SOURCE} = true ]; then \
    mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo_bak && \
    curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo \
;fi && ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime && echo "${TZ}" > /etc/timezone; \

ARG PLUGIN_VERSION=6.8.19
RUN set -eux \
    && yum update -y \
    ## alias
    && printf "alias ls='ls --color=auto'\nalias ll='ls -l --color=auto'\nalias l='ls -lA --color=auto'" >> /etc/profile.d/alias.sh \
    ## set limits.conf
    && printf "* soft nofile 65536\n* hard nofile 65536\n" >> /etc/security/limits.conf \
    && printf "elasticsearch soft memlock unlimited\nelasticsearch hard memlock unlimited\n" >> /etc/security/limits.conf \
    ## set sysctl.conf
    && printf "vm.max_map_count=262144" >> /etc/sysctl.conf \
    && printf "fs.file-max=65536" >> /etc/sysctl.conf \
    ## Install plugin
    ## Clean up
    && yum clean all

USER kibana
