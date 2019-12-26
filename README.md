# Install-Nginx-on-Centos7
## Step 1 install the prerequisites
```
# sudo yum -y install yum-utils
```
## Step 2 Set up the yum repository，create the file name /etc/yum.repos.d/nginx.repo with the folling contents:
```
[nginx-stable]
name=nginx stable repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=1
enabled=1
gpgkey=http://nginx.org/keys/nginx_signing.key
moudle_hotfixes=true

[nginx-mainline]
name=nginx mainline repo
baseurl=http://nginx.org/packages/mainline/centos/$releasever/$basearch/
gpgcheck=1
enabled=0
gpgkey=https://nginx.org/keys/nginx_signing.key
moudle_hotfixes=true
```
## Step 3 By default，the repository for stable nginx packages is used.If you would like to use mainline nginx packages，run the following command:
```
# sudo yum-config-manager --enable nginx-mainline
```
## Step 4 install nginx，run the following command:
```
# sudo yum -y install nginx
```
When promoted to accept the GPG key，verify that the fingerprint maches 573B FD6B 3D8F BC64 1079 A6AB ABF5 BD82 7BD9 BF62，and if so，accept it.
