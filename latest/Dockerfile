FROM gcr.io/google.com/cloudsdktool/cloud-sdk:alpine

# Waypoint install/setup
ADD waypoint /usr/bin
ADD plugins/* /root/.config/waypoint/plugins/
RUN mkdir /data \
  && touch /data/data.db \
  && chmod +x /root/.config/waypoint/plugins/*

# NodeJS + Yarn install
RUN apk add nodejs npm --no-cache \
  && npm i -g yarn

EXPOSE 9701 9702
ENTRYPOINT [ "/usr/bin/waypoint" ]