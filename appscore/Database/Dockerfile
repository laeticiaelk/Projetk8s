FROM mcr.microsoft.com/mssql/server:2017-latest
ENV SA_PASSWORD=Pass@word
ENV ACCEPT_EULA=Y
COPY entrypoint.sh entrypoint.sh
COPY SqlCmdStartup.sh SqlCmdStartup.sh
COPY SqlCmdScript.sql SqlCmdScript.sql
RUN chmod +x ./entrypoint.sh ./SqlCmdStartup.sh \
 && apt-get update && apt-get install -y systemd
CMD /bin/bash -c "apt-get update && apt-get install -y systemd && /bin/bash ./entrypoint.sh"