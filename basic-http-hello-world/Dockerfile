FROM busybox:latest
ENV PORT=8080

ADD index.html /www/index.html

HEALTHCHECK CMD nc -z localhost $PORT

CMD echo "httpd started" && trap "exit 0;" TERM INT; httpd -v -p $PORT -h /www -f & wait