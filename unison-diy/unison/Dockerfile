FROM alpine:latest

# Layer: latest Alpine with unison installed
RUN apk update \
    && apk upgrade \
    && apk add unison

# Layer: system tuning
# increase the max number of inotify watches for large directories
RUN echo 'fs.inotify.max_user_watches=524288' >> /etc/sysctl.conf

# Layer: directories to be synchronized + Unison state
RUN mkdir -p /root/macos /root/docker /root/.unison

ENV UNISONLOCALHOSTNAME unison
CMD unison /root/macos /root/docker \
    -auto \
    -batch \
    -ignore 'Path .git' \
    -logfile /proc/self/fd/2 \
    -numericids \
    -prefer /root/macos \
    -repeat watch
