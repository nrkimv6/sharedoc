---
title: Jenkins Local setting
updated: 2023-10-25 00:45:47Z
created: 2023-10-25 00:25:22Z
latitude: 37.44491680
longitude: 127.13886840
altitude: 0.0000
---


TODO : 172.90.4.13:8080를 자기 IP&포트로 바꿔주기.



---

Front-end


<a href="{{ site.baseurl }}/assets/Dockerfile">Dockerfile</a>

<a href="{{ site.baseurl }}/assets/제목%20없음.env">.env</a>






---

Backend



<a href="{{ site.baseurl }}/assets/docker-compose.yml">docker-compose.yml</a>



<a href="{{ site.baseurl }}/assets/Dockerfile-1">Dockerfile</a>




<a href="{{ site.baseurl }}/assets/build.sh">build.sh</a>


---

front&back 빌드 명령어 : ./build.sh 



---

Jenkins - setting

#포트열기
sudo nano /etc/pf.conf

#jenkin 포트지정
```
(base) ➜  ~ which jenkins-lts
/usr/local/bin/jenkins-lts
(base) ➜  ~ cd /usr/local/bin/jenkins-lts
cd: not a directory: /usr/local/bin/jenkins-lts
(base) ➜  ~
(base) ➜  ~ cd /usr/local/bin/
(base) ➜  bin ls

(base) ➜  bin ls -l jenkins*
lrwxr-xr-x@ 1 mz01-risingnrkim  admin  45 10 24 10:48 jenkins-lts -> ../Cellar/jenkins-lts/2.414.3/bin/jenkins-lts
lrwxr-xr-x@ 1 mz01-risingnrkim  admin  49 10 24 10:48 jenkins-lts-cli -> ../Cellar/jenkins-lts/2.414.3/bin/jenkins-lts-cli
(base) ➜  bin cd ../Cellar/jenkins-lts/2.414.3
(base) ➜  2.414.3 ls
INSTALL_RECEIPT.json            homebrew.mxcl.jenkins-lts.plist
bin                             libexec
homebrew.jenkins-lts.service
(base) ➜  2.414.3 vim homebrew.mxcl.jenkins-lts.plist
```
vim homebrew.mxcl.jenkins-lts.plist
- 하단에 포트 지정
- ListenAddress : 0.0.0.0  
<img src="{{ site.baseurl }}/assets/eba2bd1791c713a10fd6fc9b2207fb56.png"/>



<img src="{{ site.baseurl }}/assets/3a31bf0e77ea22193ef52edecdcdd245.png"/>


---
Jenkins - pipeline create


<a href="{{ site.baseurl }}/assets/jenkinsfile">jenkinsfile</a>]
동작순서
* backend git pull
* frontend git pull
* frontend build
* backend build
* docker run


  
---
Test : http://172.90.4.13:8082/job/codereview-gpt-admin/

















