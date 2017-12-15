FROM nginx

RUN apt-get -y update
RUN apt-get -y install ruby ruby-dev make gcc

RUN gem install jekyll bundler octopress-autoprefixer

COPY conf/nginx.conf /etc/nginx

RUN mkdir /src

ADD src /src

WORKDIR /src

RUN bundle install

RUN jekyll build ENV=production

RUN cp -r _site/* /usr/share/nginx/html

