# -----------------------------------------------------------------------------
# docker-minecraft
#
# Builds a basic docker image that can run a Minecraft server
# (https://www.technicpack.net/modpack/attack-of-the-bteam.552556).
#
# Authors: Tyler Burr
# Updated: Jul 5th, 2020
# Require: Docker (http://www.docker.io/)
# -----------------------------------------------------------------------------


# Base system is the LTS version of Ubuntu.
FROM   ubuntu:20.04


# Make sure we don't get notifications we can't answer during building.
ENV    DEBIAN_FRONTEND noninteractive


# Download and install everything from the repos.
RUN    apt update -y
RUN    apt install openjdk-8-jre-headless -y



# Load in all of our config files.
ADD    ./scripts/start /start


# Fix all permissions
RUN    chmod +x /start


# 25565 is for minecraft
EXPOSE 25565

# /data contains static files and database
VOLUME ["/data"]

# /start runs it.
CMD    ["/start"]
