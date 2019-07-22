# FROM              ruby

# # Install rails and create the rails application path.
# RUN               apt-get update \
#                   && apt-get upgrade -y \
#                   && apt-get install -y \
#                       build-essential \
#                       nodejs \
#                       libpq-dev
# RUN               gem install rails \
#                   && gem install bundler
# RUN               mkdir /opt/app

# # Add the application to the application path.

FROM ruby

RUN apt-get update && \
	apt-get install nodejs -y && \
	gem install rails && \
	mkdir -p /opt/app

ONBUILD WORKDIR /opt/app
ONBUILD ADD myapp /opt/app

ONBUILD RUN bundle install && rake db:migrate && rake db:seed