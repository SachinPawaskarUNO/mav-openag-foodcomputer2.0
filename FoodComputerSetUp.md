# **<b>OpenAg - Installation Guide for the Foodcomputer Project</b>**
--------------------------------------------------
# **Installation Operating System - Raspbian Jesse**

First, install a compatible operating system on your SD Card that you will be using inside the Raspberry PI. For Raspberry Pi, we recommend Raspbian Jessie. The image can be downloaded  
>http://downloads.raspberrypi.org/raspbian/images/

and flashed to the SD card. For the current setup we have used
>http://downloads.raspberrypi.org/raspbian/images/raspbian-2017-07-05/

To flash the operating system into SD card we have used a graphical SD
card writing tool called Etcher. The instructions to do so are as
follows:

-   Download [*Etcher*](https://etcher.io/) and install it in
    your laptop.

-   Connect an SD card reader with the SD card inside.

-   Open Etcher and select from your hard drive the Raspberry Pi .img or
    .zip file you wish to write to the SD card.

-   Open Etcher and follow the instructions as follows -

    -   Click on Select Image

    -   Navigate to the image that you get from downloading the zipped
        Raspbian Jessie.

    -   Then Click on Flash button.

<img src="./media/image1.png" width="451" height="322" />

  Fig 1: Select Image from Etcher

 <img src="./media/image2.png" width="548" height="374" />

 Fig 2: Raspbian Jessie Image Navigate

 <img src="./media/image3.png" width="543" height="317" />

 Fig 3: Flash to SD CARD

This would take upto 10-15 minutes to Flash and have the Operating System(OS) validated.

Once we have the OS flashed and validated, plug in the SD card into the raspberry PI and connect it to a monitor, the power cord to raspberry Pi, a ethernet cable and test the connectivity. The monitor should display the newly flashed operating system booting up.
We should be able to see the home screen.


---------------------------------------
# **Setting Up Static Address - Raspberry PI**

---------------------------------------
# **Installing Openag\_brain with Docker**

Click on the terminal and run the following commands to install the brain on the raspberry Pi for the OpenAg project.

Things required here are:

1.  Raspberry Pi3 with Raspbian Jesse pre-installed.

2.  Arduino Mega

Note: If you do not want the camera, disable the service from
docker-composer.yml file –

We wanted to flash the Arduino, so currently disabled the service for camera by commenting the line in devices as highlighted below-

<img src="./media/image4.png" width="624" height="332" />

First, clone this repository on your Raspberry Pi

> git clone https://github.com/OpenAgInitiative/openag\_brain\_docker\_rpi

After cloning the repository, change the directory to
openag\_brain\_docker\_rpi by running the command

> cd openag\_brain\_docker\_rpi

Once we navigate to this directory, we can install docker by running a shell script.

> sh install\_docker.sh

After the installation, restart the operating system.

Start a new terminal session in order for the installation to complete.
Then, the project can be started by running the following:

> docker-compose up -d

The docker containers that are up and running can be seen by giving in the following command-

> docker ps

To check all the logs, if they are working right, give in this command-

> docker logs -f openagbraindockerrpi\_brain\_1

To configure the docker, give in the command-

> docker exec -it openagbraindockerrpi\_brain\_1 bash

When we were trying to flash into the Arduino, the error message that we were getting continuosly was–

<img src="./media/image5.png" width="624" height="170" />

We tried to upgrade the platform with the following command to fix the issue-

> platformio upgrade

<img src="./media/image6.png" width="624" height="71" />

You might notice your cursor prompt will have different text in front of
it. You may also get a few short errors. Disregard them. You are now
INSIDE the docker container where ROS and the OpenAg brain are running!

To initialize the workspace, run the command:

> source catkin\_ws/devel/setup.bash

To flash the Arduino you need to unplug the USB cord from the RaspberryPi an d plug it into a different USB port. Alternatively you can wait 30
seconds and plug it into the same port. This frees the port from other services blocking our way.

Once you've plugged the Arduino back in and type this command:

> rosrun openag\_brain flash

We need to make sure the process exits with SUCCESS. You may need to try this process a few times. Once it does reach around and pat yourself on
the back. You've got a OpenAg brain running!!!

Let's restart the docker container to make sure it's clean and happy and
explore ROS.

Type this command to leave the docker container:

> exit

Then restart the docker containers. Don't worry you won't lose your
changes.

> docker-compose restart

Now let's go back into the container with this command:

> docker exec -it openagbraindockerrpi\_brain\_1 bash

Re-initialize your workspace. You have to do this everytime you restart
the docker container for now.

> source catkin\_ws/devel/setup.bash

Let's take a look at the ROS topics:

> rostopic list

Please note, We need to run the following commands everytime we need to start the containers.

> docker-compose up-d
> docker exec -it openagbraindockerrpi\_brain\_1 bash
> source catkin\_ws/devel/setup.bash
----------------------------------

# **Installing UI**

To setup the control panel or the UI for the OpenAg food computer run
the following command by changing the directory to the root directory.

These shell commands have to be run in the terminal.

We first have to install nodejs/npm

> curl -sL https://deb.nodesource.com/setup\_6.x | sudo -E bash

> sudo apt-get install -y nodejs

Get the code for the UI by running the command to clone from the
repository below.

> git clone <https://github.com/OpenAgInitiative/openag_ui>

To build and deploy, execute the commands below.

> cd openag\_ui

> npm install

> npm run couchapp\_deploy --app\_db\_url="http://localhost:5984/app"

To access the UI

To access the UI locally, replace the IP OF FOOD COMPUTER with localhost

> <http://localhost:5984/app/_design/app/_rewrite>
