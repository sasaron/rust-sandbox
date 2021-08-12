FROM rust:1.54 as builder
ARG APP="hello_world"
ARG RUNTIME="x86_64-unknown-linux-musl"
WORKDIR /usr/src/${APP}
COPY ./${APP} .
RUN rustup target add ${RUNTIME} \
    && cargo build --release --target=${RUNTIME}

FROM alpine:latest as release
RUN apk --no-cache add ca-certificates
ARG APP="hello_world"
COPY --from=builder /usr/src/${APP}/target/release/${APP} /usr/local/bin/${APP}
CMD ${APP}

FROM rust:1.54 as develop
ARG APP="hello_world"
WORKDIR /usr/src/${APP}
COPY ./${APP} .
RUN cargo install --path . 
