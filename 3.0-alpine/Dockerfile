FROM redis:3.0-alpine

MAINTAINER Tommy Chen <tommy351@gmail.com>

RUN apk --update --no-cache add supervisor ruby ca-certificates openssl && \
  gem install --no-ri --no-rdoc redis && \
  REDIS_TRIB_PATH=/usr/local/bin/redis-trib && \
  wget https://raw.githubusercontent.com/antirez/redis/3.0/src/redis-trib.rb -O $REDIS_TRIB_PATH && \
  chmod +x $REDIS_TRIB_PATH

COPY start.sh /
VOLUME /data
WORKDIR /

EXPOSE 7000 7001 7002 7003 7004 7005

CMD ["/start.sh"]
