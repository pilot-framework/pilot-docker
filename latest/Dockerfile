FROM node:latest

# Waypoint install/setup
ADD waypoint /usr/bin
RUN mkdir /data
ADD plugins/* /root/.config/waypoint/plugins/
RUN chmod +x /root/.config/waypoint/plugins/*
RUN touch /data/data.db

# RUN apk --no-cache --virtual add curl python git
# Gcloud install
# Downloading gcloud package
RUN curl https://dl.google.com/dl/cloudsdk/release/google-cloud-sdk.tar.gz > /tmp/google-cloud-sdk.tar.gz
# Installing the package
RUN mkdir -p /usr/local/gcloud \
  && tar -C /usr/local/gcloud -xvf /tmp/google-cloud-sdk.tar.gz \
  && /usr/local/gcloud/google-cloud-sdk/install.sh
# Adding the package path to local
ENV PATH $PATH:/usr/local/gcloud/google-cloud-sdk/bin
# Remove google-cloud-sdk.tar.gz
RUN rm /tmp/google-cloud-sdk.tar.gz

EXPOSE 9701 9702
ENTRYPOINT [ "/usr/bin/waypoint" ]