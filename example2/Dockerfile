# syntax = docker/dockerfile:1.2
FROM ruby:3.2-slim AS build
WORKDIR /app
COPY Gemfile Gemfile.lock ./
RUN --mount=type=cache,target=/var/cache/apt apt-get update \
    && apt-get -y install libmariadb-dev build-essential libmariadb3 \
    && bundle install --without development test
COPY . .

FROM build AS test
WORKDIR /app
RUN bundle install --without development && echo "test"

FROM ruby:3.2-slim AS release
WORKDIR /app
ENV RACK_ENV=production
COPY --from=build /app /app
COPY --from=build /usr/local/bundle /usr/local/bundle
CMD ["bundle", "exec", "ruby", "./myapp.rb"]
