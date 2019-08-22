# Docker Notes

Here is a youtube Docker Introduction: [link](https://youtu.be/VlSW-tztsvM)
Here is another Udemy vidoe: [link](https://www.udemy.com/docker-mastery/learn/lecture/7742916#overview)

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



[docker: Got permission denied issue](https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue)
```
sudo chmod 666 /var/run/docker.sock
```

Here is a link for Markdown Guides on GitHub platform
* [Markdown Guides](https://guides.github.com/features/mastering-markdown/)
* [Another Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)




## Git
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


## [bintrees](https://pypi.org/project/bintrees/)
Installation
```
pip install bintrees
```
[Outdated binary tree package, please switch to sortedcontainers](https://github.com/mozman/bintrees)\
The sortedcontainers module is the best-in-class module for sorted sets and sorted dictionaries.



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
