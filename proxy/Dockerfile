FROM alpine:3.10

RUN apk add --update-cache --no-cache 'squid<5'

# TZ環境変数でタイムゾーンを変更できるようにするため
RUN apk add --update-cache --no-cache tzdata

WORKDIR /workdir
RUN chown squid:squid ./

# ログを標準出力に出すために必要
USER squid

CMD [ \
	"squid", \
	"-f", "./squid.conf", \
	"-N" \
]

COPY ./squid.conf ./
