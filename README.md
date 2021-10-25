Setting up Spring Cloud Config Server

Step 1: Create a Maven project using Spring Initializr https://start.spring.io/

Step 2: Choose the Spring Boot version 2.2.0 M6 or higher version. Do not choose the snapshot version.

Step 3: Provide the Group name. In our case, com.org.microservices.

Step 4: Provide the Artifact id. We have provided spring-cloud-config-server.

Step 5: Add the Spring Boot DevTools and Config Server dependencies.

Step 6: Click on Generate the project button. A zip file will download, extract it in the hard disk.

Step 7: Now, open the eclipse. Import the downloaded maven project. It will download the required files.

In the next step, we will create a simple Git repository and configure the spring cloud config server to pick up the values from the particular Git repository. We need to install the local Git.

Creating a local repository in Git

Open the Git bash and type the following commands:

Creating a new directory:

mkdir git-localconfig-repo  
cd git-localconfig-repo/  

Initializing a new Git repository:

git init  

It initializes an empty git repository.

Step 3: Now move to the spring-cloud-config-server project and add a link to the specific folder.

Right-click on the spring-cloud-config-server project.

Click on Build Path->Configure Build Path…

Select the Source tab.

Click on Link Source and browse the folder git-localconfig-repo.

Right click on the folder-> New -> Other -> File -> Next -> Provide the file name: limits-service-properties-> Finish.

Now write the following code in the properties file:

limits-service.minimum=8  

limits-service.maximum=888  

Step 4: Configure the user name and user email:

git config -global user.email abc@example.com  

git config -global user.name "abc"  

The command commits any file we have added with the git add command and also commits any files we have changed since then.

git add -A  

Now execute the command to commit

git commit -m "first commit"  
