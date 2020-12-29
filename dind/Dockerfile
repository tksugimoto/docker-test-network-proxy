FROM docker:20.10.1-dind

RUN apk add --update-cache --no-cache docker-compose

# dig
RUN apk add --update-cache --no-cache bind-tools

# for dind docker-compose environment
RUN { \
    echo "# Since IP resolution of the outer container is not possible from inside the dind container, it is converted to IP format by name resolution at login."; \
    echo "export http_proxy=http://\$(dig +short proxy):3128"; \
    echo "export https_proxy=http://\$(dig +short proxy):3128"; \
} > /etc/profile.d/proxy.sh

WORKDIR /root/

COPY ./compose ./
