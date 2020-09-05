FROM httpd:2.4.46

RUN echo -e "\n\
alias ll='ls -l --color=auto'\n\
" >> /root/.bashrc

RUN ["apt-get", "update"]

# 設定ファイルのオーバーライド
COPY ./httpd-tomcat.conf /usr/local/apache2/conf/extra/httpd-tomcat.conf
RUN mv /usr/local/apache2/conf/httpd.conf /usr/local/apache2/conf/httpd.conf.org
COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf
RUN ["apachectl", "restart"]
