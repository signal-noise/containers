FROM eu.gcr.io/signalnoise/base:12

# Things for accesibility and end-to-end testing stuff
RUN apk add \
    chromium \
    freetype \
    harfbuzz \
    nss \
    ttf-freefont \
    && ln -s /usr/bin/chromium-browser /usr/bin/chromium \
    && rm -rf /var/cache/apk/*

# Tell Puppeteer to skip installing Chrome. We'll be using the installed package.
ENV PUPPETEER_SKIP_CHROMIUM_DOWNLOAD true

RUN	npm install -g \
    pa11y-ci \
    depcheck \
    --unsafe-perm \
    && npm cache clean --force

VOLUME ["/root/.config"]


