FROM mysql:8

# Set environment variables for credentials
ENV MYSQL_ROOT_PASSWORD="RoboShop@1"
COPY db/ /docker-entrypoint-initdb.d

# Expose the default MySQL port
EXPOSE 3306
