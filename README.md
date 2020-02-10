# go-web-hello-world

Task 1: (kernel updgrade to latest available version : v5.5.2)
- downloaded the needed .deb  file from the repo: https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.5.2/ 
for kernel upgrade(v5.5.2)
- Tried installing them however, it failed with reason below:

***linux-headers-5.5.2-050502-generic depends on libssl1.1 (>= 1.1.0); however:
  Package libssl1.1 is not installed***
  
  
-  apt update did not work because ubuntu 16.04 does not have the required openssl version : https://packages.ubuntu.com/xenial/openssl
-  Hence download the openssl source from  https://www.openssl.org/source/openssl-1.1.1d.tar.gz, 
compiled and installed it. Commands are:

'./config'
'sudo apt install make gcc'
'sudo make'
'sudo make install'
'sudo ldconfig'

kumar@MyProjectVM:~/go/src/hello$ openssl version -a

**OpenSSL 1.1.1d  10 Sep 2019**

**built on: Sat Feb  8 13:46:37 2020 UTC**

platform: linux-x86_64**


- kernel upgrade went fine after this.

**kumar@MyProjectVM:~$ uname -a
Linux MyProjectVM 5.5.2-050502-generic #202002041931 SMP Tue Feb 4 19:33:15 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux**


Task 2: installed gitlab-ce following the reference
and able access from my laptop at http://127.0.0.1:8080
and created the project(via webUI)

Task 3/4: following the given references, compiled the hello.go and created a binary named 'hello' which listens on 8081.
since it was only one .go file that required to be pushed to the remote (gitlab), I created the file on gitlab directly via webUI from my laptop and added the code.


Task 5/6/7: installed docker host and created a docker image. Tried running it as container exposing the port with the below command and able to see the message from the service
at http://127.0.0.1:8082.
command: sudo docker run -p vmIp:8082:8081/tcp -d Image

Added the Dockerfile(with content) to gitlab repo via webUI.
Pushed the docker image to : https://hub.docker.com/repository/docker/kumarbavandla/go-web-hello-world/tags?page=1


