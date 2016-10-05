# Current version 1.3.6
FROM discourse/base:1.3.6

MAINTAINER Keith Newton "https://twitter.com/inovae_keith"

# Discourse specific bits
RUN useradd discourse -s /bin/bash -m -U &&\
    mkdir -p /var/www && cd /var/www &&\
     git clone https://github.com/corillian/discourse.git &&\
     cd discourse &&\
    chown -R discourse:discourse /var/www/discourse &&\
    cd /var/www/discourse &&\
     sudo -u discourse bundle install --deployment \
         --without test --without development &&\
    find /var/www/discourse/vendor/bundle -name tmp -type d -exec rm -rf {} +

