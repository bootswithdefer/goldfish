FROM alpine:3.7

# Version of goldfish to install
ENV GOLDFISH_VERSION=v0.9.0

# Directory to put Goldfish binary in
WORKDIR /app

# Install Goldfish binary and clean up
RUN apk --no-cache add curl ca-certificates && \
          curl -L -o goldfish https://github.com/Caiyeon/goldfish/releases/download/$GOLDFISH_VERSION/goldfish-linux-amd64 && \
          chmod +x ./goldfish

#Copy Goldfish files
COPY docker.hcl .

#Default port to expose
EXPOSE 8000

#Default command to run
CMD /app/goldfish -config=/app/docker.hcl
