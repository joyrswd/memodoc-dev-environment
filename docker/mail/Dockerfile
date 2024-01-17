# Use Alpine Linux as the base image
FROM alpine:latest

# Install Postfix and syslog
RUN apk add --no-cache postfix busybox

# Start Postfix service
CMD sh -c 'touch /var/log/mail.log && syslogd -O /var/log/mail.log && postfix start-fg'
