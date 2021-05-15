
fork of [gitbucket](https://github.com/gitbucket/gitbucket)

* changed path of where lfs objects store on server (incompatible!)
* client skips uploading if file already exists on server (compared with path & size, no integration check)

use at your own risk

### run with docker

$ sbt executable

$ cp ./target/executable/gitbucket.war ./gitbucket.war

$ docker build .

create an alias for the image just built:

$ docker tag 82f634d7cae3 shyang/gitbucket

deploy the image:

$ docker run -d --restart unless-stopped -p 8380:8080 -p 8370:8370 -v /mnt/git-repositories:/gitbucket --name gitbucket1 shyang/gitbucket
