# Use the official Alpine image as the base
FROM debian:bullseye

# Install required dependencies
RUN apt-get update && apt-get install -y \
    bash curl git unzip xz-utils zip libglu1-mesa && \
    apt-get clean

# Install Flutter SDK
ENV FLUTTER_VERSION=3.29.0
RUN curl -L https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz | tar -xJ -C /opt \
    && ln -s /opt/flutter/bin/flutter /usr/local/bin/flutter

# Add Flutter to PATH
ENV PATH="/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk/bin:$PATH"

# Mark the Flutter directory as safe for Git
RUN git config --global --add safe.directory /opt/flutter

# Pre-download Flutter dependencies
RUN flutter doctor -v

# Set the working directory
WORKDIR /app

# Expose the port for Flutter apps (optional, for web projects)
# EXPOSE 8080

# Default command (can be overridden in derived images)
CMD ["flutter", "--version"]