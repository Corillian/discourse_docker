FROM discourse/base:2.0.20180608

MAINTAINER Keith Newton "https://twitter.com/inovae_keith"

# Discourse specific bits
RUN useradd discourse -s /bin/bash -m -U &&\
    mkdir -p /var/www &&\
    cd /var/www &&\
    git clone https://github.com/corillian/discourse.git &&\
    cd discourse &&\
    chown -R discourse:discourse /var/www/discourse &&\
    cd /var/www/discourse &&\
    sudo -u discourse bundle install --deployment \
         --without test --without development &&\
    bundle exec rake maxminddb:get &&\
    find /var/www/discourse/vendor/bundle -name tmp -type d -exec rm -rf {} +


# For a smaller but less flexible image:
#RUN apt-get -y autoremove build-essential gcc gcc-4.7 .+-dev
#RUN echo image size: $(du -hsx /)
