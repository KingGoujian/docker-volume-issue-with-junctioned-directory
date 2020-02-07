# docker-volume-issue-with-junctioned-directory
https://github.com/docker/for-win/issues/5530

Platform: Windows 10 Pro Version	10.0.18363 Build 18363

Pull the git repository

Create Junction using command line in the repo folder
mklink /J sub2\common\ sub1\

then run 
docker-compose build

and 
docker-compose run sub2 sh

/usr/src/app # ls -latr
total 4
lrwxr-xr-x    1 root     root             0 Feb  7 11:35 common -> ../sub1
drwxr-xr-x    3 root     root          4096 Feb  7 11:40 ..
-rwxr-xr-x    1 root     root            93 Feb  7 11:40 Dockerfile
drwxrwxrwx    1 root     root             0 Feb  7 11:46 .
drwxrwxrwx    1 root     root             0 Feb  7 11:46 realdir
