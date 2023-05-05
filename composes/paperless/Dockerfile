FROM openjdk:17-jdk-slim

ARG CRYPTOMATOR_CLI_VERSION=0.5.1

RUN adduser --disabled-password cryptomator 

COPY ./cryptomator-cli-${CRYPTOMATOR_CLI_VERSION}.jar /usr/bin/cryptomator.jar

USER cryptomator

VOLUME ["/vaults"]

# ENTRYPOINT ["java", "-jar", "/usr/bin/cryptomator.jar", "--vault", "vault=/vaults/vault", "--password", "vault=foobarbaz", "--bind", "0.0.0.0", "--port", "8080"]

# run cryptomator with password from crypto.env
CMD java -jar /usr/bin/cryptomator.jar --vault vault=/vaults/vault --password vault=${VAULT_PASSWORD} --bind 0.0.0.0 --port 8080