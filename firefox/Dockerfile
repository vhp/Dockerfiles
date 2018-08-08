FROM ubuntu:18.04

RUN apt-get update && apt-get upgrade -y && apt-get install -y firefox

RUN export uid=1000 gid=1000 && \
    mkdir -p /home/tempuser && \
    echo "tempuser:x:${uid}:${gid}:tempuser,,,:/home/tempuser:/bin/bash" >> /etc/passwd && \
    echo "tempuser:x:${uid}:" >> /etc/group && \
    chown ${uid}:${gid} -R /home/tempuser

USER tempuser
ENV HOME /home/tempuser
CMD /usr/bin/firefox --no-remote

