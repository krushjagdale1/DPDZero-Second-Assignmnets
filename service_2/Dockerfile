FROM python:3.10-slim

# Install curl and PDM
RUN apt-get update && apt-get install -y curl \
  && curl -sSL https://pdm.fming.dev/install-pdm.py | python3 - \
  && apt-get clean

# Set working directory
WORKDIR /app

# Copy project files
COPY . .

# Add PDM to PATH
ENV PATH="/root/.local/bin:$PATH"

# Install only production dependencies
RUN pdm install --prod

# Expose correct port
EXPOSE 8002

# Run the app
CMD ["pdm", "run", "python", "app.py"]

