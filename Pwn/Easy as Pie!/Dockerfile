FROM ubuntu:latest

RUN apt-get update && apt-get install -y socat python3 nano
RUN groupadd ctf

RUN mkdir /pwn

COPY shell.py /pwn/
COPY entry.sh /pwn/

RUN useradd -G ctf --home=/pwn pwnuser
RUN useradd -G ctf --home=/pwn pwnflag

RUN chown pwnflag:pwnflag /pwn/shell.py
RUN chown pwnflag:pwnflag /pwn

RUN chmod 4755 /pwn/shell.py
RUN chmod 4755 /pwn/entry.sh

EXPOSE 30010
ENTRYPOINT ["/pwn/entry.sh"]
