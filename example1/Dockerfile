FROM ruby
WORKDIR /app
COPY . .
RUN apt-get update 
RUN apt-get -y install libmariadb-dev build-essential libmariadb3
RUN echo "tests"
RUN bundle install 
CMD ["bundle", "exec", "ruby", "./myapp.rb"]
