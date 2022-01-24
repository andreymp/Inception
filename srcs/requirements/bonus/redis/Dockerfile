FROM debian:buster
EXPOSE 6379
RUN apt-get update
RUN apt-get install -y redis-server vim
RUN touch /etc/redis.conf
RUN sed -i "s|bind 127.0.0.1|#bind 127.0.0.1|g" /etc/redis.conf
RUN sed -i "s|maxmemory <bytes>|maxmemory 256mb|g" /etc/redis.conf
RUN sed -i "s|maxmemory-policy noeviction|maxmemory-policy allkeys-lfu|g" /etc/redis.conf
RUN sed -i "s|protected-mode yes|protected-mode no|g" /etc/redis.conf
CMD ["/usr/bin/redis-server", "/etc/redis.conf"]
