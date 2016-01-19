FROM debian:wheezy
MAINTAINER Jacob Tomlinson <jacob.tomlinson@informaticslab.co.uk>
MAINTAINER aykit <code@aykit.org>


#=========================#
#   INSTALL DEPENDENCIES  #
#=========================#

RUN apt-get update && \
	apt-get -y install ruby1.9.3 git libpq-dev build-essential

RUN gem install bundler


#====================#
#   INSTALL GITROB   #
#====================#

RUN gem install gitrob
COPY start-gitrob.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/start-gitrob.sh
RUN touch $(gem environment gemdir)/gems/gitrob-0.0.6/agreement


#=============#
#   CLEANUP   #
#=============#

RUN apt-get -y purge build-essential


#=============#
#   RUNTIME   #
#=============#

EXPOSE 9393
ENTRYPOINT ["/usr/local/bin/start-gitrob.sh"]
