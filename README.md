# Monitor System Resources Using Netdata

## Objective:
The objective of this task is to install **Netdata**, a lightweight open-source monitoring tool, and visualize system and application performance metrics. Netdata allows you to monitor real-time CPU, memory, disk usage, network performance, and Docker containers.

## Tools Used:
- **Netdata**: Open-source real-time monitoring tool
- **Docker**: Containerization platform

## Deliverables:
1. Screenshot of the Netdata dashboard showing system resource metrics.
2. Documentation of the steps followed to run Netdata using Docker.

## Prerequisites:
Before starting, make sure you have the following:
- **Docker** installed on your machine.
  - [Docker installation guide](https://docs.docker.com/get-docker/)
- A modern web browser (e.g., Chrome, Firefox).

## Steps:

### Step 1: Run Netdata using Docker

1. Open a terminal or PowerShell in your task directory.
2. Run the following command to start the Netdata container:

   ```bash
   docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata


This will run the Netdata container in the background and expose it on port 19999.

You can access the Netdata dashboard at http://localhost:19999.

Step 2: Access the Netdata Dashboard
Open your web browser and navigate to http://localhost:19999.

You should see the Netdata real-time monitoring dashboard, where you can monitor:

CPU Usage

Memory Usage

Disk Usage

Network Traffic

Docker Containers (if applicable)

Step 3: Explore Logs
1.To view logs generated by Netdata, open a terminal and access the container:
docker exec -it netdata bash

2.Navigate to the log directory:
cd /var/log/netdata

3.View the log files (e.g., error.log or access.log):
cat error.log

These logs provide insights into the system’s health and any issues Netdata might encounter.

Step 4: Cleanup
After completing the task, you can stop and remove the Netdata container:

1.Stop the container:
docker stop netdata

2.Remove the container:
docker rm netdata

Conclusion:
This task demonstrates how to monitor system resources using Netdata in a Docker container. It's a lightweight and efficient way to keep track of system performance and troubleshoot potential issues in real-time.

