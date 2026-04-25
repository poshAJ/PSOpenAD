FROM mcr.microsoft.com/devcontainers/base:debian

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y krb5-user

COPY <<EOF /etc/krb5.conf
[libdefaults]
  rdns = false
  default_realm = PSOPENAD.LOCAL

[realms]
  PSOPENAD.LOCAL = {
    kdc = dc.psopenad.local
    admin_server = dc.psopenad.local
  }

[domain_realm]
  psopenad.local = PSOPENAD.LOCAL
  .psopenad.local = PSOPENAD.LOCAL
EOF
