
#source


https://app.pluralsight.com/course-player?clipId=c0bb7e54-f9d0-43ea-81b2-b90dd25b3213
https://app.pluralsight.com/library/courses/docker-web-developers/table-of-contents



# Using a Container Volume for Logging

### Build the Image
To build the image run the following command from the `LoggingToAVolume` folder:

`docker build -t logging-to-a-volume .`
 
### Run the Container

To run the container run with a custom volume location:

`docker run -d -p 3000:3000 -v "$(pwd)/logs":/var/www/logs logging-to-a-volume`

NOTE: The `$(pwd)` command is for Linux, Mac, and WSL on Windows. If you are using PowerShell on Windows, you will need to use `${PWD}` instead. The quotes around `"$(pwd)/logs"` are generally only needed if you have a space character in the working directory path.

Visit http://localhost:3000 and refresh the page a few times. Then open the `logs/access.log` file and you should see the log entries.

### Additional Docker Commands Run in the demo

`docker volume --help`
`docker volume ls`
`docker inspect <container-name>`
`docker volume inspect <volume-name>`

 