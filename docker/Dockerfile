FROM rust:1.54 as builder
WORKDIR /usr/src/rust-sandbox
COPY . .
#RUN cargo install --path .

#FROM alpine:latest
#RUN apk --no-cache add ca-certificates
#COPY --from=builder /usr/local/cargo/bin/rust-sandbox /usr/local/bin/rust-sandbox
#CMD ["rust-sandbox"]