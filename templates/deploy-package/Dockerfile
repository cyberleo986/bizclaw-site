FROM node:20-slim

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git curl ca-certificates dumb-init \
    && rm -rf /var/lib/apt/lists/*

# Install OpenClaw globally
RUN npm install -g openclaw@latest

# Create the agent workspace directory
WORKDIR /app/agent

# Copy agent files (SOUL.md, AGENTS.md, MEMORY.md, etc.)
COPY . /app/agent/

# Create a non-root user for security
RUN groupadd -r agent && useradd -r -g agent -d /app/agent agent \
    && chown -R agent:agent /app/agent
USER agent

# Expose the default OpenClaw port (if using webhook mode)
EXPOSE 3000

# Use dumb-init for proper signal handling
ENTRYPOINT ["dumb-init", "--"]

# Start OpenClaw with the agent workspace
CMD ["openclaw", "gateway", "start", "--workspace", "/app/agent"]