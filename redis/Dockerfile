FROM ubuntu:jammy
RUN apt-get update && apt-get install -y lsb-release curl gpg \
 && curl -fsSL https://packages.redis.io/gpg | gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg \
 && echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" \ 
    | tee /etc/apt/sources.list.d/redis.list >> /dev/null \
 && apt-get update && apt-get install -y redis redis-tools
EXPOSE 6379
CMD ["redis-server","--protected-mode no"]
