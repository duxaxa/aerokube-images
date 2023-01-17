FROM browsers/base:7.4.0

ARG VERSION=19.4.2.698-1

LABEL browser=yandex-browser-stable:$VERSION

RUN  \
        # curl -v https://repo.yandex.ru/yandex-browser/YANDEX-BROWSER-KEY.GPG | apt-key add - || \
        curl -v https://repo.yandex.ru/yandex-browser/YANDEX-BROWSER-KEY.GPG -o /etc/apt/trusted.gpg.d//YANDEX-BROWSER-KEY.asc && \
        echo 'deb [arch=amd64] https://repo.yandex.ru/yandex-browser/deb stable main' > /etc/apt/sources.list.d/yandex-browser.list && \
        apt-get update && \
        apt-get -y --no-install-recommends install yandex-browser-stable=$VERSION && \
        yandex-browser --version && \
        ln -s /usr/bin/yandex-browser /usr/bin/google-chrome && \
        rm /etc/apt/sources.list.d/yandex-browser.list && \
        rm -Rf /tmp/* && rm -Rf /var/lib/apt/lists/*
