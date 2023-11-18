FROM alpine:3.17

ADD https://github.com/whosgonna/sipexer/releases/download/untagged-0c39aa5e47f0ab1c3255/sipexer /usr/bin/sipexer

RUN wget -O whosgonna-repo-00B57683F0568A5B55999F542C5F836ED8A8A135.rsa.pub \
        https://packagecloud.io/whosgonna/repo/rsakey/whosgonna-repo-00B57683F0568A5B55999F542C5F836ED8A8A135.rsa.pub \
    && echo "https://packagecloud.io/whosgonna/repo/alpine/v3.17/main" /etc/apk/repositories \
    && apk add --no-cache kamailio kamailio-mysql kamailio-extras  \
                          kamailio-redis sipp sngrep kamailio-json sipp sngrep

ENTRYPOINT ["kamailio", "-dDDE"]

