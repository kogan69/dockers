FROM arm64v8/postgres:latest
VOLUME /var
RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get -y install  gnupg postgresql-common apt-transport-https lsb-release wget

RUN /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh -y
RUN echo "deb https://packagecloud.io/timescale/timescaledb/debian/ $(lsb_release -c -s) main" | tee /etc/apt/sources.list.d/timescaledb.list
RUN wget --quiet -O - https://packagecloud.io/timescale/timescaledb/gpgkey | apt-key add -
RUN apt update
RUN apt-get -y  install timescaledb-2-postgresql-15
#RUN timescaledb-tune --yes --quiet -pg-config  /usr/lib/postgresql/15/bin
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" | tee  /etc/apt/sources.list.d/pgdg.list
RUN apt-get -y  install postgresql-15-postgis-3
RUN apt-get -y install vim


