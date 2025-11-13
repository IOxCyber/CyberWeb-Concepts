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