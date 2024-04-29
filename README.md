
# This is a twitter clone, built with spring boot microservices and angular.

# Running the app locally

# Run in AWS

1: Launch an EC2 Ubuntu instance
    - Select at minimum t2.large to ensure we have enough RAM
2: Install Maven and java

    > sudo apt update
    > sudo apt install maven -y
    > sudo apt install fontconfig openjdk-17-jre

3: Install docker
    > sudo apt-get update
    > sudo apt-get install ca-certificates curl
    > sudo install -m 0755 -d /etc/apt/keyrings
    > sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    > sudo chmod a+r /etc/apt/keyrings/docker.asc
    
    
    > echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    > sudo apt-get update


    > sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    > docker --version
4: Install Jenkins

    > sudo apt-get update

    > sudo apt-get install jenkins

    // I'm not sure when this command has to be run, I think this is the earliest and if you do it after jenkins starts you need to restart jenkins
    > sudo usermod -a -G docker jenkins 

    > sudo systemctl enable jenkins

    > sudo systemctl start jenkins

    > sudo systemctl status jenkins


Step 4: connect with jenkins server
    1. modify aws security group - inbound rule - allow all traffic all ip

    2. http:<public IP4 number>:8080

    3. get the initialPassword
    > sudo cat /var/lib/jenkins/secrets/initialAdminPassword

    Basic Jenkins Setup -- Suggested plugins, admin account

    Install Plugins At minimum
        Eclipse Termurin Installer
        Docker
        Docker Pipeline
        docker-build-step

    Configure tools
        JDK
        Maven
        Docker
        etc

Step 5: Write pipeline job
    Checkout
    Build
    Test
    Deploy (docker compose up)
