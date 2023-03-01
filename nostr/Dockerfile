FROM debian:testing
RUN apt update;apt install -y build-essential git curl libssl-dev pkg-config protobuf-compiler
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > rust.sh;bash rust.sh -y 
WORKDIR /opt
RUN git clone -q https://git.sr.ht/\~gheartsfield/nostr-rs-relay --depth=1
WORKDIR /opt/nostr-rs-relay
COPY compile.sh /opt/
RUN bash /opt/compile.sh
COPY config.toml  /opt/nostr-rs-relay/
COPY favicon.ico /opt/nostr-rs-relay/
CMD RUST_LOG=warn,nostr_rs_relay=info ./target/release/nostr-rs-relay