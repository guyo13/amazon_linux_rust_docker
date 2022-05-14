FROM arm64v8/amazonlinux:2

RUN yum install -y shadow-utils gcc && adduser -m -s /bin/bash compile

USER compile

WORKDIR /home/compile

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > rustup-init.sh \
    && chmod +x rustup-init.sh \
    && ./rustup-init.sh -y \
    && echo 'source $HOME/.cargo/env' >> "$HOME/.bashrc" 

VOLUME /opt/src

WORKDIR /opt/src

CMD ["/bin/bash"]

