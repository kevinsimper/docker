FROM docker:stable

LABEL "name"="Docker CLI Action"
LABEL "maintainer"="GitHub Actions <support+actions@github.com>"
LABEL "version"="1.0.0"

LABEL "com.github.actions.name"="GitHub Action for Docker"
LABEL "com.github.actions.description"="Wraps the Docker CLI to enable Docker commands."
LABEL "com.github.actions.icon"="package"
LABEL "com.github.actions.color"="blue"

ADD https://raw.githubusercontent.com/davido/bazel-alpine-package/master/david@ostrovsky.org-5a0369d6.rsa.pub \
    /etc/apk/keys/david@ostrovsky.org-5a0369d6.rsa.pub
    
ADD https://github.com/davido/bazel-alpine-package/releases/download/0.26.1/bazel-0.26.1-r0.apk \
    /tmp/bazel-0.26.1-r0.apk
    
RUN apk add /tmp/bazel-0.26.1-r0.apk

COPY LICENSE README.md THIRD_PARTY_NOTICE.md /

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
