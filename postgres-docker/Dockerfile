FROM postgres:latest

# Set environment variables
ENV POSTGRES_DB=mydatabase
ENV POSTGRES_USER=myuser
ENV POSTGRES_PASSWORD=mypassword

# Copy the initialization SQL script into the container
COPY init.sql /docker-entrypoint-initdb.d/

# Expose the PostgreSQL port
EXPOSE 5432

# # Use the official PostgreSQL image as the base image
# FROM postgres:latest

# # Copy the initialization SQL script into the container
# COPY init.sql /docker-entrypoint-initdb.d/

# # Set environment variables if needed
# # ENV ...

# # Expose the PostgreSQL port if needed
# # EXPOSE ...

# # Optionally, perform any other configuration or setup
# # ...

# # Start PostgreSQL service
# CMD ["postgres"]