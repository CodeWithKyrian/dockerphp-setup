# Docker-Based PHP Development Environment

This repository provides a simple and flexible Docker-based development environment for PHP projects. With this setup,
you can easily configure and manage your development environment, making it reproducible across different machines.
Whether you're working on PHP web applications, Laravel projects, or other similar endeavors, this environment can
streamline your development workflow.

## Features

- **PHP Container**: Configured with PHP-FPM and Nginx, using the `webdevops/php-nginx-dev` image.
- **MySQL Support**: Integrated with the official MySQL Docker image for database management.
- **phpMyAdmin**: Includes phpMyAdmin for convenient MySQL database administration.(accessible at http://localhost:8080)
- **MailPit**: Optional integration for email testing during development. (accessible at http://localhost:1080)
- **Node.js and NPM**: For managing front-end assets in Laravel projects.
- **Scheduler Configuration**: Laravel-specific setup for scheduling tasks.

## Getting Started

To set up your development environment using Docker, follow these steps:

1. Ensure that you have Docker installed on your machine. If not, download and install Docker for your operating system
   from the [Official Website](https://docs.docker.com/engine/install/) or for WSL2, check out my guide
   on [How to Install Docker on Windows 10 WSL2](https://codewithkyrian.com/p/how-to-install-docker-in-wsl2-without-docker-desktop).

2. Set up your project environment.

    - **Option 1: Easy Setup (Linux, Mac, or WSL2)**

      Run the following command in the root folder of your project to automatically set up the environment:

       ```sh
       curl -s https://codewithkyrian.com/dockerphp-setup | bash
       ```

      This script will clone the repository and set up the necessary files in your project.

    - **Option 2: Manual Setup**

      Alternatively, if curl is not available on your system, you can manually set up the environment by downloading
      the
      repository and copying the files to the root folder of your project.

3. Create a `.env` file in the root directory of the project and configure environment variables as needed. (One has
   been created for you if you used the automatic setup script.)

4. Run the Docker Compose command to start the services:

   ```bash
   docker compose up -d
    ```
5. Access your PHP application in a web browser by navigating to http://localhost.

6. Access phpMyAdmin for database management at http://localhost:8080 (username: root, password: specified in the .env
   file).

7. For Laravel projects, set your .env file's `DB_CONNECTION` to mysql and `DB_HOST` to mysql.

Enjoy a seamless and customizable development environment!

## Configuration

- Adjust the Docker Compose configuration in the docker-compose.yml file to suit your project's requirements.
- Customize the Nginx configuration in the `docker/nginx.conf` file.
- For email testing, use the optional MailPit service.

## Scheduler Setup

To configure the Laravel scheduler:

- Edit the docker/scheduler.sh script to define scheduled tasks as needed.
- Make the script executable by running:
   ```
   chmod +x docker/scheduler.sh
   ```

The scheduler script will run Laravel scheduled tasks at specified intervals.

## Contributing

Feel free to contribute to this project by opening issues or pull requests. Your feedback and contributions are highly
appreciated!
