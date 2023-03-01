These guides will allow you to setup Nostr within a Docker container with ease.

Download the files in this repo, if you have an icon that you wanna use make sure you put "favicon.ico" in your working directory. 

Make sure you create a proper working directory I'm using Windows so C:\DIRECTORY\NOSTR something simple to locate your files. 

Next use the sample docker-compose.yaml for ease of use keep this file one level up from your nostr directory as we will run the compose file from its directory. 

In the config.toml file you will see entries where you must edit and change your information to reflect your domain and configuration. 

Next we will need nginx attachted is a simple configuration file, note this docker build does not contain nginx this should be setup seperately to keep the container small. 

You can use the sample nginx configuration file also attachted this may need to be a completely new file depending on your setup. 

Next in the directory of your docker-compose file you should have two files "docker-compose.yaml" and the folder "nostr" run the command "docker-compose build" then wait for it to finish and run "docker-compose up -d" this will start the container and it should be online, any issues related to this are most likely nginx configuration issues make sure nginx is running and passes all tests. 
