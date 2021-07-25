FROM alpine AS build

WORKDIR /code

RUN fallocate -l 100M big_file.dat
RUN fallocate -l 10M small_file.dat

RUN rm ./big_file.dat

FROM alpine

WORKDIR /app
COPY --from=build /code ./