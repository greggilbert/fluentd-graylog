# Fluentd + fluent-bit + Graylog2 + Elasticsearch

I couldn't find an all-in-one solution for this stack that worked out of the box, so I made this.

Keep in mind that this is merely a proof of concept, and should _not_ be used as-is in production.

## Setup

1. `docker-compose build`
2. `docker-compose up -d`
3. Go to http://127.0.0.1:9000 and log in
4. Go to System > Inputs
5. Add GELF UDP with the default values, but a Receive Buffer Size of 212992

From there, you should be good to go.

To check if it's working, I exec bash into the client container and run `echo "test" >> /var/log/syslog`, and it should show up in Graylog.
