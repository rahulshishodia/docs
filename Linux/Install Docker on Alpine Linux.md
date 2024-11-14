**Step 1: Enable the Community Repository (A Quick Prep)**

Docker is hosted in Alpine’s community repository, so before you can install it, you need to make sure that repository is enabled.

Here’s how to do that:

1\. Open the repositories file:

`sudo vi /etc/apk/repositories`

2\. Inside this file, you’ll notice a line that looks like this:

`#` [`http://dl-cdn.alpinelinux.org/alpine/latest-stable/community`](http://dl-cdn.alpinelinux.org/alpine/latest-stable/community)

3\. Remove the # to **uncomment** this line. It should now look like this

`http://dl-cdn.alpinelinux.org/alpine/latest-stable/community`

4\. Save and close the file.

Now Alpine knows it can tap into the community repository for packages like Docker. Simple enough, right?

**Step 2: Update the Package Index**

With the community repository enabled, you need to update the package index so your system is aware of the new, available packages (like Docker). Just run:

`sudo apk update`

This command refreshes your system’s package database, ensuring you have access to the latest software.

**Step 3: Add Your User to the Docker Group**

By default, Docker requires root privileges to run. But with a quick adjustment, you can allow your user to run Docker commands without needing to prefix everything with sudo. Here’s how:

1\. Create a Docker group:

`sudo addgroup username docker`

Replace username with your actual system username. For example, if your username is john, you would run:

`sudo addgroup john docker`

2\. After adding yourself to the Docker group, you’ll need to log out and back in for the changes to take effect.

This step is like unlocking a secret level—no more need to run Docker commands with root access.

**Step 4: Install Docker and Docker Compose**

Now that your system is prepped, you can install Docker along with Docker Compose in one easy step:

`sudo apk add docker docker-compose`

This command pulls Docker and Docker Compose from the community repository and installs them on your system. Docker Compose is particularly useful if you want to manage multi-container Docker applications, so it’s a good idea to have it installed right from the start.

**Step 5: Set Docker to Start Automatically**

To ensure Docker starts automatically when your system reboots:

`sudo rc-update add docker boot`

**Step 6: Start Docker**

Now that Docker is installed and set to start on boot, it’s time to fire it up:

`sudo service docker start`

If you want to confirm everything is working as expected, check the Docker version:

`docker --version`

If Docker is running, you’ll see the version number pop up, confirming that everything is set up correctly.

That’s all there is to it! Docker is successfully installed on your Alpine system.
