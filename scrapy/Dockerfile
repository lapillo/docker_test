FROM debian:buster

RUN apt-get update && \
	apt-get install --assume-yes --no-install-recommends \
		gcc \
		libffi-dev \
		libssl-dev \
		libxml2-dev \
		libxslt1-dev \
		python3-pip \
		python3-dev \
		zlib1g-dev && \
	apt-get clean && \
	rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN python3 -m pip install --upgrade \
		setuptools \
		wheel && \
	python3 -m pip install --upgrade scrapy


## SQL CONNECTION ##
RUN python3 -m pip install SQLAlchemy
RUN apt-get update

RUN python3 -m pip install mysql-connector
RUN python3 -m pip install mysql-connector-python
RUN python3 -m pip install pymysql

## CRON ##
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_13.x | bash -
RUN apt-get update
RUN apt-get install -y nodejs
RUN npm install -g crontab-ui
RUN apt-get install -y cron
#RUN apt-get install -y procps
#RUN apt-get install -y nano

CMD crontab-ui --autosave& cron -f

#CMD ["/etc/init.d/cron", "start&", "&&", "crontab-ui", "--autosave"]
#CMD ["tail", "-f", "/etc/passwd"]
#CMD ["scrapy", "shell", "--nolog"]