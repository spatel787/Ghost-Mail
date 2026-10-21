FROM mcr.microsoft.com/dotnet/sdk:10.0

# Install Node.js and npm.
# Pin the Node.js major version for consistent team tooling.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       curl ca-certificates \
    && curl -fsSL https://deb.nodesource.com/setup_22.x \
       | bash - \
    && apt-get install -y --no-install-recommends nodejs \
    && rm -rf /var/lib/apt/lists/*

# Add a non-root development user.
RUN useradd -m -s /bin/bash vscode \
    && mkdir -p /workspace \
    && chown vscode:vscode /workspace

WORKDIR /workspace
USER vscode