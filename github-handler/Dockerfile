FROM postgres:17

# When running the `docker buildx build` command, you may encounter the following warning:
#
# 1 warning found (use docker --debug to expand):
# - SecretsUsedInArgOrEnv: Do not use ARG or ENV instructions for sensitive data (ENV "POSTGRES_PASSWORD") (line 5)
#
# This warning indicates that sensitive data, such as passwords, should not be passed using ARG or ENV instructions
# in the Dockerfile. This is a security best practice to prevent accidental exposure of sensitive information.
#
# However, since this `Dockerfile` is intended for use in a development environment, you can choose to ignore this warning, or raise a pull request to help us improving it.
ENV POSTGRES_DB=${POSTGRES_DB}
ENV POSTGRES_USER=${POSTGRES_USER}
ENV POSTGRES_PASSWORD=${POSTGRES_PASSWORD}

COPY postgresql.conf /etc/postgresql/postgresql.conf

EXPOSE 5432

CMD ["postgres"]
