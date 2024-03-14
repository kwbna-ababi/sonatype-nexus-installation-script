# Nexus Installation Script

This script automates the installation process of Nexus Repository Manager on a newly provisioned Ubuntu server on AWS. Nexus Repository Manager is a popular tool used for managing software artifacts and dependencies.

## Minimum System Requirements

To ensure optimal performance, it is recommended to use a minimum instance type of `t2.large` or `t3.large` when installing Nexus. These instance types provide sufficient resources for running Nexus and its associated services.

## Installation Steps

The script performs the following steps:

1. **Setting Hostname**: The script sets the hostname of the EC2 instance to "nexus" to identify it as the Nexus server.

2. **Updating Packages**: The script updates and upgrades the system packages to ensure that the server has the latest security patches and updates.

3. **Creating User 'nexus'**: It creates a user named 'nexus' with sudo access to manage Nexus services.

4. **Installing Java**: The script installs OpenJDK 8, which is required for running Nexus.

5. **Downloading and Extracting Nexus**: Nexus Repository Manager version 3.65.0-02 is downloaded and extracted to the `/opt` directory.

6. **Configuring Ownership**: The ownership of Nexus and Sonatype-work directories is changed to the 'nexus' user to ensure proper permissions.

7. **Configuring Nexus Run-As User**: Nexus is configured to run as the 'nexus' user for security reasons.

8. **Creating Systemd Service**: A systemd service file is created to manage the Nexus service, specifying its startup and shutdown commands.

9. **Reloading Systemd Daemon**: The systemd daemon is reloaded to apply the changes made to the service configuration.

10. **Starting and Enabling Nexus**: Finally, the Nexus service is started and enabled to ensure that it automatically starts on system boot.

## Usage

### Option 1: Direct Execution

To use this script, simply copy and paste it into a new file on your Ubuntu server and name it nexus-install.sh. Execute it using the bash interpreter:

    sudo bash nexus-install.sh

### Option 2: Clone from GitHub

Alternatively, you can clone the repository containing the script onto your server using the following command: 

    git clone https://github.com/chriscloudaz/sonatype-nexus-installation-script/

Navigate to the cloned repository directory and execute the script:

    cd sonatype-nexus-installation-script
    sudo bash nexus-install.sh

This method allows you to keep the script up-to-date by pulling changes from the repository when needed. 

## Important Note
Ensure that you have appropriate permissions and access rights before running this script, as it performs system-level operations that may affect the stability and security of your server.

For any questions or issues related to this script, please open an issue on the GitHub repository or reach out to me via email on chriscloudaz@gmail.com.

Happy artifact management with Nexus!
