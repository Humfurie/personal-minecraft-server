# Base image for the container
FROM ubuntu:focal

RUN apt-get update
RUN apt-get install ca-certificates -y wget
RUN update-ca-certificates

# Create directory for PlayIt.gg binary
RUN mkdir /app

# Set working directory
WORKDIR /app

# Download PlayIt.gg binary (Replace URL with the actual download link)
RUN wget https://github.com/playit-cloud/playit-agent/releases/download/v0.15.13/playit-linux-amd64 -O /app/playit

# Set permissions for the binary
RUN chmod 0755 /app/playit

# Define a volume to persist configuration (Optional)
VOLUME ["/config"]

# Copy configuration file (if using volume)
COPY playit.toml /root/.config/playit_gg/playit.toml

# Entrypoint to run PlayIt.gg tunnel (replace with your actual command)
CMD [ "/app/playit", "-s" ]