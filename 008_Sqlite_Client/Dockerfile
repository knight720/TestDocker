# Clone Repository
FROM alpine AS git_client
MAINTAINER knight

RUN apk update
RUN apk add git
RUN apk add sqlite
WORKDIR /repo
RUN git clone https://github.com/knight720/VoteIt.git