![CI/CD](https://github.com/kool-dev/docker-java/workflows/CI/CD/badge.svg)

## Description

Minimal Java Docker image focused on Java applications based on [Amazon Corretto](https://github.com/corretto/corretto-docker). It's use is intended for [kool.dev](https://github.com/kool-dev/kool), but can fit in any other Java use-case.

Legacy images automatically load classpaths for Maven and Gradle applications. Modern images provide pinned Maven and Gradle toolchains without modifying project build files.

## Available Tags

The image built is [`kooldev/java`](https://hub.docker.com/r/kooldev/java/tags?page=1&ordering=last_updated) which has a bunch of tags available:

### 26

- [26](https://github.com/kool-dev/docker-java/blob/master/26/Dockerfile) and [26-prod](https://github.com/kool-dev/docker-java/blob/master/26-prod/Dockerfile)

### 25

- [25](https://github.com/kool-dev/docker-java/blob/master/25/Dockerfile) and [25-prod](https://github.com/kool-dev/docker-java/blob/master/25-prod/Dockerfile)

### 21

- [21](https://github.com/kool-dev/docker-java/blob/master/21/Dockerfile) and [21-prod](https://github.com/kool-dev/docker-java/blob/master/21-prod/Dockerfile)

### 17

- [17](https://github.com/kool-dev/docker-java/blob/master/17/Dockerfile) and [17-prod](https://github.com/kool-dev/docker-java/blob/master/17-prod/Dockerfile)

### Legacy versions

The following versions remain available for compatibility but are not recommended for new projects. Java 15 and 16 are end-of-life (EOL) non-LTS releases and are no longer actively maintained.

### 16 (EOL)

- [16](https://github.com/kool-dev/docker-java/blob/master/16/Dockerfile)
- [16-prod](https://github.com/kool-dev/docker-java/blob/master/16-prod/Dockerfile)

### 15 (EOL)

- [15](https://github.com/kool-dev/docker-java/blob/master/15/Dockerfile)
- [15-prod](https://github.com/kool-dev/docker-java/blob/master/15-prod/Dockerfile)

### 11 (Legacy LTS)

- [11](https://github.com/kool-dev/docker-java/blob/master/11/Dockerfile)
- [11-prod](https://github.com/kool-dev/docker-java/blob/master/11-prod/Dockerfile)

### 8 (Legacy LTS)

- [8](https://github.com/kool-dev/docker-java/blob/master/8/Dockerfile)
- [8-prod](https://github.com/kool-dev/docker-java/blob/master/8-prod/Dockerfile)

## Environment Variables

Variable | Default Value | Description
--- | --- | ---
**ASUSER** | `0` | Changes the user id that executes the commands
**UID** | `0` | Changes the user id that executes the commands **(ignored if ASUSER is provided)**
**VM_OPTIONS_XMS** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_XMX** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_MAX_METASPACE_SIZE** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_PERM_SIZE** | `512m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_XMN** | `64m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_SURVIVOR_RATIO** | `128` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**CMS_TRIGGER_PERCENT** | `70` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**JVM_FILE_ENCODING** | `UTF-8` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm) 
**JVM_TTL** | `60` | See [Java Documentations](https://docs.oracle.com/javase/7/docs/technotes/guides/net/properties.html)
**JVM_USER_LANGUAGE** | `en` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm) 
**JVM_USER_COUNTRY** | `US` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm)
**TZ** | | Set default Timezone
**JAVA_OPTIONS** | | Additional Java Options 
**RMI_SERVER_HOSTNAME** | | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/guides/rmi/javarmiproperties.html)
**JVM_JMXREMOTE_PORT** | | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/guides/management/agent.html)
**JVM_JMXREMOTE_AUTHENTICATE** | | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/guides/management/agent.html)
**JVM_JMXREMOTE_SSL** | | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/guides/management/agent.html)
**DEBUG_PORT** | `9000` | Debug port
**DEBUG_SUSPEND** | `n` | Suspend debug to waiting attached
**CLASSPATH** | | Custom classpath, bay default defined by **maven** or **gradle** architecture 
**MAIN_CLASS** | | Class main, required by execute 

Modern images (`17`, `21`, `25`, and `26`) provide pinned Maven and Gradle versions and support AMD64 and ARM64. Mount Maven and Gradle caches at `/home/kool/.m2` and `/home/kool/.gradle`.

### PROD

Variable | Default Value | Description
--- | --- | ---
**ASUSER** | `0` | Changes the user id that executes the commands
**UID** | `0` | Changes the user id that executes the commands **(ignored if ASUSER is provided)**
**VM_OPTIONS_XMS** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_XMX** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_MAX_METASPACE_SIZE** | `256m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_PERM_SIZE** | `512m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_XMN** | `64m` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**VM_OPTIONS_SURVIVOR_RATIO** | `128` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**CMS_TRIGGER_PERCENT** | `70` | See [Java Documentations](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
**JVM_FILE_ENCODING** | `UTF-8` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm)
**JVM_TTL** | `60` | See [Java Documentations](https://docs.oracle.com/javase/7/docs/technotes/guides/net/properties.html)
**JVM_USER_LANGUAGE** | `en` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm)
**JVM_USER_COUNTRY** | `US` | See [Java Documentations](https://docs.oracle.com/javame/config/cdc/cdc-opt-impl/ojmeec/1.0/runtime/html/localization.htm)
**TZ** | | Set default Timezone
**JAVA_OPTIONS** | | Additional Java Options
**JAR_FILE** | `/app/application.jar` | Jar file you application

## Usage

The developer version, you need mount your volume to maven and gradle.

- $HOME/.kool/m2:/home/kool/.m2
- $HOME/.kool/gradle:/home/kool/.gradle

### With `kool`:

In your application directory:

```shell
kool docker -e MAIN_CLASS=your.package.MainClass kooldev/java:8
```

To production version:

```shell
kool docker -e JAR_FILE=yout_application.jar kooldev/java:8-prod
```

Execute Jshell:

```shell
kool docker kooldev/java:11 jshell
```

### With `docker run`:

```sh
docker run -it --rm kooldev/java:11 jshell
```

### With `docker-compose.yml`:

```yaml
app:
  image: kooldev/java:8
  volumes:
    - ".:/app:cached"
    - "$HOME/.ssh/id_rsa:/home/developer/.ssh/id_rsa:cached"
  environment:
    ASUSER: "${$UID}"
```

## Contributing

### Update images with templates

You should change `fwd-template.json` for configuration and `template` folder for the actual base templates.

After any changes, we need to run `kool run template` to parse the templates and generate all versions folder/files.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
