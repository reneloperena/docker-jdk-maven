FROM centos:7

RUN yum install -y wget

RUN cd ~ \
  && wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.rpm" \
  && yum localinstall -y jdk-7u79-linux-x64.rpm \
  && rm -f ~/jre-7u79-linux-x64.rpm

ENV JAVA_HOME /usr/java/jdk1.7.0_79

RUN wget http://archive.apache.org/dist/maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.tar.gz \
  && tar xzf apache-maven-3.1.1-bin.tar.gz \
  && mv apache-maven-3.1.1 /usr/share/maven \
  && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn \
  && rm -f ~/apache-maven-3.1.1-bin.tar.gz

ENV MAVEN_HOME /usr/share/maven