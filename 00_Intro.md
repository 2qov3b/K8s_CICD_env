---
layout: lecture
title: "CI/CD In Kubernetes"
date: 2020-05-02
ready: true
video:
  aspect:
  id:
---

{% comment %}
[Configure for containers](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)
{% endcomment %}

# Prerequisite
## Container(Docker)
- Dockerfile

## Kubernetes
- Concept
*Master/Slave*, *Controller*, *Deployment*, *Pod*...etc

- Operations
*Kubectl*
*Deploy resources*

# Kubernetes
(diagram)

# How To Use Kubernetes
## Application
- Services are businesses logic.
- Kubernetes is a deployment tool/platform - Can switch to other tools.
*CI/CD Workflow*
(diagram)

## Infrastructure
- Customize K8s platform.
Provide powerful features.
K8s Service: Public/Private Cloud solution.
*CI/CD Workflow*
(diagram)

# Others
How to run test for 2 use cases? (Application/Infrastructure)
How to update K8s yaml? (Multiple K8s)
Container registry (Public/Private)
How CI server accesses K8s? (Public/Private)
How to update services? (Blue green deployment/others)

# Service Introduction



```console
$ vagrant up
Bringing machine 'k8s' up with 'virtualbox' provider...
==> k8s: Importing base box 'bento/ubuntu-18.04'...
==> k8s: Matching MAC address for NAT networking...
==> k8s: Checking if box 'bento/ubuntu-18.04' version '201912.14.0' is up to date...
==> k8s: Setting the name of the VM: kind_k8s_1588405254927_90309
==> k8s: Clearing any previously set network interfaces...
==> k8s: Preparing network interfaces based on configuration...
    k8s: Adapter 1: nat
    k8s: Adapter 2: hostonly
==> k8s: Forwarding ports...
    k8s: 22 (guest) => 2222 (host) (adapter 1)
==> k8s: Running 'pre-boot' VM customizations...
==> k8s: Booting VM...
==> k8s: Waiting for machine to boot. This may take a few minutes...
    k8s: SSH address: 127.0.0.1:2222
    k8s: SSH username: vagrant
    k8s: SSH auth method: private key
    k8s: 
    k8s: Vagrant insecure key detected. Vagrant will automatically replace
    k8s: this with a newly generated keypair for better security.
    k8s: 
    k8s: Inserting generated public key within guest...
    k8s: Removing insecure key from the guest if it's present...
    k8s: Key inserted! Disconnecting and reconnecting using new SSH key...
==> k8s: Machine booted and ready!
==> k8s: Checking for guest additions in VM...
==> k8s: Setting hostname...
==> k8s: Configuring and enabling network interfaces...
==> k8s: Mounting shared folders...
    k8s: /vagrant => /Users/xxx/vagrant/kind
==> k8s: Running provisioner: shell...
    k8s: Running: inline script
    k8s: ++ export DEBIAN_FRONTEND=noninteractive
    k8s: ++ DEBIAN_FRONTEND=noninteractive
    k8s: ++ sudo apt-get update
    k8s: Hit:1 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Get:2 http://archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
    k8s: Get:3 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
    k8s: Get:4 http://archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
    k8s: Get:5 http://security.ubuntu.com/ubuntu bionic-security/main i386 Packages [464 kB]
    k8s: Get:6 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [932 kB]
    k8s: Get:7 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [707 kB]
    k8s: Get:8 http://archive.ubuntu.com/ubuntu bionic-updates/main i386 Packages [675 kB]
    k8s: Get:9 http://security.ubuntu.com/ubuntu bionic-security/main Translation-en [224 kB]
    k8s: Get:10 http://archive.ubuntu.com/ubuntu bionic-updates/main Translation-en [318 kB]
    k8s: Get:11 http://security.ubuntu.com/ubuntu bionic-security/restricted amd64 Packages [40.3 kB]
    k8s: Get:12 http://security.ubuntu.com/ubuntu bionic-security/restricted Translation-en [10.2 kB]
    k8s: Get:13 http://security.ubuntu.com/ubuntu bionic-security/universe i386 Packages [619 kB]
    k8s: Get:14 http://archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [50.2 kB]
    k8s: Get:15 http://archive.ubuntu.com/ubuntu bionic-updates/restricted i386 Packages [9,924 B]
    k8s: Get:16 http://archive.ubuntu.com/ubuntu bionic-updates/restricted Translation-en [12.6 kB]
    k8s: Get:17 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1,068 kB]
    k8s: Get:18 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [660 kB]
    k8s: Get:19 http://archive.ubuntu.com/ubuntu bionic-updates/universe i386 Packages [1,014 kB]
    k8s: Get:20 http://security.ubuntu.com/ubuntu bionic-security/universe Translation-en [219 kB]
    k8s: Get:21 http://security.ubuntu.com/ubuntu bionic-security/multiverse i386 Packages [4,288 B]
    k8s: Get:22 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [7,392 B]
    k8s: Get:23 http://security.ubuntu.com/ubuntu bionic-security/multiverse Translation-en [2,788 B]
    k8s: Get:24 http://archive.ubuntu.com/ubuntu bionic-updates/universe Translation-en [332 kB]
    k8s: Get:25 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [15.5 kB]
    k8s: Get:26 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse i386 Packages [8,760 B]
    k8s: Get:27 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse Translation-en [6,352 B]
    k8s: Get:28 http://archive.ubuntu.com/ubuntu bionic-backports/main amd64 Packages [7,516 B]
    k8s: Get:29 http://archive.ubuntu.com/ubuntu bionic-backports/main i386 Packages [7,508 B]
    k8s: Get:30 http://archive.ubuntu.com/ubuntu bionic-backports/main Translation-en [4,764 B]
    k8s: Get:31 http://archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [7,484 B]
    k8s: Get:32 http://archive.ubuntu.com/ubuntu bionic-backports/universe i386 Packages [7,472 B]
    k8s: Get:33 http://archive.ubuntu.com/ubuntu bionic-backports/universe Translation-en [4,436 B]
    k8s: Fetched 7,693 kB in 5s (1,626 kB/s)
    k8s: Reading package lists...
    k8s: ++ sudo apt-get install -y vim git cmake build-essential tcpdump tig jq socat bash-completion
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: Reading state information...
    k8s: The following additional packages will be installed:
    k8s:   cmake-data cpp-7 dpkg-dev fakeroot g++ g++-7 gcc gcc-7 gcc-7-base gcc-8-base
    k8s:   libalgorithm-diff-perl libalgorithm-diff-xs-perl libalgorithm-merge-perl
    k8s:   libarchive13 libasan4 libatomic1 libcc1-0 libcilkrts5 libdpkg-perl
    k8s:   libfakeroot libfile-fcntllock-perl libgcc-7-dev libgcc1 libgomp1 libitm1
    k8s:   libjq1 libjsoncpp1 liblsan0 libmpx2 libonig4 libquadmath0 librhash0
    k8s:   libstdc++-7-dev libstdc++6 libtsan0 libubsan0 vim-common vim-runtime
    k8s:   vim-tiny
    k8s: Suggested packages:
    k8s:   cmake-doc ninja-build gcc-7-locales debian-keyring g++-multilib
    k8s:   g++-7-multilib gcc-7-doc libstdc++6-7-dbg gcc-multilib manpages-dev autoconf
    k8s:   automake libtool flex bison gdb gcc-doc gcc-7-multilib libgcc1-dbg
    k8s:   libgomp1-dbg libitm1-dbg libatomic1-dbg libasan4-dbg liblsan0-dbg
    k8s:   libtsan0-dbg libubsan0-dbg libcilkrts5-dbg libmpx2-dbg libquadmath0-dbg
    k8s:   git-daemon-run | git-daemon-sysvinit git-doc git-el git-email git-gui gitk
    k8s:   gitweb git-cvs git-mediawiki git-svn lrzip bzr libstdc++-7-doc ctags vim-doc
    k8s:   vim-scripts indent
    k8s: The following NEW packages will be installed:
    k8s:   bash-completion build-essential cmake cmake-data dpkg-dev fakeroot g++ g++-7
    k8s:   gcc gcc-7 jq libalgorithm-diff-perl libalgorithm-diff-xs-perl
    k8s:   libalgorithm-merge-perl libarchive13 libasan4 libatomic1 libcc1-0
    k8s:   libcilkrts5 libdpkg-perl libfakeroot libfile-fcntllock-perl libgcc-7-dev
    k8s:   libgomp1 libitm1 libjq1 libjsoncpp1 liblsan0 libmpx2 libonig4 libquadmath0
    k8s:   librhash0 libstdc++-7-dev libtsan0 libubsan0 socat tig
    k8s: The following packages will be upgraded:
    k8s:   cpp-7 gcc-7-base gcc-8-base git libgcc1 libstdc++6 tcpdump vim vim-common
    k8s:   vim-runtime vim-tiny
    k8s: 11 upgraded, 37 newly installed, 0 to remove and 91 not upgraded.
    k8s: Need to get 51.7 MB of archives.
    k8s: After this operation, 124 MB of additional disk space will be used.
    k8s: Get:1 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-8-base amd64 8.4.0-1ubuntu1~18.04 [18.7 kB]
    k8s: Get:2 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libstdc++6 amd64 8.4.0-1ubuntu1~18.04 [400 kB]
    k8s: Get:3 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgcc1 amd64 1:8.4.0-1ubuntu1~18.04 [40.6 kB]
    k8s: Get:4 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim amd64 2:8.0.1453-1ubuntu1.3 [1,153 kB]
    k8s: Get:5 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-tiny amd64 2:8.0.1453-1ubuntu1.3 [476 kB]
    k8s: Get:6 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-runtime all 2:8.0.1453-1ubuntu1.3 [5,436 kB]
    k8s: Get:7 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-common all 2:8.0.1453-1ubuntu1.3 [70.6 kB]
    k8s: Get:8 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 git amd64 1:2.17.1-1ubuntu0.7 [3,915 kB]
    k8s: Get:9 http://archive.ubuntu.com/ubuntu bionic/main amd64 bash-completion all 1:2.8-1ubuntu1 [168 kB]
    k8s: Get:10 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 tcpdump amd64 4.9.3-0ubuntu0.18.04.1 [364 kB]
    k8s: Get:11 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cpp-7 amd64 7.5.0-3ubuntu1~18.04 [8,591 kB]
    k8s: Get:12 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-7-base amd64 7.5.0-3ubuntu1~18.04 [18.3 kB]
    k8s: Get:13 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcc1-0 amd64 8.4.0-1ubuntu1~18.04 [39.4 kB]
    k8s: Get:14 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgomp1 amd64 8.4.0-1ubuntu1~18.04 [76.5 kB]
    k8s: Get:15 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libitm1 amd64 8.4.0-1ubuntu1~18.04 [27.9 kB]
    k8s: Get:16 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libatomic1 amd64 8.4.0-1ubuntu1~18.04 [9,192 B]
    k8s: Get:17 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasan4 amd64 7.5.0-3ubuntu1~18.04 [358 kB]
    k8s: Get:18 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 liblsan0 amd64 8.4.0-1ubuntu1~18.04 [133 kB]
    k8s: Get:19 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libtsan0 amd64 8.4.0-1ubuntu1~18.04 [288 kB]
    k8s: Get:20 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libubsan0 amd64 7.5.0-3ubuntu1~18.04 [126 kB]
    k8s: Get:21 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcilkrts5 amd64 7.5.0-3ubuntu1~18.04 [42.5 kB]
    k8s: Get:22 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libmpx2 amd64 8.4.0-1ubuntu1~18.04 [11.6 kB]
    k8s: Get:23 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libquadmath0 amd64 8.4.0-1ubuntu1~18.04 [134 kB]
    k8s: Get:24 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgcc-7-dev amd64 7.5.0-3ubuntu1~18.04 [2,378 kB]
    k8s: Get:25 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-7 amd64 7.5.0-3ubuntu1~18.04 [9,381 kB]
    k8s: Get:26 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc amd64 4:7.4.0-1ubuntu2.3 [5,184 B]
    k8s: Get:27 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libstdc++-7-dev amd64 7.5.0-3ubuntu1~18.04 [1,471 kB]
    k8s: Get:28 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 g++-7 amd64 7.5.0-3ubuntu1~18.04 [9,697 kB]
    k8s: Get:29 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 g++ amd64 4:7.4.0-1ubuntu2.3 [1,568 B]
    k8s: Get:30 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdpkg-perl all 1.19.0.5ubuntu2.3 [211 kB]
    k8s: Get:31 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 dpkg-dev all 1.19.0.5ubuntu2.3 [607 kB]
    k8s: Get:32 http://archive.ubuntu.com/ubuntu bionic/main amd64 build-essential amd64 12.4ubuntu1 [4,758 B]
    k8s: Get:33 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake-data all 3.10.2-1ubuntu2.18.04.1 [1,332 kB]
    k8s: Get:34 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libarchive13 amd64 3.2.2-3.1ubuntu0.6 [288 kB]
    k8s: Get:35 http://archive.ubuntu.com/ubuntu bionic/main amd64 libjsoncpp1 amd64 1.7.4-3 [73.6 kB]
    k8s: Get:36 http://archive.ubuntu.com/ubuntu bionic/main amd64 librhash0 amd64 1.3.6-2 [78.1 kB]
    k8s: Get:37 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake amd64 3.10.2-1ubuntu2.18.04.1 [3,152 kB]
    k8s: Get:38 http://archive.ubuntu.com/ubuntu bionic/main amd64 libfakeroot amd64 1.22-2ubuntu1 [25.9 kB]
    k8s: Get:39 http://archive.ubuntu.com/ubuntu bionic/main amd64 fakeroot amd64 1.22-2ubuntu1 [62.3 kB]
    k8s: Get:40 http://archive.ubuntu.com/ubuntu bionic/universe amd64 libonig4 amd64 6.7.0-1 [119 kB]
    k8s: Get:41 http://archive.ubuntu.com/ubuntu bionic/universe amd64 libjq1 amd64 1.5+dfsg-2 [111 kB]
    k8s: Get:42 http://archive.ubuntu.com/ubuntu bionic/universe amd64 jq amd64 1.5+dfsg-2 [45.6 kB]
    k8s: Get:43 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-perl all 1.19.03-1 [47.6 kB]
    k8s: Get:44 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-xs-perl amd64 0.04-5 [11.1 kB]
    k8s: Get:45 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-merge-perl all 0.08-3 [12.0 kB]
    k8s: Get:46 http://archive.ubuntu.com/ubuntu bionic/main amd64 libfile-fcntllock-perl amd64 0.22-3build2 [33.2 kB]
    k8s: Get:47 http://archive.ubuntu.com/ubuntu bionic/universe amd64 tig amd64 2.3.0-1 [299 kB]
    k8s: Get:48 http://archive.ubuntu.com/ubuntu bionic/main amd64 socat amd64 1.7.3.2-2ubuntu2 [342 kB]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 51.7 MB in 9s (5,573 kB/s)
    k8s: (Reading database ... 
    k8s: (Reading database ... 5%
    k8s: (Reading database ... 10%
    k8s: (Reading database ... 15%
    k8s: (Reading database ... 20%
    k8s: (Reading database ... 25%
    k8s: (Reading database ... 30%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
    k8s: (Reading database ... 100%
    k8s: (Reading database ... 
    k8s: 42631 files and directories currently installed.)
    k8s: Preparing to unpack .../gcc-8-base_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking gcc-8-base:amd64 (8.4.0-1ubuntu1~18.04) over (8.3.0-6ubuntu1~18.04.1) ...
    k8s: Setting up gcc-8-base:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: (Reading database ... 
    k8s: (Reading database ... 5%
    k8s: (Reading database ... 10%
    k8s: (Reading database ... 15%
    k8s: (Reading database ... 20%
    k8s: (Reading database ... 25%
    k8s: (Reading database ... 30%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
    k8s: (Reading database ... 100%
    k8s: (Reading database ... 
    k8s: 42631 files and directories currently installed.)
    k8s: Preparing to unpack .../libstdc++6_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libstdc++6:amd64 (8.4.0-1ubuntu1~18.04) over (8.3.0-6ubuntu1~18.04.1) ...
    k8s: Setting up libstdc++6:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: (Reading database ... 
(Reading database ... 15%e ... 5%
    k8s: (Reading database ... 20%
(Reading database ... 30%e ... 25%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
(Reading database ... 42631 files and directories currently installed.)
    k8s: Preparing to unpack .../libgcc1_1%3a8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libgcc1:amd64 (1:8.4.0-1ubuntu1~18.04) over (1:8.3.0-6ubuntu1~18.04.1) ...
    k8s: Setting up libgcc1:amd64 (1:8.4.0-1ubuntu1~18.04) ...
    k8s: (Reading database ... 
(Reading database ... 15%e ... 5%
    k8s: (Reading database ... 20%
(Reading database ... 30%e ... 25%
    k8s: (Reading database ... 35%
(Reading database ... 45%e ... 40%
(Reading database ... 55%e ... 50%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
(Reading database ... 42631 files and directories currently installed.)
    k8s: Preparing to unpack .../00-vim_2%3a8.0.1453-1ubuntu1.3_amd64.deb ...
    k8s: Unpacking vim (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1.1) ...
    k8s: Preparing to unpack .../01-vim-tiny_2%3a8.0.1453-1ubuntu1.3_amd64.deb ...
    k8s: Unpacking vim-tiny (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1.1) ...
    k8s: Preparing to unpack .../02-vim-runtime_2%3a8.0.1453-1ubuntu1.3_all.deb ...
    k8s: Unpacking vim-runtime (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1.1) ...
    k8s: Preparing to unpack .../03-vim-common_2%3a8.0.1453-1ubuntu1.3_all.deb ...
    k8s: Unpacking vim-common (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1.1) ...
    k8s: Preparing to unpack .../04-git_1%3a2.17.1-1ubuntu0.7_amd64.deb ...
    k8s: Unpacking git (1:2.17.1-1ubuntu0.7) over (1:2.17.1-1ubuntu0.5) ...
    k8s: Selecting previously unselected package bash-completion.
    k8s: Preparing to unpack .../05-bash-completion_1%3a2.8-1ubuntu1_all.deb ...
    k8s: Unpacking bash-completion (1:2.8-1ubuntu1) ...
    k8s: Preparing to unpack .../06-tcpdump_4.9.3-0ubuntu0.18.04.1_amd64.deb ...
    k8s: Unpacking tcpdump (4.9.3-0ubuntu0.18.04.1) over (4.9.2-3) ...
    k8s: Preparing to unpack .../07-cpp-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking cpp-7 (7.5.0-3ubuntu1~18.04) over (7.4.0-1ubuntu1~18.04.1) ...
    k8s: Preparing to unpack .../08-gcc-7-base_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking gcc-7-base:amd64 (7.5.0-3ubuntu1~18.04) over (7.4.0-1ubuntu1~18.04.1) ...
    k8s: Selecting previously unselected package libcc1-0:amd64.
    k8s: Preparing to unpack .../09-libcc1-0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libcc1-0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libgomp1:amd64.
    k8s: Preparing to unpack .../10-libgomp1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libgomp1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libitm1:amd64.
    k8s: Preparing to unpack .../11-libitm1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libitm1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libatomic1:amd64.
    k8s: Preparing to unpack .../12-libatomic1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libatomic1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libasan4:amd64.
    k8s: Preparing to unpack .../13-libasan4_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libasan4:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package liblsan0:amd64.
    k8s: Preparing to unpack .../14-liblsan0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking liblsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libtsan0:amd64.
    k8s: Preparing to unpack .../15-libtsan0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libtsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libubsan0:amd64.
    k8s: Preparing to unpack .../16-libubsan0_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libubsan0:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libcilkrts5:amd64.
    k8s: Preparing to unpack .../17-libcilkrts5_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libcilkrts5:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libmpx2:amd64.
    k8s: Preparing to unpack .../18-libmpx2_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libmpx2:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libquadmath0:amd64.
    k8s: Preparing to unpack .../19-libquadmath0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libquadmath0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Selecting previously unselected package libgcc-7-dev:amd64.
    k8s: Preparing to unpack .../20-libgcc-7-dev_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libgcc-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package gcc-7.
    k8s: Preparing to unpack .../21-gcc-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking gcc-7 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package gcc.
    k8s: Preparing to unpack .../22-gcc_4%3a7.4.0-1ubuntu2.3_amd64.deb ...
    k8s: Unpacking gcc (4:7.4.0-1ubuntu2.3) ...
    k8s: Selecting previously unselected package libstdc++-7-dev:amd64.
    k8s: Preparing to unpack .../23-libstdc++-7-dev_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking libstdc++-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package g++-7.
    k8s: Preparing to unpack .../24-g++-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    k8s: Unpacking g++-7 (7.5.0-3ubuntu1~18.04) ...
    k8s: Selecting previously unselected package g++.
    k8s: Preparing to unpack .../25-g++_4%3a7.4.0-1ubuntu2.3_amd64.deb ...
    k8s: Unpacking g++ (4:7.4.0-1ubuntu2.3) ...
    k8s: Selecting previously unselected package libdpkg-perl.
    k8s: Preparing to unpack .../26-libdpkg-perl_1.19.0.5ubuntu2.3_all.deb ...
    k8s: Unpacking libdpkg-perl (1.19.0.5ubuntu2.3) ...
    k8s: Selecting previously unselected package dpkg-dev.
    k8s: Preparing to unpack .../27-dpkg-dev_1.19.0.5ubuntu2.3_all.deb ...
    k8s: Unpacking dpkg-dev (1.19.0.5ubuntu2.3) ...
    k8s: Selecting previously unselected package build-essential.
    k8s: Preparing to unpack .../28-build-essential_12.4ubuntu1_amd64.deb ...
    k8s: Unpacking build-essential (12.4ubuntu1) ...
    k8s: Selecting previously unselected package cmake-data.
    k8s: Preparing to unpack .../29-cmake-data_3.10.2-1ubuntu2.18.04.1_all.deb ...
    k8s: Unpacking cmake-data (3.10.2-1ubuntu2.18.04.1) ...
    k8s: Selecting previously unselected package libarchive13:amd64.
    k8s: Preparing to unpack .../30-libarchive13_3.2.2-3.1ubuntu0.6_amd64.deb ...
    k8s: Unpacking libarchive13:amd64 (3.2.2-3.1ubuntu0.6) ...
    k8s: Selecting previously unselected package libjsoncpp1:amd64.
    k8s: Preparing to unpack .../31-libjsoncpp1_1.7.4-3_amd64.deb ...
    k8s: Unpacking libjsoncpp1:amd64 (1.7.4-3) ...
    k8s: Selecting previously unselected package librhash0:amd64.
    k8s: Preparing to unpack .../32-librhash0_1.3.6-2_amd64.deb ...
    k8s: Unpacking librhash0:amd64 (1.3.6-2) ...
    k8s: Selecting previously unselected package cmake.
    k8s: Preparing to unpack .../33-cmake_3.10.2-1ubuntu2.18.04.1_amd64.deb ...
    k8s: Unpacking cmake (3.10.2-1ubuntu2.18.04.1) ...
    k8s: Selecting previously unselected package libfakeroot:amd64.
    k8s: Preparing to unpack .../34-libfakeroot_1.22-2ubuntu1_amd64.deb ...
    k8s: Unpacking libfakeroot:amd64 (1.22-2ubuntu1) ...
    k8s: Selecting previously unselected package fakeroot.
    k8s: Preparing to unpack .../35-fakeroot_1.22-2ubuntu1_amd64.deb ...
    k8s: Unpacking fakeroot (1.22-2ubuntu1) ...
    k8s: Selecting previously unselected package libonig4:amd64.
    k8s: Preparing to unpack .../36-libonig4_6.7.0-1_amd64.deb ...
    k8s: Unpacking libonig4:amd64 (6.7.0-1) ...
    k8s: Selecting previously unselected package libjq1:amd64.
    k8s: Preparing to unpack .../37-libjq1_1.5+dfsg-2_amd64.deb ...
    k8s: Unpacking libjq1:amd64 (1.5+dfsg-2) ...
    k8s: Selecting previously unselected package jq.
    k8s: Preparing to unpack .../38-jq_1.5+dfsg-2_amd64.deb ...
    k8s: Unpacking jq (1.5+dfsg-2) ...
    k8s: Selecting previously unselected package libalgorithm-diff-perl.
    k8s: Preparing to unpack .../39-libalgorithm-diff-perl_1.19.03-1_all.deb ...
    k8s: Unpacking libalgorithm-diff-perl (1.19.03-1) ...
    k8s: Selecting previously unselected package libalgorithm-diff-xs-perl.
    k8s: Preparing to unpack .../40-libalgorithm-diff-xs-perl_0.04-5_amd64.deb ...
    k8s: Unpacking libalgorithm-diff-xs-perl (0.04-5) ...
    k8s: Selecting previously unselected package libalgorithm-merge-perl.
    k8s: Preparing to unpack .../41-libalgorithm-merge-perl_0.08-3_all.deb ...
    k8s: Unpacking libalgorithm-merge-perl (0.08-3) ...
    k8s: Selecting previously unselected package libfile-fcntllock-perl.
    k8s: Preparing to unpack .../42-libfile-fcntllock-perl_0.22-3build2_amd64.deb ...
    k8s: Unpacking libfile-fcntllock-perl (0.22-3build2) ...
    k8s: Selecting previously unselected package tig.
    k8s: Preparing to unpack .../43-tig_2.3.0-1_amd64.deb ...
    k8s: Unpacking tig (2.3.0-1) ...
    k8s: Selecting previously unselected package socat.
    k8s: Preparing to unpack .../44-socat_1.7.3.2-2ubuntu2_amd64.deb ...
    k8s: Unpacking socat (1.7.3.2-2ubuntu2) ...
    k8s: Setting up libquadmath0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libgomp1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libatomic1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libcc1-0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libarchive13:amd64 (3.2.2-3.1ubuntu0.6) ...
    k8s: Setting up socat (1.7.3.2-2ubuntu2) ...
    k8s: Setting up bash-completion (1:2.8-1ubuntu1) ...
    k8s: Setting up libtsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libonig4:amd64 (6.7.0-1) ...
    k8s: Setting up libdpkg-perl (1.19.0.5ubuntu2.3) ...
    k8s: Setting up cmake-data (3.10.2-1ubuntu2.18.04.1) ...
    k8s: Setting up tcpdump (4.9.3-0ubuntu0.18.04.1) ...
    k8s: Setting up librhash0:amd64 (1.3.6-2) ...
    k8s: Setting up liblsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up gcc-7-base:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up libfile-fcntllock-perl (0.22-3build2) ...
    k8s: Setting up libjq1:amd64 (1.5+dfsg-2) ...
    k8s: Setting up libmpx2:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up dpkg-dev (1.19.0.5ubuntu2.3) ...
    k8s: Setting up libfakeroot:amd64 (1.22-2ubuntu1) ...
    k8s: Setting up vim-common (2:8.0.1453-1ubuntu1.3) ...
    k8s: Setting up libalgorithm-diff-perl (1.19.03-1) ...
    k8s: Setting up vim-runtime (2:8.0.1453-1ubuntu1.3) ...
    k8s: Setting up git (1:2.17.1-1ubuntu0.7) ...
    k8s: Setting up libitm1:amd64 (8.4.0-1ubuntu1~18.04) ...
    k8s: Setting up libjsoncpp1:amd64 (1.7.4-3) ...
    k8s: Setting up vim-tiny (2:8.0.1453-1ubuntu1.3) ...
    k8s: Setting up jq (1.5+dfsg-2) ...
    k8s: Setting up libasan4:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up vim (2:8.0.1453-1ubuntu1.3) ...
    k8s: Setting up libcilkrts5:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up libubsan0:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up tig (2.3.0-1) ...
    k8s: Setting up fakeroot (1.22-2ubuntu1) ...
    k8s: update-alternatives: using /usr/bin/fakeroot-sysv to provide /usr/bin/fakeroot (fakeroot) in auto mode
    k8s: Setting up libgcc-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up cpp-7 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up libstdc++-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up libalgorithm-merge-perl (0.08-3) ...
    k8s: Setting up libalgorithm-diff-xs-perl (0.04-5) ...
    k8s: Setting up cmake (3.10.2-1ubuntu2.18.04.1) ...
    k8s: Setting up gcc-7 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up g++-7 (7.5.0-3ubuntu1~18.04) ...
    k8s: Setting up gcc (4:7.4.0-1ubuntu2.3) ...
    k8s: Setting up g++ (4:7.4.0-1ubuntu2.3) ...
    k8s: update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
    k8s: Setting up build-essential (12.4ubuntu1) ...
    k8s: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    k8s: Processing triggers for mime-support (3.60ubuntu1) ...
    k8s: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    k8s: ++ export DOCKER_VERSION=5:19.03.5~3-0~ubuntu-bionic
    k8s: ++ DOCKER_VERSION=5:19.03.5~3-0~ubuntu-bionic
    k8s: ++ curl -fsSL https://download.docker.com/linux/ubuntu/gpg
    k8s: ++ sudo apt-key add -
    k8s: Warning: apt-key output should not be parsed (stdout is not a terminal)
    k8s: OK
    k8s: +++ lsb_release -cs
    k8s: ++ sudo add-apt-repository 'deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable'
    k8s: Get:1 https://download.docker.com/linux/ubuntu bionic InRelease [64.4 kB]
    k8s: Get:2 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages [11.0 kB]
    k8s: Hit:3 http://security.ubuntu.com/ubuntu bionic-security InRelease
    k8s: Hit:4 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Hit:5 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    k8s: Hit:6 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    k8s: Fetched 75.5 kB in 1s (55.8 kB/s)
    k8s: Reading package lists...
    k8s: ++ sudo apt-get update
    k8s: Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
    k8s: Hit:2 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Hit:3 http://security.ubuntu.com/ubuntu bionic-security InRelease
    k8s: Hit:4 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    k8s: Hit:5 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    k8s: Reading package lists...
    k8s: ++ sudo apt-get install -y docker-ce=5:19.03.5~3-0~ubuntu-bionic
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: Reading state information...
    k8s: The following additional packages will be installed:
    k8s:   aufs-tools cgroupfs-mount containerd.io docker-ce-cli libltdl7 pigz
    k8s: The following NEW packages will be installed:
    k8s:   aufs-tools cgroupfs-mount containerd.io docker-ce docker-ce-cli libltdl7
    k8s:   pigz
    k8s: 0 upgraded, 7 newly installed, 0 to remove and 91 not upgraded.
    k8s: Need to get 85.7 MB of archives.
    k8s: After this operation, 385 MB of additional disk space will be used.
    k8s: Get:1 https://download.docker.com/linux/ubuntu bionic/stable amd64 containerd.io amd64 1.2.13-1 [20.1 MB]
    k8s: Get:2 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce-cli amd64 5:19.03.8~3-0~ubuntu-bionic [42.6 MB]
    k8s: Get:3 http://archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
    k8s: Get:4 http://archive.ubuntu.com/ubuntu bionic/universe amd64 aufs-tools amd64 1:4.9+20170918-1ubuntu1 [104 kB]
    k8s: Get:5 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce amd64 5:19.03.5~3-0~ubuntu-bionic [22.8 MB]
    k8s: Get:6 http://archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6,320 B]
    k8s: Get:7 http://archive.ubuntu.com/ubuntu bionic/main amd64 libltdl7 amd64 2.4.6-2 [38.8 kB]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 85.7 MB in 2s (46.7 MB/s)
    k8s: Selecting previously unselected package pigz.
    k8s: (Reading database ... 
    k8s: (Reading database ... 5%
    k8s: (Reading database ... 10%
    k8s: (Reading database ... 15%
    k8s: (Reading database ... 20%
    k8s: (Reading database ... 25%
    k8s: (Reading database ... 30%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
    k8s: (Reading database ... 100%
    k8s: (Reading database ... 
    k8s: 47368 files and directories currently installed.)
    k8s: Preparing to unpack .../0-pigz_2.4-1_amd64.deb ...
    k8s: Unpacking pigz (2.4-1) ...
    k8s: Selecting previously unselected package aufs-tools.
    k8s: Preparing to unpack .../1-aufs-tools_1%3a4.9+20170918-1ubuntu1_amd64.deb ...
    k8s: Unpacking aufs-tools (1:4.9+20170918-1ubuntu1) ...
    k8s: Selecting previously unselected package cgroupfs-mount.
    k8s: Preparing to unpack .../2-cgroupfs-mount_1.4_all.deb ...
    k8s: Unpacking cgroupfs-mount (1.4) ...
    k8s: Selecting previously unselected package containerd.io.
    k8s: Preparing to unpack .../3-containerd.io_1.2.13-1_amd64.deb ...
    k8s: Unpacking containerd.io (1.2.13-1) ...
    k8s: Selecting previously unselected package docker-ce-cli.
    k8s: Preparing to unpack .../4-docker-ce-cli_5%3a19.03.8~3-0~ubuntu-bionic_amd64.deb ...
    k8s: Unpacking docker-ce-cli (5:19.03.8~3-0~ubuntu-bionic) ...
    k8s: Selecting previously unselected package docker-ce.
    k8s: Preparing to unpack .../5-docker-ce_5%3a19.03.5~3-0~ubuntu-bionic_amd64.deb ...
    k8s: Unpacking docker-ce (5:19.03.5~3-0~ubuntu-bionic) ...
    k8s: Selecting previously unselected package libltdl7:amd64.
    k8s: Preparing to unpack .../6-libltdl7_2.4.6-2_amd64.deb ...
    k8s: Unpacking libltdl7:amd64 (2.4.6-2) ...
    k8s: Setting up aufs-tools (1:4.9+20170918-1ubuntu1) ...
    k8s: Setting up containerd.io (1.2.13-1) ...
    k8s: Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
    k8s: Setting up cgroupfs-mount (1.4) ...
    k8s: Setting up libltdl7:amd64 (2.4.6-2) ...
    k8s: Setting up docker-ce-cli (5:19.03.8~3-0~ubuntu-bionic) ...
    k8s: Setting up pigz (2.4-1) ...
    k8s: Setting up docker-ce (5:19.03.5~3-0~ubuntu-bionic) ...
    k8s: Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
    k8s: Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
    k8s: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    k8s: Processing triggers for systemd (237-3ubuntu10.33) ...
    k8s: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    k8s: Processing triggers for ureadahead (0.100.0-21) ...
    k8s: ++ sudo usermod -aG docker vagrant
    k8s: ++ sudo swapoff -a
    k8s: ++ sudo sysctl -w vm.swappiness=0
    k8s: vm.swappiness = 0
    k8s: ++ sudo sed /vagrant--vg-swap/d -i /etc/fstab
    k8s: ++ git clone https://github.com/xxx
    k8s: Cloning into 'xxx'...
    k8s: ++ sudo apt-get update
    k8s: Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
    k8s: Hit:2 http://security.ubuntu.com/ubuntu bionic-security InRelease
    k8s: Hit:3 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Hit:4 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    k8s: Hit:5 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    k8s: Reading package lists...
    k8s: ++ sudo apt-get install -y apt-transport-https curl
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: Reading state information...
    k8s: curl is already the newest version (7.58.0-2ubuntu3.8).
    k8s: The following NEW packages will be installed:
    k8s:   apt-transport-https
    k8s: 0 upgraded, 1 newly installed, 0 to remove and 92 not upgraded.
    k8s: Need to get 1,692 B of archives.
    k8s: After this operation, 153 kB of additional disk space will be used.
    k8s: Get:1 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 apt-transport-https all 1.6.12 [1,692 B]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 1,692 B in 0s (3,538 B/s)
    k8s: Selecting previously unselected package apt-transport-https.
    k8s: (Reading database ... 
    k8s: (Reading database ... 5%
    k8s: (Reading database ... 10%
    k8s: (Reading database ... 15%
    k8s: (Reading database ... 20%
    k8s: (Reading database ... 25%
    k8s: (Reading database ... 30%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
    k8s: (Reading database ... 100%
    k8s: (Reading database ... 
    k8s: 47678 files and directories currently installed.)
    k8s: Preparing to unpack .../apt-transport-https_1.6.12_all.deb ...
    k8s: Unpacking apt-transport-https (1.6.12) ...
    k8s: Setting up apt-transport-https (1.6.12) ...
    k8s: ++ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg
    k8s: ++ sudo apt-key add -
    k8s: Warning: apt-key output should not be parsed (stdout is not a terminal)
    k8s: OK
    k8s: ++ sudo tee --append /etc/apt/sources.list.d/kubernetes.list
    k8s: ++ echo 'deb http://apt.kubernetes.io/ kubernetes-xenial main'
    k8s: deb http://apt.kubernetes.io/ kubernetes-xenial main
    k8s: ++ sudo apt-get update
    k8s: Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
    k8s: Hit:2 http://security.ubuntu.com/ubuntu bionic-security InRelease
    k8s: Hit:3 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Hit:5 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    k8s: Hit:6 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    k8s: Get:4 https://packages.cloud.google.com/apt kubernetes-xenial InRelease [8,993 B]
    k8s: Get:7 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 Packages [35.3 kB]
    k8s: Fetched 44.3 kB in 1s (31.4 kB/s)
    k8s: Reading package lists...
    k8s: ++ sudo apt-get install -y kubectl
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: Reading state information...
    k8s: The following NEW packages will be installed:
    k8s:   kubectl
    k8s: 0 upgraded, 1 newly installed, 0 to remove and 92 not upgraded.
    k8s: Need to get 8,825 kB of archives.
    k8s: After this operation, 44.0 MB of additional disk space will be used.
    k8s: Get:1 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubectl amd64 1.18.2-00 [8,825 kB]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 8,825 kB in 1s (7,450 kB/s)
    k8s: Selecting previously unselected package kubectl.
    k8s: (Reading database ... 
    k8s: (Reading database ... 5%
    k8s: (Reading database ... 10%
    k8s: (Reading database ... 15%
    k8s: (Reading database ... 20%
    k8s: (Reading database ... 25%
    k8s: (Reading database ... 30%
    k8s: (Reading database ... 35%
    k8s: (Reading database ... 40%
    k8s: (Reading database ... 45%
    k8s: (Reading database ... 50%
    k8s: (Reading database ... 55%
    k8s: (Reading database ... 60%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
    k8s: (Reading database ... 100%
    k8s: (Reading database ... 
    k8s: 47682 files and directories currently installed.)
    k8s: Preparing to unpack .../kubectl_1.18.2-00_amd64.deb ...
    k8s: Unpacking kubectl (1.18.2-00) ...
    k8s: Setting up kubectl (1.18.2-00) ...
    k8s: +++ uname
    k8s: ++ curl -Lo ./kind https://github.com/kubernetes-sigs/kind/releases/download/v0.7.0/kind-Linux-amd64
    k8s:  
    k8s:  
    k8s: %
    k8s:  
    k8s: T
    k8s: o
    k8s: t
    k8s: a
    k8s: l
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: %
    k8s:  
    k8s: R
    k8s: e
    k8s: c
    k8s: e
    k8s: i
    k8s: v
    k8s: e
    k8s: d
    k8s:  
    k8s: %
    k8s:  
    k8s: X
    k8s: f
    k8s: e
    k8s: r
    k8s: d
    k8s:  
    k8s:  
    k8s: A
    k8s: v
    k8s: e
    k8s: r
    k8s: a
    k8s: g
    k8s: e
    k8s:  
    k8s: S
    k8s: p
    k8s: e
    k8s: e
    k8s: d
    k8s:  
    k8s:  
    k8s:  
    k8s: T
    k8s: i
    k8s: m
    k8s: e
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: T
    k8s: i
    k8s: m
    k8s: e
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: T
    k8s: i
    k8s: m
    k8s: e
    k8s:   Current
    k8s:                                  Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
    k8s: 1
    k8s: 0
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s: 6
    k8s: 2
    k8s: 9
    k8s:  
    k8s:  
    k8s: 1
    k8s: 0
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s: 6
    k8s: 2
    k8s: 9
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s: 1
    k8s: 5
    k8s: 5
    k8s: 3
    k8s:  
    k8s:      0 --:--:-- --:--:-- --:--:--  1553
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s:  
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s:  
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s: :
    k8s: -
    k8s: -
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  0
    k8s:  
    k8s:  
    k8s: 1
    k8s:  
    k8s: 9
    k8s: 1
    k8s: 3
    k8s: 6
    k8s: k
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 1
    k8s:  
    k8s:  
    k8s: 1
    k8s: 1
    k8s: 8
    k8s: k
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s: 6
    k8s: 8
    k8s: 2
    k8s: 1
    k8s: 4
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s:  
    k8s: 0
    k8s:  
    k8s:  
    k8s: 0
    k8s: :
    k8s: 0
    k8s: 2:17  0:00:01  0:02:16  120k
 32 9136k   32 2933k    0     0  1031k      0  0:00:08  0:00:02  0:00:06 1432k
100 9136k  100 9136k    0     0  2559k      0
    k8s:   0:00:03  0:00:03 --:--:-- 3293k
    k8s: ++ chmod a+x ./kind
    k8s: ++ sudo mv ./kind /usr/local/bin/kind
    k8s: ++ sudo kind create cluster --config hxxx/vagrant/kind.yaml
    k8s: Creating cluster "kind" ...
    k8s:  • Ensuring node image (kindest/node:v1.17.0) 🖼  ...
    k8s:  ✓ Ensuring node image (kindest/node:v1.17.0) 🖼
    k8s:  • Preparing nodes 📦 📦 📦   ...
    k8s:  ✓ Preparing nodes 📦 📦 📦 
    k8s:  • Writing configuration 📜  ...
    k8s:  ✓ Writing configuration 📜
    k8s:  • Starting control-plane 🕹️  ...
    k8s:  ✓ Starting control-plane 🕹️
    k8s:  • Installing CNI 🔌  ...
    k8s:  ✓ Installing CNI 🔌
    k8s:  • Installing StorageClass 💾  ...
    k8s:  ✓ Installing StorageClass 💾
    k8s:  • Joining worker nodes 🚜  ...
    k8s:  ✓ Joining worker nodes 🚜
    k8s: Set kubectl context to "kind-kind"
    k8s: You can now use your cluster with:
    k8s: 
    k8s: kubectl cluster-info --context kind-kind
    k8s: 
    k8s: Have a nice day! 👋
    k8s: +++ id -u
    k8s: +++ id -g
    k8s: ++ sudo chown 1000:1000 /home/vagrant/.kube/config
    k8s: ++ echo 'source <(kubectl completion bash)'
    k8s: ++ set -x
    k8s: +++ mktemp -d
    k8s: ++ cd /tmp/tmp.K1rGoLjm5p
    k8s: ++ curl -fsSLO 'https://github.com/kubernetes-sigs/krew/releases/latest/download/krew.{tar.gz,yaml}'
    k8s: ++ tar zxvf krew.tar.gz
    k8s: ./LICENSE
    k8s: ./krew-darwin_amd64
    k8s: ./krew-linux_amd64
    k8s: ./krew-linux_arm
    k8s: ./krew-windows_amd64.exe
    k8s: +++ uname
    k8s: +++ tr '[:upper:]' '[:lower:]'
    k8s: ++ KREW=./krew-linux_amd64
    k8s: ++ ./krew-linux_amd64 install --manifest=krew.yaml --archive=krew.tar.gz
    k8s: WARNING: Detected stdin, but discarding it because of --manifest or args
    k8s: Installing plugin: krew
    k8s: Installed plugin: krew
    k8s: \
    k8s:  | Use this plugin:
    k8s:  |     kubectl krew
    k8s:  | Documentation:
    k8s:  |     https://sigs.k8s.io/krew
    k8s:  | Caveats:
    k8s:  | \
    k8s:  |  | krew is now installed! To start using kubectl plugins, you need to add
    k8s:  |  | krew's installation directory to your PATH:
    k8s:  |  | 
    k8s:  |  |   * macOS/Linux:
    k8s:  |  |     - Add the following to your ~/.bashrc or ~/.zshrc:
    k8s:  |  |         export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"
    k8s:  |  |     - Restart your shell.
    k8s:  |  | 
    k8s:  |  |   * Windows: Add %USERPROFILE%\.krew\bin to your PATH environment variable
    k8s:  |  | 
    k8s:  |  | To list krew commands and to get help, run:
    k8s:  |  |   $ kubectl krew
    k8s:  |  | For a full list of available plugins, run:
    k8s:  |  |   $ kubectl krew search
    k8s:  |  | 
    k8s:  |  | You can find documentation at https://sigs.k8s.io/krew.
    k8s:  | /
    k8s: /
    k8s: ++ ./krew-linux_amd64 update
    k8s: WARNING: To be able to run kubectl plugins, you need to add
    k8s: the following to your ~/.bash_profile or ~/.bashrc:
    k8s: 
    k8s:     export PATH="${PATH}:${HOME}/.krew/bin"
    k8s: 
    k8s: and restart your shell.
    k8s: Updated the local copy of plugin index.
    k8s: ++ echo 'export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"'
```

```console
$ vagrant ssh
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-72-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat May  2 07:47:38 UTC 2020

  System load:  1.09               Users logged in:        0
  Usage of /:   11.0% of 61.80GB   IP address for eth0:    10.0.2.15
  Memory usage: 25%                IP address for eth1:    172.17.8.111
  Swap usage:   0%                 IP address for docker0: 172.18.0.1
  Processes:    165

 * Ubuntu 20.04 LTS is out, raising the bar on performance, security,
   and optimisation for Intel, AMD, Nvidia, ARM64 and Z15 as well as
   AWS, Azure and Google Cloud.

     https://ubuntu.com/blog/ubuntu-20-04-lts-arrives


95 packages can be updated.
61 updates are security updates.



This system is built by the Bento project by Chef Software
More information can be found at https://github.com/chef/bento
vagrant@k8s-dev:~$ 
```

```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo make build-image
docker build --build-arg HASH=8376ed1 --build-arg LOG="add prodiction for kustomize" --tag ken/cicd-app:8376ed1 .
Sending build context to Docker daemon  32.26kB
Step 1/8 : FROM ubuntu:16.04
16.04: Pulling from library/ubuntu
e92ed755c008: Pull complete 
b9fd7cb1ff8f: Pull complete 
ee690f2d57a1: Pull complete 
53e3366ec435: Pull complete 
Digest: sha256:db6697a61d5679b7ca69dbde3dad6be0d17064d5b6b0e9f7be8d456ebb337209
Status: Downloaded newer image for ubuntu:16.04
 ---> 005d2078bdfa
Step 2/8 : RUN apt-get update &&         apt-get install -y nginx
 ---> Running in 9c1c0c3a7688
Get:1 http://security.ubuntu.com/ubuntu xenial-security InRelease [109 kB]
Get:2 http://archive.ubuntu.com/ubuntu xenial InRelease [247 kB]
Get:3 http://security.ubuntu.com/ubuntu xenial-security/main amd64 Packages [1101 kB]
Get:4 http://archive.ubuntu.com/ubuntu xenial-updates InRelease [109 kB]
Get:5 http://security.ubuntu.com/ubuntu xenial-security/restricted amd64 Packages [12.7 kB]
Get:6 http://security.ubuntu.com/ubuntu xenial-security/universe amd64 Packages [624 kB]
Get:7 http://security.ubuntu.com/ubuntu xenial-security/multiverse amd64 Packages [6680 B]
Get:8 http://archive.ubuntu.com/ubuntu xenial-backports InRelease [107 kB]
Get:9 http://archive.ubuntu.com/ubuntu xenial/main amd64 Packages [1558 kB]
Get:10 http://archive.ubuntu.com/ubuntu xenial/restricted amd64 Packages [14.1 kB]
Get:11 http://archive.ubuntu.com/ubuntu xenial/universe amd64 Packages [9827 kB]
Get:12 http://archive.ubuntu.com/ubuntu xenial/multiverse amd64 Packages [176 kB]
Get:13 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 Packages [1470 kB]
Get:14 http://archive.ubuntu.com/ubuntu xenial-updates/restricted amd64 Packages [13.1 kB]
Get:15 http://archive.ubuntu.com/ubuntu xenial-updates/universe amd64 Packages [1029 kB]
Get:16 http://archive.ubuntu.com/ubuntu xenial-updates/multiverse amd64 Packages [19.7 kB]
Get:17 http://archive.ubuntu.com/ubuntu xenial-backports/main amd64 Packages [7942 B]
Get:18 http://archive.ubuntu.com/ubuntu xenial-backports/universe amd64 Packages [8807 B]
Fetched 16.4 MB in 6s (2726 kB/s)
Reading package lists...
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
  fontconfig-config fonts-dejavu-core geoip-database libexpat1 libfontconfig1
  libfreetype6 libgd3 libgeoip1 libicu55 libjbig0 libjpeg-turbo8 libjpeg8
  libpng12-0 libssl1.0.0 libtiff5 libvpx3 libx11-6 libx11-data libxau6 libxcb1
  libxdmcp6 libxml2 libxpm4 libxslt1.1 nginx-common nginx-core sgml-base ucf
  xml-core
Suggested packages:
  libgd-tools geoip-bin fcgiwrap nginx-doc ssl-cert sgml-base-doc debhelper
The following NEW packages will be installed:
  fontconfig-config fonts-dejavu-core geoip-database libexpat1 libfontconfig1
  libfreetype6 libgd3 libgeoip1 libicu55 libjbig0 libjpeg-turbo8 libjpeg8
  libpng12-0 libssl1.0.0 libtiff5 libvpx3 libx11-6 libx11-data libxau6 libxcb1
  libxdmcp6 libxml2 libxpm4 libxslt1.1 nginx nginx-common nginx-core sgml-base
  ucf xml-core
0 upgraded, 30 newly installed, 0 to remove and 0 not upgraded.
Need to get 15.5 MB of archives.
After this operation, 57.4 MB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu xenial/main amd64 libxau6 amd64 1:1.0.8-1 [8376 B]
Get:2 http://archive.ubuntu.com/ubuntu xenial/main amd64 sgml-base all 1.26+nmu4ubuntu1 [12.5 kB]
Get:3 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libjpeg-turbo8 amd64 1.4.2-0ubuntu3.3 [111 kB]
Get:4 http://archive.ubuntu.com/ubuntu xenial/main amd64 libjbig0 amd64 2.1-3.1 [26.6 kB]
Get:5 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libexpat1 amd64 2.1.0-7ubuntu0.16.04.5 [71.5 kB]
Get:6 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libpng12-0 amd64 1.2.54-1ubuntu1.1 [116 kB]
Get:7 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libssl1.0.0 amd64 1.0.2g-1ubuntu4.15 [1084 kB]
Get:8 http://archive.ubuntu.com/ubuntu xenial/main amd64 ucf all 3.0036 [52.9 kB]
Get:9 http://archive.ubuntu.com/ubuntu xenial/main amd64 geoip-database all 20160408-1 [1678 kB]
Get:10 http://archive.ubuntu.com/ubuntu xenial/main amd64 libgeoip1 amd64 1.6.9-1 [70.1 kB]
Get:11 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libicu55 amd64 55.1-7ubuntu0.5 [7650 kB]
Get:12 http://archive.ubuntu.com/ubuntu xenial/main amd64 libxdmcp6 amd64 1:1.1.2-1.1 [11.0 kB]
Get:13 http://archive.ubuntu.com/ubuntu xenial/main amd64 libxcb1 amd64 1.11.1-1ubuntu1 [40.0 kB]
Get:14 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libx11-data all 2:1.6.3-1ubuntu2.1 [113 kB]
Get:15 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libx11-6 amd64 2:1.6.3-1ubuntu2.1 [570 kB]
Get:16 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libxml2 amd64 2.9.3+dfsg1-1ubuntu0.7 [698 kB]
Get:17 http://archive.ubuntu.com/ubuntu xenial/main amd64 xml-core all 0.13+nmu2 [23.3 kB]
Get:18 http://archive.ubuntu.com/ubuntu xenial/main amd64 fonts-dejavu-core all 2.35-1 [1039 kB]
Get:19 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 fontconfig-config all 2.11.94-0ubuntu1.1 [49.9 kB]
Get:20 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libfreetype6 amd64 2.6.1-0.1ubuntu2.4 [315 kB]
Get:21 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libfontconfig1 amd64 2.11.94-0ubuntu1.1 [131 kB]
Get:22 http://archive.ubuntu.com/ubuntu xenial/main amd64 libjpeg8 amd64 8c-2ubuntu8 [2194 B]
Get:23 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libtiff5 amd64 4.0.6-1ubuntu0.7 [149 kB]
Get:24 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libvpx3 amd64 1.5.0-2ubuntu1.1 [732 kB]
Get:25 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libxpm4 amd64 1:3.5.11-1ubuntu0.16.04.1 [33.8 kB]
Get:26 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libgd3 amd64 2.1.1-4ubuntu0.16.04.12 [126 kB]
Get:27 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libxslt1.1 amd64 1.1.28-2.1ubuntu0.3 [146 kB]
Get:28 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 nginx-common all 1.10.3-0ubuntu0.16.04.5 [26.9 kB]
Get:29 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 nginx-core amd64 1.10.3-0ubuntu0.16.04.5 [429 kB]
Get:30 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 nginx all 1.10.3-0ubuntu0.16.04.5 [3494 B]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 15.5 MB in 5s (3091 kB/s)
Selecting previously unselected package libxau6:amd64.
(Reading database ... 4781 files and directories currently installed.)
Preparing to unpack .../libxau6_1%3a1.0.8-1_amd64.deb ...
Unpacking libxau6:amd64 (1:1.0.8-1) ...
Selecting previously unselected package sgml-base.
Preparing to unpack .../sgml-base_1.26+nmu4ubuntu1_all.deb ...
Unpacking sgml-base (1.26+nmu4ubuntu1) ...
Selecting previously unselected package libjpeg-turbo8:amd64.
Preparing to unpack .../libjpeg-turbo8_1.4.2-0ubuntu3.3_amd64.deb ...
Unpacking libjpeg-turbo8:amd64 (1.4.2-0ubuntu3.3) ...
Selecting previously unselected package libjbig0:amd64.
Preparing to unpack .../libjbig0_2.1-3.1_amd64.deb ...
Unpacking libjbig0:amd64 (2.1-3.1) ...
Selecting previously unselected package libexpat1:amd64.
Preparing to unpack .../libexpat1_2.1.0-7ubuntu0.16.04.5_amd64.deb ...
Unpacking libexpat1:amd64 (2.1.0-7ubuntu0.16.04.5) ...
Selecting previously unselected package libpng12-0:amd64.
Preparing to unpack .../libpng12-0_1.2.54-1ubuntu1.1_amd64.deb ...
Unpacking libpng12-0:amd64 (1.2.54-1ubuntu1.1) ...
Selecting previously unselected package libssl1.0.0:amd64.
Preparing to unpack .../libssl1.0.0_1.0.2g-1ubuntu4.15_amd64.deb ...
Unpacking libssl1.0.0:amd64 (1.0.2g-1ubuntu4.15) ...
Selecting previously unselected package ucf.
Preparing to unpack .../archives/ucf_3.0036_all.deb ...
Moving old data out of the way
Unpacking ucf (3.0036) ...
Selecting previously unselected package geoip-database.
Preparing to unpack .../geoip-database_20160408-1_all.deb ...
Unpacking geoip-database (20160408-1) ...
Selecting previously unselected package libgeoip1:amd64.
Preparing to unpack .../libgeoip1_1.6.9-1_amd64.deb ...
Unpacking libgeoip1:amd64 (1.6.9-1) ...
Selecting previously unselected package libicu55:amd64.
Preparing to unpack .../libicu55_55.1-7ubuntu0.5_amd64.deb ...
Unpacking libicu55:amd64 (55.1-7ubuntu0.5) ...
Selecting previously unselected package libxdmcp6:amd64.
Preparing to unpack .../libxdmcp6_1%3a1.1.2-1.1_amd64.deb ...
Unpacking libxdmcp6:amd64 (1:1.1.2-1.1) ...
Selecting previously unselected package libxcb1:amd64.
Preparing to unpack .../libxcb1_1.11.1-1ubuntu1_amd64.deb ...
Unpacking libxcb1:amd64 (1.11.1-1ubuntu1) ...
Selecting previously unselected package libx11-data.
Preparing to unpack .../libx11-data_2%3a1.6.3-1ubuntu2.1_all.deb ...
Unpacking libx11-data (2:1.6.3-1ubuntu2.1) ...
Selecting previously unselected package libx11-6:amd64.
Preparing to unpack .../libx11-6_2%3a1.6.3-1ubuntu2.1_amd64.deb ...
Unpacking libx11-6:amd64 (2:1.6.3-1ubuntu2.1) ...
Selecting previously unselected package libxml2:amd64.
Preparing to unpack .../libxml2_2.9.3+dfsg1-1ubuntu0.7_amd64.deb ...
Unpacking libxml2:amd64 (2.9.3+dfsg1-1ubuntu0.7) ...
Selecting previously unselected package xml-core.
Preparing to unpack .../xml-core_0.13+nmu2_all.deb ...
Unpacking xml-core (0.13+nmu2) ...
Selecting previously unselected package fonts-dejavu-core.
Preparing to unpack .../fonts-dejavu-core_2.35-1_all.deb ...
Unpacking fonts-dejavu-core (2.35-1) ...
Selecting previously unselected package fontconfig-config.
Preparing to unpack .../fontconfig-config_2.11.94-0ubuntu1.1_all.deb ...
Unpacking fontconfig-config (2.11.94-0ubuntu1.1) ...
Selecting previously unselected package libfreetype6:amd64.
Preparing to unpack .../libfreetype6_2.6.1-0.1ubuntu2.4_amd64.deb ...
Unpacking libfreetype6:amd64 (2.6.1-0.1ubuntu2.4) ...
Selecting previously unselected package libfontconfig1:amd64.
Preparing to unpack .../libfontconfig1_2.11.94-0ubuntu1.1_amd64.deb ...
Unpacking libfontconfig1:amd64 (2.11.94-0ubuntu1.1) ...
Selecting previously unselected package libjpeg8:amd64.
Preparing to unpack .../libjpeg8_8c-2ubuntu8_amd64.deb ...
Unpacking libjpeg8:amd64 (8c-2ubuntu8) ...
Selecting previously unselected package libtiff5:amd64.
Preparing to unpack .../libtiff5_4.0.6-1ubuntu0.7_amd64.deb ...
Unpacking libtiff5:amd64 (4.0.6-1ubuntu0.7) ...
Selecting previously unselected package libvpx3:amd64.
Preparing to unpack .../libvpx3_1.5.0-2ubuntu1.1_amd64.deb ...
Unpacking libvpx3:amd64 (1.5.0-2ubuntu1.1) ...
Selecting previously unselected package libxpm4:amd64.
Preparing to unpack .../libxpm4_1%3a3.5.11-1ubuntu0.16.04.1_amd64.deb ...
Unpacking libxpm4:amd64 (1:3.5.11-1ubuntu0.16.04.1) ...
Selecting previously unselected package libgd3:amd64.
Preparing to unpack .../libgd3_2.1.1-4ubuntu0.16.04.12_amd64.deb ...
Unpacking libgd3:amd64 (2.1.1-4ubuntu0.16.04.12) ...
Selecting previously unselected package libxslt1.1:amd64.
Preparing to unpack .../libxslt1.1_1.1.28-2.1ubuntu0.3_amd64.deb ...
Unpacking libxslt1.1:amd64 (1.1.28-2.1ubuntu0.3) ...
Selecting previously unselected package nginx-common.
Preparing to unpack .../nginx-common_1.10.3-0ubuntu0.16.04.5_all.deb ...
Unpacking nginx-common (1.10.3-0ubuntu0.16.04.5) ...
Selecting previously unselected package nginx-core.
Preparing to unpack .../nginx-core_1.10.3-0ubuntu0.16.04.5_amd64.deb ...
Unpacking nginx-core (1.10.3-0ubuntu0.16.04.5) ...
Selecting previously unselected package nginx.
Preparing to unpack .../nginx_1.10.3-0ubuntu0.16.04.5_all.deb ...
Unpacking nginx (1.10.3-0ubuntu0.16.04.5) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for systemd (229-4ubuntu21.27) ...
Setting up libxau6:amd64 (1:1.0.8-1) ...
Setting up sgml-base (1.26+nmu4ubuntu1) ...
Setting up libjpeg-turbo8:amd64 (1.4.2-0ubuntu3.3) ...
Setting up libjbig0:amd64 (2.1-3.1) ...
Setting up libexpat1:amd64 (2.1.0-7ubuntu0.16.04.5) ...
Setting up libpng12-0:amd64 (1.2.54-1ubuntu1.1) ...
Setting up libssl1.0.0:amd64 (1.0.2g-1ubuntu4.15) ...
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.22.1 /usr/local/share/perl/5.22.1 /usr/lib/x86_64-linux-gnu/perl5/5.22 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.22 /usr/share/perl/5.22 /usr/local/lib/site_perl /usr/lib/x86_64-linux-gnu/perl-base .) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up ucf (3.0036) ...
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.22.1 /usr/local/share/perl/5.22.1 /usr/lib/x86_64-linux-gnu/perl5/5.22 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.22 /usr/share/perl/5.22 /usr/local/lib/site_perl /usr/lib/x86_64-linux-gnu/perl-base .) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up geoip-database (20160408-1) ...
Setting up libgeoip1:amd64 (1.6.9-1) ...
Setting up libicu55:amd64 (55.1-7ubuntu0.5) ...
Setting up libxdmcp6:amd64 (1:1.1.2-1.1) ...
Setting up libxcb1:amd64 (1.11.1-1ubuntu1) ...
Setting up libx11-data (2:1.6.3-1ubuntu2.1) ...
Setting up libx11-6:amd64 (2:1.6.3-1ubuntu2.1) ...
Setting up libxml2:amd64 (2.9.3+dfsg1-1ubuntu0.7) ...
Setting up xml-core (0.13+nmu2) ...
Setting up fonts-dejavu-core (2.35-1) ...
Setting up fontconfig-config (2.11.94-0ubuntu1.1) ...
Setting up libfreetype6:amd64 (2.6.1-0.1ubuntu2.4) ...
Setting up libfontconfig1:amd64 (2.11.94-0ubuntu1.1) ...
Setting up libjpeg8:amd64 (8c-2ubuntu8) ...
Setting up libtiff5:amd64 (4.0.6-1ubuntu0.7) ...
Setting up libvpx3:amd64 (1.5.0-2ubuntu1.1) ...
Setting up libxpm4:amd64 (1:3.5.11-1ubuntu0.16.04.1) ...
Setting up libgd3:amd64 (2.1.1-4ubuntu0.16.04.12) ...
Setting up libxslt1.1:amd64 (1.1.28-2.1ubuntu0.3) ...
Setting up nginx-common (1.10.3-0ubuntu0.16.04.5) ...
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.22.1 /usr/local/share/perl/5.22.1 /usr/lib/x86_64-linux-gnu/perl5/5.22 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.22 /usr/share/perl/5.22 /usr/local/lib/site_perl /usr/lib/x86_64-linux-gnu/perl-base .) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up nginx-core (1.10.3-0ubuntu0.16.04.5) ...
invoke-rc.d: could not determine current runlevel
invoke-rc.d: policy-rc.d denied execution of start.
Setting up nginx (1.10.3-0ubuntu0.16.04.5) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for sgml-base (1.26+nmu4ubuntu1) ...
Processing triggers for systemd (229-4ubuntu21.27) ...
Removing intermediate container 9c1c0c3a7688
 ---> f22b4f7bf048
Step 3/8 : ARG HASH
 ---> Running in a6aac26b90c0
Removing intermediate container a6aac26b90c0
 ---> 98841a2c1e0c
Step 4/8 : ARG LOG
 ---> Running in fc646d11bce0
Removing intermediate container fc646d11bce0
 ---> 01fcebf02406
Step 5/8 : ENV COMMITHASH=$HASH
 ---> Running in 011dddcf3d3f
Removing intermediate container 011dddcf3d3f
 ---> 340a74ad605c
Step 6/8 : ENV COMMITLOG=$LOG
 ---> Running in 7eced6444b68
Removing intermediate container 7eced6444b68
 ---> c993b860fc49
Step 7/8 : COPY entrypoint.sh ./
 ---> 70d8e5a1e6df
Step 8/8 : ENTRYPOINT ["/bin/bash", "./entrypoint.sh"]
 ---> Running in d508c7f5a293
Removing intermediate container d508c7f5a293
 ---> 811109c4413b
Successfully built 811109c4413b
Successfully tagged ken/cicd-app:8376ed1
docker image tag ken/cicd-app:8376ed1 ken/cicd-app:latest
```

```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ken/cicd-app        8376ed1             811109c4413b        3 minutes ago       207MB
ken/cicd-app        latest              811109c4413b        3 minutes ago       207MB
ubuntu              16.04               005d2078bdfa        8 days ago          125MB
kindest/node        <none>              ec6ab22d89ef        3 months ago        1.23GB
```

```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo make REPO=test/app-test build-image
docker build --build-arg HASH=8376ed1 --build-arg LOG="add prodiction for kustomize" --tag test/app-test:8376ed1 .
Sending build context to Docker daemon  32.26kB
Step 1/8 : FROM ubuntu:16.04
 ---> 005d2078bdfa
Step 2/8 : RUN apt-get update &&         apt-get install -y nginx
 ---> Using cache
 ---> f22b4f7bf048
Step 3/8 : ARG HASH
 ---> Using cache
 ---> 98841a2c1e0c
Step 4/8 : ARG LOG
 ---> Using cache
 ---> 01fcebf02406
Step 5/8 : ENV COMMITHASH=$HASH
 ---> Using cache
 ---> 340a74ad605c
Step 6/8 : ENV COMMITLOG=$LOG
 ---> Using cache
 ---> c993b860fc49
Step 7/8 : COPY entrypoint.sh ./
 ---> Using cache
 ---> 70d8e5a1e6df
Step 8/8 : ENTRYPOINT ["/bin/bash", "./entrypoint.sh"]
 ---> Using cache
 ---> 811109c4413b
Successfully built 811109c4413b
Successfully tagged test/app-test:8376ed1
docker image tag test/app-test:8376ed1 test/app-test:latest
```
```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
test/app-test       8376ed1             811109c4413b        7 minutes ago       207MB
test/app-test       latest              811109c4413b        7 minutes ago       207MB
ken/cicd-app        8376ed1             811109c4413b        7 minutes ago       207MB
ken/cicd-app        latest              811109c4413b        7 minutes ago       207MB
ubuntu              16.04               005d2078bdfa        8 days ago          125MB
kindest/node        <none>              ec6ab22d89ef        3 months ago        1.23GB
```
```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: 
Password: 
WARNING! Your password will be stored unencrypted in /home/vagrant/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
```
```console
vagrant@k8s-dev:~/ken/cicd/application$ sudo make push-image
docker build --build-arg HASH=8376ed1 --build-arg LOG="add prodiction for kustomize" --tag 2qov3b/cicd-app:8376ed1 .
Sending build context to Docker daemon  32.26kB
Step 1/8 : FROM ubuntu:16.04
 ---> 005d2078bdfa
Step 2/8 : RUN apt-get update &&         apt-get install -y nginx
 ---> Using cache
 ---> f22b4f7bf048
Step 3/8 : ARG HASH
 ---> Using cache
 ---> 98841a2c1e0c
Step 4/8 : ARG LOG
 ---> Using cache
 ---> 01fcebf02406
Step 5/8 : ENV COMMITHASH=$HASH
 ---> Using cache
 ---> 340a74ad605c
Step 6/8 : ENV COMMITLOG=$LOG
 ---> Using cache
 ---> c993b860fc49
Step 7/8 : COPY entrypoint.sh ./
 ---> Using cache
 ---> 70d8e5a1e6df
Step 8/8 : ENTRYPOINT ["/bin/bash", "./entrypoint.sh"]
 ---> Using cache
 ---> 811109c4413b
Successfully built 811109c4413b
Successfully tagged 2qov3b/cicd-app:8376ed1
docker image tag 2qov3b/cicd-app:8376ed1 2qov3b/cicd-app:latest
docker image push 2qov3b/cicd-app:8376ed1
The push refers to repository [docker.io/2qov3b/cicd-app]
5a21c9db0b76: Pushed 
546151b04813: Pushed 
64d2e4aaa54c: Mounted from ken/cicd-app 
0d3833376c2f: Mounted from ken/cicd-app 
4a048ea09024: Mounted from ken/cicd-app 
b592b5433bbf: Mounted from ken/cicd-app 
8376ed1: digest: sha256:cda5d38808751d7ad3a6b4b0b350c7447dcbba916611e716bd6791b4658eaf68 size: 1569
docker image push 2qov3b/cicd-app:latest
The push refers to repository [docker.io/2qov3b/cicd-app]
5a21c9db0b76: Layer already exists 
546151b04813: Layer already exists 
64d2e4aaa54c: Layer already exists 
0d3833376c2f: Layer already exists 
4a048ea09024: Layer already exists 
b592b5433bbf: Layer already exists 
latest: digest: sha256:cda5d38808751d7ad3a6b4b0b350c7447dcbba916611e716bd6791b4658eaf68 size: 1569
```
```console
vagrant@k8s-dev:~/ken/cicd/application/yamls$ kubectl apply -f .
configmap/index2 created
deployment.apps/debug-pod created
deployment.apps/nginx created
service/nginx created
vagrant@k8s-dev:~/ken/cicd/application/yamls$ kubectl get pods
NAME                         READY   STATUS              RESTARTS   AGE
debug-pod-6845ffcd87-v4cnj   1/1     Running             0          21s
nginx-7b88dbd6bc-7tpcb       1/1     Running             0          21s
nginx-7b88dbd6bc-9zxqk       1/1     Running             0          21s
nginx-7b88dbd6bc-fngc9       0/1     ContainerCreating   0          21s
vagrant@k8s-dev:~/ken/cicd/application/yamls$ kubectl get svc
NAME         TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
kubernetes   ClusterIP   10.96.0.1      <none>        443/TCP        56m
nginx        NodePort    10.96.51.243   <none>        80:30122/TCP   40s
vagrant@k8s-dev:~/ken/cicd/application/yamls$ kubectl get nodes
NAME                 STATUS   ROLES    AGE   VERSION
kind-control-plane   Ready    master   57m   v1.17.0
kind-worker          Ready    <none>   57m   v1.17.0
kind-worker2         Ready    <none>   57m   v1.17.0
vagrant@k8s-dev:~/ken/cicd/application/yamls$ sudo docker ps
CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS                       NAMES
6f17f30b9e6f        kindest/node:v1.17.0   "/usr/local/bin/entr…"   58 minutes ago      Up 58 minutes                                   kind-worker
e0bf64912bde        kindest/node:v1.17.0   "/usr/local/bin/entr…"   58 minutes ago      Up 58 minutes                                   kind-worker2
617a84022558        kindest/node:v1.17.0   "/usr/local/bin/entr…"   58 minutes ago      Up 58 minutes       127.0.0.1:32768->6443/tcp   kind-control-plane
vagrant@k8s-dev:~/ken/cicd/application/yamls$ sudo docker inspect kind-worker | grep -i ip
            "IpcMode": "private",
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.18.0.4",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
                    "IPAMConfig": null,
                    "IPAddress": "172.18.0.4",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
vagrant@k8s-dev:~/ken/cicd/application/yamls$ curl 172.18.0.4:30122
Hostname is ch1_nginx-7b88dbd6bc-fngc9
Latest Commit Hash is ch1_8376ed1
Latest Commit Log is ch1_add prodiction for kustomize
IP address list are ch1_10.244.2.3 
Datetime is Sat May  2 08:40:52 UTC 2020
```

But when you $ curl 172.18.0.4:30122
again, you will get other IPs because we deploy 3 different pods.

```console
$ kubectl get pods -o wide
NAME                         READY   STATUS    RESTARTS   AGE   IP           NODE           NOMINATED NODE   READINESS GATES
debug-pod-6845ffcd87-v4cnj   1/1     Running   0          20h   10.244.2.2   kind-worker    <none>           <none>
nginx-7b88dbd6bc-7tpcb       1/1     Running   0          20h   10.244.1.3   kind-worker2   <none>           <none>
nginx-7b88dbd6bc-9zxqk       1/1     Running   0          20h   10.244.1.2   kind-worker2   <none>           <none>
nginx-7b88dbd6bc-fngc9       1/1     Running   0          20h   10.244.2.3   kind-worker    <none>           <none>
vagrant@k8s-dev:~/ken/cicd/application/yamls$ curl 172.18.0.4:30122
Hostname is ch1_nginx-7b88dbd6bc-9zxqk
Latest Commit Hash is ch1_8376ed1
Latest Commit Log is ch1_add prodiction for kustomize
IP address list are ch1_10.244.1.2 
Datetime is Sat May  2 08:40:40 UTC 2020
```

`kube-apiserver ---(timeout) --> kubelet(node) ---(timeout) --> ConfigMap --> Mount --> Pod`

```console
$ curl 172.18.0.4:30122/test/index2.html
cousre-testing file from ConfigMap
$ vi conf.yaml 
$ kubectl apply -f conf.yaml 
configmap/index2 configured
$ curl 172.18.0.4:30122/test/index2.html
cousre-testing file from ConfigMap
test
la la la
I am testing.
```