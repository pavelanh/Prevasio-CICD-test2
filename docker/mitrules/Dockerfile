FROM ubuntu:22.04

EXPOSE 1234
EXPOSE 1443
EXPOSE 1550
EXPOSE 3000
EXPOSE 7000
EXPOSE 8088

RUN apt-get update && apt-get install -y curl

COPY /ping.sh ping.sh
Run chmod +x ping.sh
CMD ["/bin/sh", "ping.sh"]
