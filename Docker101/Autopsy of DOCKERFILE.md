```DOCKERFILE
# 1️⃣ Base image
FROM python:3.10-slim

# 2️⃣ Maintainer info (optional)
LABEL maintainer="sweetbud@example.com"

# 3️⃣ Set environment variables
ENV APP_HOME=/app \
    FLASK_ENV=development

# 4️⃣ Set working directory
WORKDIR $APP_HOME

# 5️⃣ Copy project files into image
COPY . .

# 6️⃣ Add files from remote URL or tar (less common)
# ADD https://example.com/config.tar.gz /tmp/

# 7️⃣ Install dependencies
RUN pip install --no-cache-dir flask requests

# 8️⃣ Expose port for container
EXPOSE 5000

# 9️⃣ Set default user (optional security)
USER nobody

# 🔟 Define volumes (for data persistence)
VOLUME ["/app/data"]

# 1️⃣1️⃣ Define environment variable dynamically
ARG VERSION=1.0

# 1️⃣2️⃣ Run a command when container starts
CMD ["python", "app.py"]

# 1️⃣3️⃣ Alternate: Use ENTRYPOINT to force command execution
# ENTRYPOINT ["python"]

# 1️⃣4️⃣ HEALTHCHECK to monitor container health
HEALTHCHECK CMD curl --fail http://localhost:5000/ || exit 1
```

## Dockerfile Commands Cheat Sheet

| Command | Meaning | Example Syntax | When It Executes |
|----------|----------|----------------|------------------|
| **FROM** | Defines the base image to build from | `FROM ubuntu:22.04` | Build time (first instruction) |
| **LABEL** | Adds metadata (like author, version) | `LABEL maintainer="sweetbud@example.com"` | Build time |
| **ENV** | Sets environment variables inside image | `ENV APP_HOME=/app` | Build + Run time |
| **WORKDIR** | Sets working directory inside container | `WORKDIR /app` | Build + Run time |
| **COPY** | Copies local files to image | `COPY . /app` | Build time |
| **ADD** | Like COPY but can fetch remote URLs or unpack archives | `ADD https://url/file.tar.gz /tmp/` | Build time |
| **RUN** | Executes commands during image build (layer creation) | `RUN apt-get update && apt-get install -y vim` | Build time |
| **EXPOSE** | Documents which port app listens on | `EXPOSE 8080` | Informational (not firewall rule) |
| **USER** | Sets the user to run commands as | `USER appuser` | Build + Run time |
| **VOLUME** | Creates mount point for persistent or shared data | `VOLUME ["/data"]` | Build + Run time |
| **ARG** | Defines variables for build-time only | `ARG VERSION=1.0` | Build time |
| **CMD** | Sets default command when container starts | `CMD ["python", "app.py"]` | Run time |
| **ENTRYPOINT** | Defines main executable that always runs | `ENTRYPOINT ["python"]` | Run time |
| **HEALTHCHECK** | Tests container health periodically | `HEALTHCHECK CMD curl --fail http://localhost:80 || exit 1` | Run time |
| **ONBUILD** | Sets trigger for child images (runs when base image used to build another image) | `ONBUILD COPY . /app` | Build time of child image |
| **SHELL** | Changes default shell used for RUN commands | `SHELL ["/bin/bash", "-c"]` | Build time |
| **STOPSIGNAL** | Defines system signal sent to stop container | `STOPSIGNAL SIGKILL` | Run time |

---