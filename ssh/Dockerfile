FROM alpine:latest
RUN apk update
RUN apk add --no-cache openssh
COPY ./sshd_config /etc/ssh/sshd_config
COPY ./authorized_keys /root/.ssh/authorized_keys
RUN echo -e "P@ssw0rd\nP@ssw0rd" | passwd
RUN chmod 600 /root/.ssh/authorized_keys
RUN ssh-keygen -A
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
