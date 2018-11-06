FROM alpine:latest
# 替换阿里云的源
RUN echo "http://mirrors.aliyun.com/alpine/latest-stable/main/" > /etc/apk/repositories
RUN echo "http://mirrors.aliyun.com/alpine/latest-stable/community/" >> /etc/apk/repositories
# 更新源、安装openssh 并修改配置文件和生成key 并且同步时间
RUN apk update && \
    apk upgrade && \
    apk add --no-cache openssh-server net-tools curl wget  tzdata openssh bash bash-doc bash-completion  && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    rm -rf /var/cache/apk/*  && \
    /bin/bash
