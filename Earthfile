
VERSION 0.7
FROM bash:5.2.15-alpine3.18
WORKDIR /bash-scripts

build:
    COPY test-script .
    RUN pwd
    RUN ./test-script
    SAVE ARTIFACT test-script AS LOCAL local-output/test-script


docker:
    COPY +build/test-script .
    ENTRYPOINT ["bash", "/bash-scripts/test-script"]
    ARG tag="latest"
    # SAVE IMAGE bash-test:latest 
    # SAVE IMAGE test-script:$tag 
    SAVE IMAGE --push onsokumaru/test-script:$tag 


all:
    BUILD +build
    BUILD +docker