FROM java:8-jre

# Last modified at 2015-05-25
MAINTAINER Hinsteny <hinsteny@gmail.com>

ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"

COPY scripts /scripts

RUN chmod +x /scripts/start

# Go Into the tomcat catalogue
WORKDIR $CATALINA_HOME

ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.0.29
ENV TOMCAT_TGZ_URL http://mirrors.hust.edu.cn/apache/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz

RUN set -x \
	&& DEBIAN_FRONTEND=noninteractive apt-get install -y wget  \
	&& wget "$TOMCAT_TGZ_URL" \
	&& tar -xvf apache-tomcat*.tar.gz --strip-components 1 \
	&& rm apache-tomcat*.tar.gz \
	&& rm conf/tomcat-users.xml
  
VOLUME ["/usr/local/tomcat/logs"]

EXPOSE 8080 443

CMD ["/scripts/start"]