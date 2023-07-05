FROM swift:5.9.2-jammy

RUN git clone -b master --depth 1 "https://github.com/yonaskolb/Mint.git" ~/Mint && \
    cd ~/Mint && \
    git rev-parse HEAD > /.mint_revision && \
    swift build --disable-sandbox -c release && \
    mkdir -p /usr/local/bin && \
    cp -f .build/release/mint /usr/local/bin/mint && \
    cd && \
    rm -rf ~/Mint && \
    mint install apple/swift-format@release/5.9.1

CMD /bin/bash
