# docker-101
## What is docker
* **Docker** is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers.

* **Docker Engine** is an open source containerization technology for building and containerizing your applications

* **Containers** are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels.

* Container's are:
  * lightweight : Absence of Kernel/OS
  * Fast: No booting mechanism
  * Portable: Due to absence of Kernel/OS, it can be easily port from one env to other. Its just like an executable [file] container.
  * Isolated - Uses **namespace**
  * Resource limit - Uses **cgroups** to limit the resource utilization.

  ![Image ipa](https://github.com/NileshChandekar/docker-101/blob/main/images/1.png)

## Installation
* On CentOS-7;

~~~
+----------+---------+------------------------+
|   NAME   |  STATE  |          IPV4          |
+----------+---------+------------------------+
| dockerVM | RUNNING | 192.168.100.219 (eth0) |
+----------+---------+------------------------+
~~~

~~~
[root@dockerVM ~]# cat /etc/redhat-release
CentOS Linux release 7.8.2003 (Core)
[root@dockerVM ~]#
~~~

~~~
[root@dockerVM ~]# yum install docker
~~~

~~~
[root@dockerVM ~]# systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
     Docs: http://docs.docker.com
[root@dockerVM ~]#
~~~

~~~
[root@dockerVM ~]# systemctl restart docker
~~~

~~~
[root@dockerVM ~]# systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; disabled; vendor preset: disabled)
   Active: active (running) since Tue 2020-10-06 03:54:46 UTC; 2s ago
     Docs: http://docs.docker.com
 Main PID: 642 (dockerd-current)
   CGroup: /system.slice/docker.service
           ├─642 /usr/bin/dockerd-current --add-runtime docker-runc=/usr/libexec/docker/docker-runc-current --default-runtime=docker-ru...
           └─654 /usr/bin/docker-containerd-current -l unix:///var/run/docker/libcontainerd/docker-containerd.sock --metrics-interval=0...

Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.593789884Z" level=warning msg="Running modprobe nf_nat ...atus 1"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.594615133Z" level=warning msg="Running modprobe xt_conn...atus 1"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.595977490Z" level=info msg="Firewalld running: false"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.640422759Z" level=info msg="Default bridge (docker0) is...ddress"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.676465772Z" level=info msg="Loading containers: done."
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.677825677Z" level=warning msg="Not using native diff fo...mitted"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.683015780Z" level=info msg="Daemon has completed initialization"
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.683037639Z" level=info msg="Docker daemon" commit="64e9...=1.13.1
Oct 06 03:54:46 dockerVM dockerd-current[642]: time="2020-10-06T03:54:46.686742517Z" level=info msg="API listen on /var/run/docker.sock"
Oct 06 03:54:46 dockerVM systemd[1]: Started Docker Application Container Engine.
Hint: Some lines were ellipsized, use -l to show in full.
[root@dockerVM ~]# systemctl status docker
~~~~


* On Ubuntu;

~~~
+----------+---------+------------------------+
|   NAME   |  STATE  |          IPV4          |
+----------+---------+------------------------+
| ubuntuVM | RUNNING | 192.168.100.127 (eth0) |
+----------+---------+------------------------+
~~~
