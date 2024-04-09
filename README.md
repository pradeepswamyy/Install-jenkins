# Installing Jenkins on Ubuntu

This README provides step-by-step instructions for installing Jenkins on an Ubuntu machine using OpenJDK 11 and accessing the Jenkins web interface.

## Prerequisites

Before starting the installation process, ensure you have the following:

- Ubuntu machine
- Sudo privileges
- Access to the internet
- Basic knowledge of the terminal/command line

## Steps to Install Jenkins

1. **Update Package Index:**

   ```bash
   sudo apt update
   ```

2. **Install OpenJDK 11:**

   ```bash
   sudo apt install openjdk-11-jdk
   ```

3. **Verify Java Installation:**

   ```bash
   java --version
   ```

   Ensure that the Java version displayed is 11 or higher.

4. **Add Jenkins Repository Key:**

   ```bash
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian/jenkins.io-2023.key
   ```

5. **Add Jenkins Repository:**

   ```bash
   echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
   ```

6. **Update Package Index Again:**

   ```bash
   sudo apt-get update
   ```

7. **Install Jenkins:**

   ```bash
   sudo apt-get install jenkins
   ```

8. **Check Jenkins Service Status:**

   ```bash
   systemctl status jenkins
   ```

   Ensure that the Jenkins service is active and running.

## Accessing Jenkins Web Interface

1. Copy the public IPv4 address of your Ubuntu machine.
2. Open a web browser and paste the IPv4 address followed by port 8080. For example: `http://your_ip_address:8080`.
3. Initially, you might encounter an error indicating that the connection is refused or the page cannot be reached.

## Configuring Security Group Rules

1. Access your cloud provider's console.
2. Modify the inbound rules of the security group associated with your Ubuntu instance.
3. Add a new rule to allow inbound traffic on port 8080 from anywhere (0.0.0.0/0).
4. Save the changes.

## Accessing Jenkins Web Interface (Continued)

1. Refresh the web page in your browser.
2. You should now see the Jenkins setup wizard, allowing you to proceed with the initial configuration.

## Additional Notes

- During the setup wizard, Jenkins will provide a temporary administrator password. Follow the instructions to complete the setup process.
- Make sure to secure your Jenkins installation by configuring authentication and authorization settings as per your requirements.
- Refer to the [Jenkins documentation](https://www.jenkins.io/doc/) for more detailed configuration and usage instructions.

Congratulations! You have successfully installed Jenkins on your Ubuntu machine. Happy automation! 🚀
