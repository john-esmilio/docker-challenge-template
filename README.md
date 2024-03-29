
Docker Challenge
These challenges were done on the Windows 11 Operating Home system.
For a Docker tutorial using the Linux, or MacOS operating systems, please look elsewhere.
Prerequisites
Software(s) Needed:
-	Visual Studio Code or similar IDE
-	Git
-	Docker Desktop
Other things needed:
-	GitHub Account
-	Provided “Challenge2.zip” folder 
Challenge One
Steps to follow:
1.	Navigate to this link, to start the repository fork process.
2.	Create a fork of the docker challenge on GitHub. A fork is a copy of a repository.
a.	The fork button is between the watch and star buttons, which is to the right of the GitHub repository title.
3.	Create a folder wherever you want the Docker challenge to live in, open that folder in the file explorer, and run command prompt by typing “cmd” in the address bar within the file explorer of your desired folder.
4.	Create a clone of the repository with this command, git clone (GitHub link).
a.	e.g., git clone https://github.com/john-esmilio/docker-challenge-template

5.	Open this new folder within the file explorer.
6.	In the “challenge1” folder, create a new folder named “public”, and inside that, create an index.html file, and a file called “Dockerfile”.
7.	Open the index.html file with Visual Studio Code or your preferred IDE, and within the body tags of the HTML file, insert your student credentials (name, and ID) into a div. Save the HTML file.
8.	Open the Dockerfile, and insert the command listed below:
FROM nginx
COPY index.html /usr/share/nginx/html
EXPOSE 80 
a.	Save this Dockerfile.
9.	Navigate back to the public folder in the file explorer, and in the command line, enter this command: “docker build -t <Tag Name> .” (Including the space and the period at the end). This will build a docker image.
a.	E.g., docker build -t docker-challenge . 

10.	Head to docker desktop to run the container. In the images tab (the dashed lined box on the left), you will see your container waiting to be executed. Select the play button and click on optional settings. In the ports input, enter 8080.
11.	Select run to run the container.
12.	On your web browser, head to http://localhost:8080/.
13.	If done correctly, you will see the hosted HTML file with your student information on the localhost.

Challenge 2
Docker Compose
What is Docker Compose? Docker Compose is a helpful utility that allows you to run multiple containers within Docker [2]. Using Docker Compose gives users an easier time to manage networks and services in a configuration file, and this configuration file can run all the services provided [2].
Required Files/Folders
-	The provided challenge2.zip folder.
Steps to Complete
1.	Navigate to the downloaded “challenge2.zip” folder. 
2.	Extract the files from the downloaded folder, and copy/move them into the “challenge2” folder that was forked from the forked repository from the last challenge.
3.	Create a DockerFile within the forked “challenge2” folder and enter these commands within the file (save this file after):
FROM node:18.7.0
WORKDIR /
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]
4.	Create a yml file named “docker-compose.yml” within the forked “challenge2” folder and enter these commands within the file (save this file after):
version: '3.8'
services:
  app:
    build: .
    ports:
      - '8080:3000'
    environment:
      - PORT=3000
5.	In the file explorer, within the “challenge2” folder, open the command prompt via the address bar and enter the command “cmd.”
6.	Enter this command: “docker built -t challenge 2 . “.
7.	Open Docker Desktop and select “Images” on the left navigation bar.
8.	Press the play button and in the Optional Settings, enter 8080 in the host port.
9.	Press “Run” to run the image.
10.	When the image is finished building, head to http://localhost:8080/api/books to see a JSON message with all books.
11.	Head to http://localhost:8080/api/books/1 to see a JSON message with only one book.
 


