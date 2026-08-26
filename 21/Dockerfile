FROM amazoncorretto:21-alpine-jdk

ENV ASUSER='' \
    UID='' \
    VM_OPTIONS_XMS=128m \
    VM_OPTIONS_XMX=512m \
    VM_OPTIONS_MAX_METASPACE_SIZE=256m \
    JVM_FILE_ENCODING=UTF-8 \
    JVM_TTL=60 \
    JVM_USER_LANGUAGE='en' \
    JVM_USER_COUNTRY='US' \
    TZ='' \
    JAVA_OPTIONS='' \
    ENTRYPOINT='' \
    GRADLE_USER_HOME=/home/kool/.gradle \
    MAVEN_CONFIG=/home/kool/.m2 \
    JAR_FILE='/app/application.jar'

WORKDIR /app

RUN adduser -D -u 1337 -h /home/kool kool \
    && mkdir -p /home/kool/.gradle /home/kool/.m2 \
    && chown -R kool:kool /home/kool \
    && apk add --no-cache bash ca-certificates curl git openssh-client shadow su-exec tzdata unzip \
    && DOCKERIZE_ARCH="$(case "$(uname -m)" in x86_64) echo amd64 ;; aarch64|arm64) echo arm64 ;; *) echo unsupported architecture >&2; exit 1 ;; esac)" \
    && curl -fsSL "https://github.com/jwilder/dockerize/releases/download/v0.9.3/dockerize-linux-${DOCKERIZE_ARCH}-v0.9.3.tar.gz" | tar xz -C /usr/local/bin \
    && curl -fsSL "https://services.gradle.org/distributions/gradle-8.14.3-bin.zip" -o /tmp/gradle.zip \
    && unzip -q /tmp/gradle.zip -d /opt \
    && ln -s "/opt/gradle-8.14.3" /opt/gradle \
    && curl -fsSL "https://archive.apache.org/dist/maven/maven-3/3.9.11/binaries/apache-maven-3.9.11-bin.tar.gz" | tar xz -C /opt \
    && ln -s "/opt/apache-maven-3.9.11" /opt/maven \
    && rm -f /tmp/gradle.zip \
    && rm -rf /var/cache/apk/*

ENV PATH="/opt/gradle/bin:/opt/maven/bin:$PATH"

COPY kool.vmoptions /kool/kool.tmpl
COPY entrypoint /kool/entrypoint
RUN chmod +x /kool/entrypoint

ENTRYPOINT [ "/kool/entrypoint" ]
CMD [ "sh" ]
