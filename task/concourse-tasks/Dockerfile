# VERSION         0.1.0
# DOCKER-VERSION  1.9.1
# DESCRIPTION:    Concourse Task Image
# TO_BUILD:       docker build -t local/task .
# TO_RUN:         docker run local/task echo "Hello World!"

FROM ubuntu:18.04

# Copy local project directories to container image
COPY . /opt/concourse-ci/task

# Set current working directory for executed scripts
WORKDIR /opt/concourse-ci/task

# Use a custom build script instead of messy chained together RUN
# or multiple RUN statements that add bloat to the image
RUN /opt/concourse-ci/task/scripts/build.sh

# Run tests on the Docker build
RUN /opt/concourse-ci/task/scripts/test.sh
