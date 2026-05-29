FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y freeradius freeradius-rest freeradius-utils curl && apt-get clean

EXPOSE 1812/udp
EXPOSE 1813/udp

CMD ["freeradius", "-f", "-X"]
