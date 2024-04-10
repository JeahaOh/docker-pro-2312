# FROM alpine:latest
# CMD ["echo", "Hello, Docker"]

FROM ubuntu:20.04
# build 시점
RUN apt update && apt install -y python3
WORKDIR /var/www/html
# RUN echo "Hell, <b>Hell, Docker</b>"
COPY ["index.html", "."]
# container 실행 시점
CMD ["python3", "-u", "-m", "http.server"]