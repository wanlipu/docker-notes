# Docker Notes

Here is a youtube Docker Introduction: [link](https://youtu.be/VlSW-tztsvM) \
Here is another Udemy vidoe: [link](https://www.udemy.com/docker-mastery/learn/lecture/7742916#overview)

## CSE6250 LAB
Please the instructions in the [lab section](http://www.sunlab.org/teaching/cse6250/fall2019/env/) to install docker and run docker containers

After installing docker for Ubuntu, you may run into [docker: Got permission denied issue](https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue)
you can use following command to address the issue
```
sudo chmod 666 /var/run/docker.sock
```
The same command should be run to start your docker service every time after restarting your computer. 

## After finishing install docker for Ubuntu
Inside of terminal, to show existing docker images
```
$ docker images 
```
To run docker container
```
$ docker run busybox:1.24 # optional echo "hello world"
```
To run interactive docker container
```
$ docker run -i -t busybox:1.24
```
to show existing docker containers
```
$ docker container ls -a
```
[How To Remove Docker Containers, Images, Volumes, and Networks](https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/)


[vscode Developing inside a Container](https://code.visualstudio.com/docs/remote/containers)

[vscode Working with Docker](https://code.visualstudio.com/docs/azure/docker)

[Run docker image with vscode](https://github.com/cmiles74/docker-vscode)





Here is a link for Markdown Guides on GitHub platform
* [Markdown Guides](https://guides.github.com/features/mastering-markdown/)
* [Another Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)


## When you want to restart your existing container
check existing containers info
```
$ docker ps -a
```
To start a container again
```
$ docker start <CONTAINER ID or NAME>
```
Then attach it by
```
$ docker attach <CONTAINER ID or NAME>
```
Every time you restart your container, you are supposed to start all those services again before any HDFS related operations.

## Start all necessary services
```
# /scripts/start-services.sh
```


## Git
[instructions](https://linuxize.com/post/how-to-install-git-on-ubuntu-18-04/)

* install git
```
$ sudo apt install git
```
* git version
```
$ git --version
```

## vscode with docker extension
* in terminal
```
$ code . # to open current directory in vscode
```
* git version
```
$ git --version
```
Config git 
```
$ git config --global user.name "Your Name"
$ git config --global user.email "youremail@yourdomain.com"
```

## Bind Mounting
* Maps a host file or directory to a container file or directory
* Basically just two locations pointing to the same file(s)
* Again, skips UFS, and host files overwrite any in container
* Can't use in Dockerfile, must be at container run
```
$ ... run -v /Users/wanli/stuff:/path/container (mac/linus)
$ ... run -v //c/Users/wanli/stuff:/path/container (windows)
```

```
docker run -it --privileged=true \
  --cap-add=SYS_ADMIN \
  -m 8192m -h bootcamp.local \
  --name bigbox -p 2222:22 -p 9530:9530 -p 8888:8888\
  -v /:/mnt/host \
  sunlab/bigbox:latest \
  /bin/bash
 ```

## Homework 1 Environment
Use the provided .yml file to create a new conda environment 
```
$ conda env create -f environment.yml
```
Active the conda version
```
$ source activate homework1
```
Deactive the conda version
```
$ source deactivate
```

## HDFS Operations
First, you will need to switch to the hdfs user via
```
# sudo su - hdfs
```
Then, you can create a directory and change ownership of the newly created folder
```
> hdfs dfs -mkdir -p /user/<username> # username is root
> hdfs dfs -chown <username> /user/<username> # username is root
> exit
```
Similar to creating local directory via linux command mkdir, creating a folder named input in HDFS use
```
> hdfs dfs -mkdir input
```
or
```
> hdfs dfs -mkdir input/events
```
to list hdfs files
```
> hdfs dfs -ls input
> hdfs dfs -ls input/events
```


Suppose you followed previous instructions and created an directory named input, you can then copy data from local file system to HDFS using -put. For example,
```
> cd /bigdata-bootcamp/data
> hdfs dfs -put case.csv input
> hdfs dfs -put control.csv input
```
```
> hdfs dfs -put /mnt/host/Users/{USERNAME}/path/to/file /input/events
```
```
> hdfs dfs -put /mnt/host/home/wanli/cse6250/bigdata4health/homework2/data/events.csv input/events
> hdfs dfs -put /mnt/host/home/wanli/cse6250/bigdata4health/homework2/data/mortality.csv input/mortality
```


## FLASK
Please go to [cs50 link](https://docs.cs50.net/web/2019/x/projects/1/project1.html) for instructions.

```
set FLASK_APP=application.py
set set DATABASE_URL=postgres://*** (from your heruku database url)
set FLASK_DEBUG=1 (to reload web application whenever you save a change to a file)
python -m flask run (sometime 'flask run' won't work, use 'python -m flask run' instead)
```
## MongoDB
Please go to [MongoDB Ebook](https://mongodb.tecladocode.com/) for instructions.\
Show Databases (cmd)
```
show dbs
```
Checkout/switch to database (cmd)
```
use database_name(*)
```
Show current database (cmd)
```
db
```
Show Collections in current database (cmd)
```
show collections
```
Query certain collection in current database (cmd)
```
db.posts.find({}).pretty() (replace posts with other collection name)
```
Remove instances in collections with query
```
db.posts.remove({}) (replace posts with other collection name)
```
## Draw Pretty Neural Network Sketch
[link](http://alexlenail.me/NN-SVG/index.html)
