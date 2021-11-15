# Glassfish:
    Install Glassfish server and change HTTP port to 8088.
    Create a demo Java (11) servlet application with maven.
    Generate war package.
    Deploy the war using glassfish app server.

> Download the glassfish server version 6 or above for Java 11.

    sudo yum install maven

    mvn -version  #version check

    sudo yum -y install  java-11-openjdk java-11-openjdk-devel

    java -version



    wget wget https://github.com/eclipse-ee4j/glassfish/releases/download/6.2.2/glassfish-6.2.2.zip

    Extracted the folder to /opt/ directory.

    unzip glassfish-6.2.2.zip -d /opt/

    Launced the asadmin file by path: /opt/glassfish6/bin ./asadmin start-domain domain1

    Which launched the server in port 8088 which I changed from the domain.xml file in config dir of domain1 (Reference picture glassfish_server_port_modified.png ) .

    After the server has been install

    For deploying the war file, I generated the war file using:
        
        mvn package (Reference Picture war_file_structure.png)

    
    For now the domain has been started in port 8088

    After the server has been running we can can access the admin site of Glassfish Server in 4848 port.

    For deploying our application we can select the generated warfile in the Application section.

    And then our app has been deployed.
