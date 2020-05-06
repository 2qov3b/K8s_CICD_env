# MASQUERADE

```console
$ pushd iptables/masquerade
$ vagrant up
Bringing machine 'linux' up with 'virtualbox' provider...
==> linux: Box 'bento/ubuntu-18.04' could not be found. Attempting to find and install...
    linux: Box Provider: virtualbox
    linux: Box Version: 201812.27.0
==> linux: Loading metadata for box 'bento/ubuntu-18.04'
    linux: URL: https://vagrantcloud.com/bento/ubuntu-18.04
==> linux: Adding box 'bento/ubuntu-18.04' (v201812.27.0) for provider: virtualbox
    linux: Downloading: https://vagrantcloud.com/bento/boxes/ubuntu-18.04/versions/201812.27.0/providers/virtualbox.box
    linux: Download redirected to host: vagrantcloud-files-production.s3.amazonaws.com
==> linux: Successfully added box 'bento/ubuntu-18.04' (v201812.27.0) for 'virtualbox'!
==> linux: Importing base box 'bento/ubuntu-18.04'...
==> linux: Matching MAC address for NAT networking...
==> linux: Checking if box 'bento/ubuntu-18.04' version '201812.27.0' is up to date...
==> linux: Setting the name of the VM: masquerade_linux_1588746261554_48824
==> linux: Fixed port collision for 22 => 2222. Now on port 2200.
==> linux: Clearing any previously set network interfaces...
==> linux: Preparing network interfaces based on configuration...
    linux: Adapter 1: nat
    linux: Adapter 2: hostonly
==> linux: Forwarding ports...
    linux: 22 (guest) => 2200 (host) (adapter 1)
==> linux: Running 'pre-boot' VM customizations...
==> linux: Booting VM...
==> linux: Waiting for machine to boot. This may take a few minutes...
    linux: SSH address: 127.0.0.1:2200
    linux: SSH username: vagrant
    linux: SSH auth method: private key
    linux: 
    linux: Vagrant insecure key detected. Vagrant will automatically replace
    linux: this with a newly generated keypair for better security.
    linux: 
    linux: Inserting generated public key within guest...
    linux: Removing insecure key from the guest if it's present...
    linux: Key inserted! Disconnecting and reconnecting using new SSH key...
==> linux: Machine booted and ready!
==> linux: Checking for guest additions in VM...
    linux: The guest additions on this VM do not match the installed version of
    linux: VirtualBox! In most cases this is fine, but in rare cases it can
    linux: prevent things such as shared folders from working properly. If you see
    linux: shared folder errors, please make sure the guest additions within the
    linux: virtual machine match the version of VirtualBox you have installed on
    linux: your host and reload your VM.
    linux: 
    linux: Guest Additions Version: 5.2.22
    linux: VirtualBox Version: 6.1
==> linux: Setting hostname...
==> linux: Configuring and enabling network interfaces...
==> linux: Mounting shared folders...
    linux: /vagrant => /Users/tzuchiehshen/00_2qov3b/MyDevOps/network-study/iptables/masquerade
==> linux: Running provisioner: shell...
    linux: Running: inline script
    linux: ++ export DEBIAN_FRONTEND=noninteractive
    linux: ++ DEBIAN_FRONTEND=noninteractive
    linux: ++ sudo apt-get update
    linux: Get:1 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
    linux: Hit:2 http://archive.ubuntu.com/ubuntu bionic InRelease
    linux: Get:3 http://archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
    linux: Get:4 http://security.ubuntu.com/ubuntu bionic-security/main i386 Packages [464 kB]
    linux: Get:5 http://archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
    linux: Get:6 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [707 kB]
    linux: Get:7 http://archive.ubuntu.com/ubuntu bionic-updates/main i386 Packages [675 kB]
    linux: Get:8 http://security.ubuntu.com/ubuntu bionic-security/main Translation-en [224 kB]
    linux: Get:9 http://security.ubuntu.com/ubuntu bionic-security/restricted amd64 Packages [40.3 kB]
    linux: Get:10 http://security.ubuntu.com/ubuntu bionic-security/restricted i386 Packages [4,280 B]
    linux: Get:11 http://security.ubuntu.com/ubuntu bionic-security/restricted Translation-en [10.2 kB]
    linux: Get:12 http://security.ubuntu.com/ubuntu bionic-security/universe i386 Packages [619 kB]
    linux: Get:13 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [660 kB]
    linux: Get:14 http://security.ubuntu.com/ubuntu bionic-security/universe Translation-en [219 kB]
    linux: Get:15 http://security.ubuntu.com/ubuntu bionic-security/multiverse i386 Packages [4,288 B]
    linux: Get:16 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [7,392 B]
    linux: Get:17 http://security.ubuntu.com/ubuntu bionic-security/multiverse Translation-en [2,788 B]
    linux: Get:18 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [932 kB]
    linux: Get:19 http://archive.ubuntu.com/ubuntu bionic-updates/main Translation-en [318 kB]
    linux: Get:20 http://archive.ubuntu.com/ubuntu bionic-updates/restricted i386 Packages [9,808 B]
    linux: Get:21 http://archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [50.1 kB]
    linux: Get:22 http://archive.ubuntu.com/ubuntu bionic-updates/restricted Translation-en [12.6 kB]
    linux: Get:23 http://archive.ubuntu.com/ubuntu bionic-updates/universe i386 Packages [1,014 kB]
    linux: Get:24 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1,068 kB]
    linux: Get:25 http://archive.ubuntu.com/ubuntu bionic-updates/universe Translation-en [332 kB]
    linux: Get:26 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [15.5 kB]
    linux: Get:27 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse i386 Packages [8,728 B]
    linux: Get:28 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse Translation-en [6,352 B]
    linux: Get:29 http://archive.ubuntu.com/ubuntu bionic-backports/main i386 Packages [7,508 B]
    linux: Get:30 http://archive.ubuntu.com/ubuntu bionic-backports/main amd64 Packages [7,516 B]
    linux: Get:31 http://archive.ubuntu.com/ubuntu bionic-backports/main Translation-en [4,764 B]
    linux: Get:32 http://archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [7,484 B]
    linux: Get:33 http://archive.ubuntu.com/ubuntu bionic-backports/universe i386 Packages [7,472 B]
    linux: Get:34 http://archive.ubuntu.com/ubuntu bionic-backports/universe Translation-en [4,436 B]
    linux: Fetched 7,697 kB in 5s (1,616 kB/s)
    linux: Reading package lists...
    linux: ++ sudo apt-get install -y vim git cmake build-essential tcpdump tig jq
    linux: Reading package lists...
    linux: Building dependency tree...
    linux: Reading state information...
    linux: The following additional packages will be installed:
    linux:   cmake-data cpp cpp-7 dpkg-dev fakeroot g++ g++-7 gcc gcc-7 gcc-7-base
    linux:   gcc-8-base libalgorithm-diff-perl libalgorithm-diff-xs-perl
    linux:   libalgorithm-merge-perl libarchive13 libasan4 libatomic1 libcc1-0
    linux:   libcilkrts5 libdpkg-perl libfakeroot libfile-fcntllock-perl libgcc-7-dev
    linux:   libgcc1 libgomp1 libitm1 libjq1 libjsoncpp1 liblsan0 libmpx2 libonig4
    linux:   libquadmath0 librhash0 libstdc++-7-dev libstdc++6 libtsan0 libubsan0
    linux:   vim-common vim-runtime vim-tiny
    linux: Suggested packages:
    linux:   cmake-doc ninja-build cpp-doc gcc-7-locales debian-keyring g++-multilib
    linux:   g++-7-multilib gcc-7-doc libstdc++6-7-dbg gcc-multilib manpages-dev autoconf
    linux:   automake libtool flex bison gdb gcc-doc gcc-7-multilib libgcc1-dbg
    linux:   libgomp1-dbg libitm1-dbg libatomic1-dbg libasan4-dbg liblsan0-dbg
    linux:   libtsan0-dbg libubsan0-dbg libcilkrts5-dbg libmpx2-dbg libquadmath0-dbg
    linux:   git-daemon-run | git-daemon-sysvinit git-doc git-el git-email git-gui gitk
    linux:   gitweb git-cvs git-mediawiki git-svn lrzip bzr libstdc++-7-doc ctags vim-doc
    linux:   vim-scripts indent
    linux: The following NEW packages will be installed:
    linux:   build-essential cmake cmake-data dpkg-dev fakeroot g++ g++-7 gcc gcc-7 jq
    linux:   libalgorithm-diff-perl libalgorithm-diff-xs-perl libalgorithm-merge-perl
    linux:   libarchive13 libasan4 libatomic1 libcc1-0 libcilkrts5 libdpkg-perl
    linux:   libfakeroot libfile-fcntllock-perl libgcc-7-dev libgomp1 libitm1 libjq1
    linux:   libjsoncpp1 liblsan0 libmpx2 libonig4 libquadmath0 librhash0 libstdc++-7-dev
    linux:   libtsan0 libubsan0 tig
    linux: The following packages will be upgraded:
    linux:   cpp cpp-7 gcc-7-base gcc-8-base git libgcc1 libstdc++6 tcpdump vim
    linux:   vim-common vim-runtime vim-tiny
    linux: 12 upgraded, 35 newly installed, 0 to remove and 232 not upgraded.
    linux: Need to get 51.2 MB of archives.
    linux: After this operation, 122 MB of additional disk space will be used.
    linux: Get:1 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-8-base amd64 8.4.0-1ubuntu1~18.04 [18.7 kB]
    linux: Get:2 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libstdc++6 amd64 8.4.0-1ubuntu1~18.04 [400 kB]
    linux: Get:3 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgcc1 amd64 1:8.4.0-1ubuntu1~18.04 [40.6 kB]
    linux: Get:4 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim amd64 2:8.0.1453-1ubuntu1.3 [1,153 kB]
    linux: Get:5 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-tiny amd64 2:8.0.1453-1ubuntu1.3 [476 kB]
    linux: Get:6 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-runtime all 2:8.0.1453-1ubuntu1.3 [5,436 kB]
    linux: Get:7 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 vim-common all 2:8.0.1453-1ubuntu1.3 [70.6 kB]
    linux: Get:8 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 tcpdump amd64 4.9.3-0ubuntu0.18.04.1 [364 kB]
    linux: Get:9 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cpp-7 amd64 7.5.0-3ubuntu1~18.04 [8,591 kB]
    linux: Get:10 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-7-base amd64 7.5.0-3ubuntu1~18.04 [18.3 kB]
    linux: Get:11 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cpp amd64 4:7.4.0-1ubuntu2.3 [27.7 kB]
    linux: Get:12 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcc1-0 amd64 8.4.0-1ubuntu1~18.04 [39.4 kB]
    linux: Get:13 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgomp1 amd64 8.4.0-1ubuntu1~18.04 [76.5 kB]
    linux: Get:14 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libitm1 amd64 8.4.0-1ubuntu1~18.04 [27.9 kB]
    linux: Get:15 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libatomic1 amd64 8.4.0-1ubuntu1~18.04 [9,192 B]
    linux: Get:16 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libasan4 amd64 7.5.0-3ubuntu1~18.04 [358 kB]
    linux: Get:17 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 liblsan0 amd64 8.4.0-1ubuntu1~18.04 [133 kB]
    linux: Get:18 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libtsan0 amd64 8.4.0-1ubuntu1~18.04 [288 kB]
    linux: Get:19 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libubsan0 amd64 7.5.0-3ubuntu1~18.04 [126 kB]
    linux: Get:20 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libcilkrts5 amd64 7.5.0-3ubuntu1~18.04 [42.5 kB]
    linux: Get:21 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libmpx2 amd64 8.4.0-1ubuntu1~18.04 [11.6 kB]
    linux: Get:22 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libquadmath0 amd64 8.4.0-1ubuntu1~18.04 [134 kB]
    linux: Get:23 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libgcc-7-dev amd64 7.5.0-3ubuntu1~18.04 [2,378 kB]
    linux: Get:24 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc-7 amd64 7.5.0-3ubuntu1~18.04 [9,381 kB]
    linux: Get:25 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 gcc amd64 4:7.4.0-1ubuntu2.3 [5,184 B]
    linux: Get:26 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libstdc++-7-dev amd64 7.5.0-3ubuntu1~18.04 [1,471 kB]
    linux: Get:27 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 g++-7 amd64 7.5.0-3ubuntu1~18.04 [9,697 kB]
    linux: Get:28 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 g++ amd64 4:7.4.0-1ubuntu2.3 [1,568 B]
    linux: Get:29 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libdpkg-perl all 1.19.0.5ubuntu2.3 [211 kB]
    linux: Get:30 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 dpkg-dev all 1.19.0.5ubuntu2.3 [607 kB]
    linux: Get:31 http://archive.ubuntu.com/ubuntu bionic/main amd64 build-essential amd64 12.4ubuntu1 [4,758 B]
    linux: Get:32 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake-data all 3.10.2-1ubuntu2.18.04.1 [1,332 kB]
    linux: Get:33 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libarchive13 amd64 3.2.2-3.1ubuntu0.6 [288 kB]
    linux: Get:34 http://archive.ubuntu.com/ubuntu bionic/main amd64 libjsoncpp1 amd64 1.7.4-3 [73.6 kB]
    linux: Get:35 http://archive.ubuntu.com/ubuntu bionic/main amd64 librhash0 amd64 1.3.6-2 [78.1 kB]
    linux: Get:36 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 cmake amd64 3.10.2-1ubuntu2.18.04.1 [3,152 kB]
    linux: Get:37 http://archive.ubuntu.com/ubuntu bionic/main amd64 libfakeroot amd64 1.22-2ubuntu1 [25.9 kB]
    linux: Get:38 http://archive.ubuntu.com/ubuntu bionic/main amd64 fakeroot amd64 1.22-2ubuntu1 [62.3 kB]
    linux: Get:39 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 git amd64 1:2.17.1-1ubuntu0.7 [3,915 kB]
    linux: Get:40 http://archive.ubuntu.com/ubuntu bionic/universe amd64 libonig4 amd64 6.7.0-1 [119 kB]
    linux: Get:41 http://archive.ubuntu.com/ubuntu bionic/universe amd64 libjq1 amd64 1.5+dfsg-2 [111 kB]
    linux: Get:42 http://archive.ubuntu.com/ubuntu bionic/universe amd64 jq amd64 1.5+dfsg-2 [45.6 kB]
    linux: Get:43 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-perl all 1.19.03-1 [47.6 kB]
    linux: Get:44 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-diff-xs-perl amd64 0.04-5 [11.1 kB]
    linux: Get:45 http://archive.ubuntu.com/ubuntu bionic/main amd64 libalgorithm-merge-perl all 0.08-3 [12.0 kB]
    linux: Get:46 http://archive.ubuntu.com/ubuntu bionic/main amd64 libfile-fcntllock-perl amd64 0.22-3build2 [33.2 kB]
    linux: Get:47 http://archive.ubuntu.com/ubuntu bionic/universe amd64 tig amd64 2.3.0-1 [299 kB]
    linux: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    linux: Fetched 51.2 MB in 31s (1,672 kB/s)
    linux: (Reading database ... 
(Reading database ... 60%ase ... 5%
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 42086 files and directories currently installed.)
    linux: Preparing to unpack .../gcc-8-base_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking gcc-8-base:amd64 (8.4.0-1ubuntu1~18.04) over (8.2.0-1ubuntu2~18.04) ...
    linux: Setting up gcc-8-base:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: (Reading database ... 
    linux: (Reading database ... 5%
(Reading database ... 20%ase ... 10%
    linux: (Reading database ... 25%
(Reading database ... 45%ase ... 30%
(Reading database ... 55%ase ... 50%
    linux: (Reading database ... 60%
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 42086 files and directories currently installed.)
    linux: Preparing to unpack .../libstdc++6_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libstdc++6:amd64 (8.4.0-1ubuntu1~18.04) over (8.2.0-1ubuntu2~18.04) ...
    linux: Setting up libstdc++6:amd64 (8.4.0-1ubuntu1~18.04) ...
(Reading database ... 5%base ... 
    linux: (Reading database ... 10%
(Reading database ... 60%ase ... 15%
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 42086 files and directories currently installed.)
    linux: Preparing to unpack .../libgcc1_1%3a8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libgcc1:amd64 (1:8.4.0-1ubuntu1~18.04) over (1:8.2.0-1ubuntu2~18.04) ...
    linux: Setting up libgcc1:amd64 (1:8.4.0-1ubuntu1~18.04) ...
(Reading database ... 60%ase ... 
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 42086 files and directories currently installed.)
    linux: Preparing to unpack .../00-vim_2%3a8.0.1453-1ubuntu1.3_amd64.deb ...
    linux: Unpacking vim (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1) ...
    linux: Preparing to unpack .../01-vim-tiny_2%3a8.0.1453-1ubuntu1.3_amd64.deb ...
    linux: Unpacking vim-tiny (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1) ...
    linux: Preparing to unpack .../02-vim-runtime_2%3a8.0.1453-1ubuntu1.3_all.deb ...
    linux: Unpacking vim-runtime (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1) ...
    linux: Preparing to unpack .../03-vim-common_2%3a8.0.1453-1ubuntu1.3_all.deb ...
    linux: Unpacking vim-common (2:8.0.1453-1ubuntu1.3) over (2:8.0.1453-1ubuntu1) ...
    linux: Preparing to unpack .../04-tcpdump_4.9.3-0ubuntu0.18.04.1_amd64.deb ...
    linux: Unpacking tcpdump (4.9.3-0ubuntu0.18.04.1) over (4.9.2-3) ...
    linux: Preparing to unpack .../05-cpp-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking cpp-7 (7.5.0-3ubuntu1~18.04) over (7.3.0-27ubuntu1~18.04) ...
    linux: Preparing to unpack .../06-gcc-7-base_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking gcc-7-base:amd64 (7.5.0-3ubuntu1~18.04) over (7.3.0-27ubuntu1~18.04) ...
    linux: Preparing to unpack .../07-cpp_4%3a7.4.0-1ubuntu2.3_amd64.deb ...
    linux: Unpacking cpp (4:7.4.0-1ubuntu2.3) over (4:7.3.0-3ubuntu2.1) ...
    linux: Selecting previously unselected package libcc1-0:amd64.
    linux: Preparing to unpack .../08-libcc1-0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libcc1-0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libgomp1:amd64.
    linux: Preparing to unpack .../09-libgomp1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libgomp1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libitm1:amd64.
    linux: Preparing to unpack .../10-libitm1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libitm1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libatomic1:amd64.
    linux: Preparing to unpack .../11-libatomic1_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libatomic1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libasan4:amd64.
    linux: Preparing to unpack .../12-libasan4_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libasan4:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package liblsan0:amd64.
    linux: Preparing to unpack .../13-liblsan0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking liblsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libtsan0:amd64.
    linux: Preparing to unpack .../14-libtsan0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libtsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libubsan0:amd64.
    linux: Preparing to unpack .../15-libubsan0_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libubsan0:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package libcilkrts5:amd64.
    linux: Preparing to unpack .../16-libcilkrts5_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libcilkrts5:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package libmpx2:amd64.
    linux: Preparing to unpack .../17-libmpx2_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libmpx2:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libquadmath0:amd64.
    linux: Preparing to unpack .../18-libquadmath0_8.4.0-1ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libquadmath0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Selecting previously unselected package libgcc-7-dev:amd64.
    linux: Preparing to unpack .../19-libgcc-7-dev_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libgcc-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package gcc-7.
    linux: Preparing to unpack .../20-gcc-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking gcc-7 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package gcc.
    linux: Preparing to unpack .../21-gcc_4%3a7.4.0-1ubuntu2.3_amd64.deb ...
    linux: Unpacking gcc (4:7.4.0-1ubuntu2.3) ...
    linux: Selecting previously unselected package libstdc++-7-dev:amd64.
    linux: Preparing to unpack .../22-libstdc++-7-dev_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking libstdc++-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package g++-7.
    linux: Preparing to unpack .../23-g++-7_7.5.0-3ubuntu1~18.04_amd64.deb ...
    linux: Unpacking g++-7 (7.5.0-3ubuntu1~18.04) ...
    linux: Selecting previously unselected package g++.
    linux: Preparing to unpack .../24-g++_4%3a7.4.0-1ubuntu2.3_amd64.deb ...
    linux: Unpacking g++ (4:7.4.0-1ubuntu2.3) ...
    linux: Selecting previously unselected package libdpkg-perl.
    linux: Preparing to unpack .../25-libdpkg-perl_1.19.0.5ubuntu2.3_all.deb ...
    linux: Unpacking libdpkg-perl (1.19.0.5ubuntu2.3) ...
    linux: Selecting previously unselected package dpkg-dev.
    linux: Preparing to unpack .../26-dpkg-dev_1.19.0.5ubuntu2.3_all.deb ...
    linux: Unpacking dpkg-dev (1.19.0.5ubuntu2.3) ...
    linux: Selecting previously unselected package build-essential.
    linux: Preparing to unpack .../27-build-essential_12.4ubuntu1_amd64.deb ...
    linux: Unpacking build-essential (12.4ubuntu1) ...
    linux: Selecting previously unselected package cmake-data.
    linux: Preparing to unpack .../28-cmake-data_3.10.2-1ubuntu2.18.04.1_all.deb ...
    linux: Unpacking cmake-data (3.10.2-1ubuntu2.18.04.1) ...
    linux: Selecting previously unselected package libarchive13:amd64.
    linux: Preparing to unpack .../29-libarchive13_3.2.2-3.1ubuntu0.6_amd64.deb ...
    linux: Unpacking libarchive13:amd64 (3.2.2-3.1ubuntu0.6) ...
    linux: Selecting previously unselected package libjsoncpp1:amd64.
    linux: Preparing to unpack .../30-libjsoncpp1_1.7.4-3_amd64.deb ...
    linux: Unpacking libjsoncpp1:amd64 (1.7.4-3) ...
    linux: Selecting previously unselected package librhash0:amd64.
    linux: Preparing to unpack .../31-librhash0_1.3.6-2_amd64.deb ...
    linux: Unpacking librhash0:amd64 (1.3.6-2) ...
    linux: Selecting previously unselected package cmake.
    linux: Preparing to unpack .../32-cmake_3.10.2-1ubuntu2.18.04.1_amd64.deb ...
    linux: Unpacking cmake (3.10.2-1ubuntu2.18.04.1) ...
    linux: Selecting previously unselected package libfakeroot:amd64.
    linux: Preparing to unpack .../33-libfakeroot_1.22-2ubuntu1_amd64.deb ...
    linux: Unpacking libfakeroot:amd64 (1.22-2ubuntu1) ...
    linux: Selecting previously unselected package fakeroot.
    linux: Preparing to unpack .../34-fakeroot_1.22-2ubuntu1_amd64.deb ...
    linux: Unpacking fakeroot (1.22-2ubuntu1) ...
    linux: Preparing to unpack .../35-git_1%3a2.17.1-1ubuntu0.7_amd64.deb ...
    linux: Unpacking git (1:2.17.1-1ubuntu0.7) over (1:2.17.1-1ubuntu0.4) ...
    linux: Selecting previously unselected package libonig4:amd64.
    linux: Preparing to unpack .../36-libonig4_6.7.0-1_amd64.deb ...
    linux: Unpacking libonig4:amd64 (6.7.0-1) ...
    linux: Selecting previously unselected package libjq1:amd64.
    linux: Preparing to unpack .../37-libjq1_1.5+dfsg-2_amd64.deb ...
    linux: Unpacking libjq1:amd64 (1.5+dfsg-2) ...
    linux: Selecting previously unselected package jq.
    linux: Preparing to unpack .../38-jq_1.5+dfsg-2_amd64.deb ...
    linux: Unpacking jq (1.5+dfsg-2) ...
    linux: Selecting previously unselected package libalgorithm-diff-perl.
    linux: Preparing to unpack .../39-libalgorithm-diff-perl_1.19.03-1_all.deb ...
    linux: Unpacking libalgorithm-diff-perl (1.19.03-1) ...
    linux: Selecting previously unselected package libalgorithm-diff-xs-perl.
    linux: Preparing to unpack .../40-libalgorithm-diff-xs-perl_0.04-5_amd64.deb ...
    linux: Unpacking libalgorithm-diff-xs-perl (0.04-5) ...
    linux: Selecting previously unselected package libalgorithm-merge-perl.
    linux: Preparing to unpack .../41-libalgorithm-merge-perl_0.08-3_all.deb ...
    linux: Unpacking libalgorithm-merge-perl (0.08-3) ...
    linux: Selecting previously unselected package libfile-fcntllock-perl.
    linux: Preparing to unpack .../42-libfile-fcntllock-perl_0.22-3build2_amd64.deb ...
    linux: Unpacking libfile-fcntllock-perl (0.22-3build2) ...
    linux: Selecting previously unselected package tig.
    linux: Preparing to unpack .../43-tig_2.3.0-1_amd64.deb ...
    linux: Unpacking tig (2.3.0-1) ...
    linux: Setting up libquadmath0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up libgomp1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up libatomic1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up libcc1-0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Processing triggers for mime-support (3.60ubuntu1) ...
    linux: Setting up libarchive13:amd64 (3.2.2-3.1ubuntu0.6) ...
    linux: Setting up libtsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up libonig4:amd64 (6.7.0-1) ...
    linux: Setting up libdpkg-perl (1.19.0.5ubuntu2.3) ...
    linux: Setting up cmake-data (3.10.2-1ubuntu2.18.04.1) ...
    linux: Setting up tcpdump (4.9.3-0ubuntu0.18.04.1) ...
    linux: Setting up librhash0:amd64 (1.3.6-2) ...
    linux: Setting up liblsan0:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up gcc-7-base:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up libfile-fcntllock-perl (0.22-3build2) ...
    linux: Setting up libjq1:amd64 (1.5+dfsg-2) ...
    linux: Setting up libmpx2:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up dpkg-dev (1.19.0.5ubuntu2.3) ...
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: Setting up libfakeroot:amd64 (1.22-2ubuntu1) ...
    linux: Setting up vim-common (2:8.0.1453-1ubuntu1.3) ...
    linux: Setting up libalgorithm-diff-perl (1.19.03-1) ...
    linux: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    linux: Setting up vim-runtime (2:8.0.1453-1ubuntu1.3) ...
    linux: Setting up git (1:2.17.1-1ubuntu0.7) ...
    linux: Setting up libitm1:amd64 (8.4.0-1ubuntu1~18.04) ...
    linux: Setting up libjsoncpp1:amd64 (1.7.4-3) ...
    linux: Setting up vim-tiny (2:8.0.1453-1ubuntu1.3) ...
    linux: Setting up jq (1.5+dfsg-2) ...
    linux: Setting up libasan4:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up vim (2:8.0.1453-1ubuntu1.3) ...
    linux: Setting up libcilkrts5:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up libubsan0:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up tig (2.3.0-1) ...
    linux: Setting up fakeroot (1.22-2ubuntu1) ...
    linux: update-alternatives: using /usr/bin/fakeroot-sysv to provide /usr/bin/fakeroot (fakeroot) in auto mode
    linux: Setting up libgcc-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up cpp-7 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up libstdc++-7-dev:amd64 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up libalgorithm-merge-perl (0.08-3) ...
    linux: Setting up libalgorithm-diff-xs-perl (0.04-5) ...
    linux: Setting up cmake (3.10.2-1ubuntu2.18.04.1) ...
    linux: Setting up cpp (4:7.4.0-1ubuntu2.3) ...
    linux: Setting up gcc-7 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up g++-7 (7.5.0-3ubuntu1~18.04) ...
    linux: Setting up gcc (4:7.4.0-1ubuntu2.3) ...
    linux: Setting up g++ (4:7.4.0-1ubuntu2.3) ...
    linux: update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
    linux: Setting up build-essential (12.4ubuntu1) ...
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: ++ git clone https://github.com/hwchiu/network-study
    linux: Cloning into 'network-study'...
    linux: +++ uname -r
    linux: ++ sudo apt-get install -y linux-headers-4.15.0-29-generic
    linux: Reading package lists...
    linux: Building dependency tree...
    linux: 
    linux: Reading state information...
    linux: The following additional packages will be installed:
    linux:   linux-headers-4.15.0-29
    linux: The following NEW packages will be installed:
    linux:   linux-headers-4.15.0-29 linux-headers-4.15.0-29-generic
    linux: 0 upgraded, 2 newly installed, 0 to remove and 232 not upgraded.
    linux: Need to get 12.1 MB of archives.
    linux: After this operation, 89.7 MB of additional disk space will be used.
    linux: Get:1 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 linux-headers-4.15.0-29 all 4.15.0-29.31 [11.0 MB]
    linux: Get:2 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 linux-headers-4.15.0-29-generic amd64 4.15.0-29.31 [1,089 kB]
    linux: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    linux: Fetched 12.1 MB in 8s (1,607 kB/s)
    linux: Selecting previously unselected package linux-headers-4.15.0-29.
(Reading database ... 5%base ... 
    linux: (Reading database ... 10%
(Reading database ... 25%ase ... 15%
    linux: (Reading database ... 30%
    linux: (Reading database ... 35%
    linux: (Reading database ... 40%
    linux: (Reading database ... 45%
    linux: (Reading database ... 50%
    linux: (Reading database ... 55%
    linux: (Reading database ... 60%
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 46110 files and directories currently installed.)
    linux: Preparing to unpack .../linux-headers-4.15.0-29_4.15.0-29.31_all.deb ...
    linux: Unpacking linux-headers-4.15.0-29 (4.15.0-29.31) ...
    linux: Selecting previously unselected package linux-headers-4.15.0-29-generic.
    linux: Preparing to unpack .../linux-headers-4.15.0-29-generic_4.15.0-29.31_amd64.deb ...
    linux: Unpacking linux-headers-4.15.0-29-generic (4.15.0-29.31) ...
    linux: Setting up linux-headers-4.15.0-29 (4.15.0-29.31) ...
    linux: Setting up linux-headers-4.15.0-29-generic (4.15.0-29.31) ...
    linux: ++ cd network-study/iptables/masquerade/module
    linux: ++ sudo make
    linux: make -C /lib/modules/4.15.0-29-generic/build M=/home/vagrant/network-study/iptables/masquerade/module modules
    linux: make[1]: Entering directory '/usr/src/linux-headers-4.15.0-29-generic'
    linux: Makefile:976: "Cannot use CONFIG_STACK_VALIDATION=y, please install libelf-dev, libelf-devel or elfutils-libelf-devel"
    linux:   CC [M]  /home/vagrant/network-study/iptables/masquerade/module/ipt_MASQUERADE.o
    linux:   Building modules, stage 2.
    linux:   MODPOST 1 modules
    linux:   CC      /home/vagrant/network-study/iptables/masquerade/module/ipt_MASQUERADE.mod.o
    linux:   LD [M]  /home/vagrant/network-study/iptables/masquerade/module/ipt_MASQUERADE.ko
    linux: make[1]: Leaving directory '/usr/src/linux-headers-4.15.0-29-generic'
    linux: +++ uname -r
    linux: ++ sudo cp ipt_MASQUERADE.ko /lib/modules/4.15.0-29-generic/kernel/net/ipv4/netfilter/ipt_MASQUERADE.ko
    linux: ++ sudo apt-get install -y ntp
    linux: Reading package lists...
    linux: Building dependency tree...
    linux: Reading state information...
    linux: The following additional packages will be installed:
    linux:   libopts25 sntp
    linux: Suggested packages:
    linux:   ntp-doc
    linux: The following NEW packages will be installed:
    linux:   libopts25 ntp sntp
    linux: 0 upgraded, 3 newly installed, 0 to remove and 232 not upgraded.
    linux: Need to get 785 kB of archives.
    linux: After this operation, 2,393 kB of additional disk space will be used.
    linux: Get:1 http://archive.ubuntu.com/ubuntu bionic/universe amd64 libopts25 amd64 1:5.18.12-4 [58.2 kB]
    linux: Get:2 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 ntp amd64 1:4.2.8p10+dfsg-5ubuntu7.1 [640 kB]
    linux: Get:3 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 sntp amd64 1:4.2.8p10+dfsg-5ubuntu7.1 [86.9 kB]
    linux: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    linux: Fetched 785 kB in 3s (296 kB/s)
    linux: Selecting previously unselected package libopts25:amd64.
    linux: (Reading database ... 
    linux: (Reading database ... 5%
    linux: (Reading database ... 10%
    linux: (Reading database ... 15%
    linux: (Reading database ... 20%
    linux: (Reading database ... 25%
    linux: (Reading database ... 30%
    linux: (Reading database ... 35%
    linux: (Reading database ... 40%
    linux: (Reading database ... 45%
    linux: (Reading database ... 50%
    linux: (Reading database ... 55%
    linux: (Reading database ... 60%
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
    linux: (Reading database ... 100%
    linux: (Reading database ... 
    linux: 75467 files and directories currently installed.)
    linux: Preparing to unpack .../libopts25_1%3a5.18.12-4_amd64.deb ...
    linux: Unpacking libopts25:amd64 (1:5.18.12-4) ...
    linux: Selecting previously unselected package ntp.
    linux: Preparing to unpack .../ntp_1%3a4.2.8p10+dfsg-5ubuntu7.1_amd64.deb ...
    linux: Unpacking ntp (1:4.2.8p10+dfsg-5ubuntu7.1) ...
    linux: Selecting previously unselected package sntp.
    linux: Preparing to unpack .../sntp_1%3a4.2.8p10+dfsg-5ubuntu7.1_amd64.deb ...
    linux: Unpacking sntp (1:4.2.8p10+dfsg-5ubuntu7.1) ...
    linux: Processing triggers for ureadahead (0.100.0-20) ...
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: Processing triggers for systemd (237-3ubuntu10.9) ...
    linux: Setting up libopts25:amd64 (1:5.18.12-4) ...
    linux: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    linux: Setting up sntp (1:4.2.8p10+dfsg-5ubuntu7.1) ...
    linux: Setting up ntp (1:4.2.8p10+dfsg-5ubuntu7.1) ...
    linux: Created symlink /etc/systemd/system/network-pre.target.wants/ntp-systemd-netif.path → /lib/systemd/system/ntp-systemd-netif.path.
    linux: Created symlink /etc/systemd/system/multi-user.target.wants/ntp.service → /lib/systemd/system/ntp.service.
    linux: ntp-systemd-netif.service is a disabled or a static unit, not starting it.
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: Processing triggers for systemd (237-3ubuntu10.9) ...
    linux: Processing triggers for ureadahead (0.100.0-20) ...
    linux: ++ export DOCKER_VERSION=18.06.3~ce~3-0~ubuntu
    linux: ++ DOCKER_VERSION=18.06.3~ce~3-0~ubuntu
    linux: ++ curl -fsSL https://download.docker.com/linux/ubuntu/gpg
    linux: ++ sudo apt-key add -
    linux: Warning: apt-key output should not be parsed (stdout is not a terminal)
    linux: OK
    linux: +++ lsb_release -cs
    linux: ++ sudo add-apt-repository 'deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable'
    linux: Get:1 https://download.docker.com/linux/ubuntu bionic InRelease [64.4 kB]
    linux: Get:2 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages [11.0 kB]
    linux: Hit:3 http://archive.ubuntu.com/ubuntu bionic InRelease
    linux: Hit:4 http://security.ubuntu.com/ubuntu bionic-security InRelease
    linux: Hit:5 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    linux: Hit:6 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    linux: Fetched 75.5 kB in 1s (74.4 kB/s)
    linux: Reading package lists...
    linux: ++ sudo apt-get update
    linux: Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
    linux: Hit:2 http://security.ubuntu.com/ubuntu bionic-security InRelease
    linux: Hit:3 http://archive.ubuntu.com/ubuntu bionic InRelease
    linux: Hit:4 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    linux: Hit:5 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    linux: Reading package lists...
    linux: ++ sudo apt-get install -y docker-ce=18.06.3~ce~3-0~ubuntu
    linux: Reading package lists...
    linux: Building dependency tree...
    linux: Reading state information...
    linux: The following additional packages will be installed:
    linux:   aufs-tools cgroupfs-mount libltdl7 pigz
    linux: The following NEW packages will be installed:
    linux:   aufs-tools cgroupfs-mount docker-ce libltdl7 pigz
    linux: 0 upgraded, 5 newly installed, 0 to remove and 232 not upgraded.
    linux: Need to get 40.4 MB of archives.
    linux: After this operation, 199 MB of additional disk space will be used.
    linux: Get:1 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce amd64 18.06.3~ce~3-0~ubuntu [40.2 MB]
    linux: Get:2 http://archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
    linux: Get:3 http://archive.ubuntu.com/ubuntu bionic/universe amd64 aufs-tools amd64 1:4.9+20170918-1ubuntu1 [104 kB]
    linux: Get:4 http://archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6,320 B]
    linux: Get:5 http://archive.ubuntu.com/ubuntu bionic/main amd64 libltdl7 amd64 2.4.6-2 [38.8 kB]
    linux: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    linux: Fetched 40.4 MB in 3s (13.0 MB/s)
    linux: Selecting previously unselected package pigz.
(Reading database ... 60%ase ... 
    linux: (Reading database ... 65%
    linux: (Reading database ... 70%
    linux: (Reading database ... 75%
    linux: (Reading database ... 80%
    linux: (Reading database ... 85%
    linux: (Reading database ... 90%
    linux: (Reading database ... 95%
(Reading database ... 75543 files and directories currently installed.)
    linux: Preparing to unpack .../archives/pigz_2.4-1_amd64.deb ...
    linux: Unpacking pigz (2.4-1) ...
    linux: Selecting previously unselected package aufs-tools.
    linux: Preparing to unpack .../aufs-tools_1%3a4.9+20170918-1ubuntu1_amd64.deb ...
    linux: Unpacking aufs-tools (1:4.9+20170918-1ubuntu1) ...
    linux: Selecting previously unselected package cgroupfs-mount.
    linux: Preparing to unpack .../cgroupfs-mount_1.4_all.deb ...
    linux: Unpacking cgroupfs-mount (1.4) ...
    linux: Selecting previously unselected package libltdl7:amd64.
    linux: Preparing to unpack .../libltdl7_2.4.6-2_amd64.deb ...
    linux: Unpacking libltdl7:amd64 (2.4.6-2) ...
    linux: Selecting previously unselected package docker-ce.
    linux: Preparing to unpack .../docker-ce_18.06.3~ce~3-0~ubuntu_amd64.deb ...
    linux: Unpacking docker-ce (18.06.3~ce~3-0~ubuntu) ...
    linux: Setting up aufs-tools (1:4.9+20170918-1ubuntu1) ...
    linux: Processing triggers for ureadahead (0.100.0-20) ...
    linux: Setting up cgroupfs-mount (1.4) ...
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: Processing triggers for systemd (237-3ubuntu10.9) ...
    linux: Setting up libltdl7:amd64 (2.4.6-2) ...
    linux: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    linux: Setting up pigz (2.4-1) ...
    linux: Setting up docker-ce (18.06.3~ce~3-0~ubuntu) ...
    linux: Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
    linux: Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
    linux: Processing triggers for ureadahead (0.100.0-20) ...
    linux: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    linux: Processing triggers for systemd (237-3ubuntu10.9) ...
```

# K8s iptables

```console
cker-ce=18.06.3~ce~3-0~ubuntu
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: 
    k8s: Reading state information...
    k8s: The following additional packages will be installed:
    k8s:   aufs-tools cgroupfs-mount pigz
    k8s: The following NEW packages will be installed:
    k8s:   aufs-tools cgroupfs-mount docker-ce pigz
    k8s: 0 upgraded, 4 newly installed, 0 to remove and 91 not upgraded.
    k8s: Need to get 40.4 MB of archives.
    k8s: After this operation, 198 MB of additional disk space will be used.
    k8s: Get:1 https://download.docker.com/linux/ubuntu bionic/stable amd64 docker-ce amd64 18.06.3~ce~3-0~ubuntu [40.2 MB]
    k8s: Get:2 http://archive.ubuntu.com/ubuntu bionic/universe amd64 pigz amd64 2.4-1 [57.4 kB]
    k8s: Get:3 http://archive.ubuntu.com/ubuntu bionic/universe amd64 aufs-tools amd64 1:4.9+20170918-1ubuntu1 [104 kB]
    k8s: Get:4 http://archive.ubuntu.com/ubuntu bionic/universe amd64 cgroupfs-mount all 1.4 [6,320 B]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 40.4 MB in 2s (23.3 MB/s)
    k8s: Selecting previously unselected package pigz.
    k8s: (Reading database ... 
(Reading database ... 60%e ... 5%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
(Reading database ... 77537 files and directories currently installed.)
    k8s: Preparing to unpack .../archives/pigz_2.4-1_amd64.deb ...
    k8s: Unpacking pigz (2.4-1) ...
    k8s: Selecting previously unselected package aufs-tools.
    k8s: Preparing to unpack .../aufs-tools_1%3a4.9+20170918-1ubuntu1_amd64.deb ...
    k8s: Unpacking aufs-tools (1:4.9+20170918-1ubuntu1) ...
    k8s: Selecting previously unselected package cgroupfs-mount.
    k8s: Preparing to unpack .../cgroupfs-mount_1.4_all.deb ...
    k8s: Unpacking cgroupfs-mount (1.4) ...
    k8s: Selecting previously unselected package docker-ce.
    k8s: Preparing to unpack .../docker-ce_18.06.3~ce~3-0~ubuntu_amd64.deb ...
    k8s: Unpacking docker-ce (18.06.3~ce~3-0~ubuntu) ...
    k8s: Setting up aufs-tools (1:4.9+20170918-1ubuntu1) ...
    k8s: Setting up docker-ce (18.06.3~ce~3-0~ubuntu) ...
    k8s: Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
    k8s: Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
    k8s: Setting up cgroupfs-mount (1.4) ...
    k8s: Setting up pigz (2.4-1) ...
    k8s: Processing triggers for libc-bin (2.27-3ubuntu1) ...
    k8s: Processing triggers for systemd (237-3ubuntu10.33) ...
    k8s: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    k8s: Processing triggers for ureadahead (0.100.0-21) ...
    k8s: ++ git clone https://github.com/hwchiu/network-study
    k8s: Cloning into 'network-study'...
    k8s: ++ cd /home/vagrant/network-study/iptables/k8s/module
    k8s: ++ sudo make
    k8s: make -C /lib/modules/4.15.0-72-generic/build M=/home/vagrant/network-study/iptables/k8s/module modules
    k8s: make[1]: Entering directory '/usr/src/linux-headers-4.15.0-72-generic'
    k8s:   CC [M]  /home/vagrant/network-study/iptables/k8s/module/xt_statistic.o
    k8s:   Building modules, stage 2.
    k8s:   MODPOST 1 modules
    k8s:   CC      /home/vagrant/network-study/iptables/k8s/module/xt_statistic.mod.o
    k8s:   LD [M]  /home/vagrant/network-study/iptables/k8s/module/xt_statistic.ko
    k8s: make[1]: Leaving directory '/usr/src/linux-headers-4.15.0-72-generic'
    k8s: +++ uname -r
    k8s: ++ sudo cp xt_statistic.ko /lib/modules/4.15.0-72-generic/kernel/net/netfilter/xt_statistic.ko
    k8s: ++ mkdir /home/vagrant/network-study/iptables/k8s/module/custom/user
    k8s: ++ cd /home/vagrant/network-study/iptables/k8s/module/custom/user
    k8s: ++ git clone -b v1.6.1 git://git.netfilter.org/iptables
    k8s: Cloning into 'iptables'...
    k8s: Note: checking out '7df66f1c13563cfbab75246b009ce36f69ee4487'.
    k8s: 
    k8s: You are in 'detached HEAD' state. You can look around, make experimental
    k8s: changes and commit them, and you can discard any commits you make in this
    k8s: state without impacting any branches by performing another checkout.
    k8s: 
    k8s: If you want to create a new branch to retain commits you create, you may
    k8s: do so (now or later) by using -b with the checkout command again. Example:
    k8s: 
    k8s:   git checkout -b <new-branch-name>
    k8s: ++ cd iptables
    k8s: ++ ./autogen.sh
    k8s: libtoolize: putting auxiliary files in AC_CONFIG_AUX_DIR, 'build-aux'.
    k8s: libtoolize: copying file 'build-aux/ltmain.sh'
    k8s: libtoolize: putting macros in AC_CONFIG_MACRO_DIRS, 'm4'.
    k8s: libtoolize: copying file 'm4/libtool.m4'
    k8s: libtoolize: copying file 'm4/ltoptions.m4'
    k8s: libtoolize: copying file 'm4/ltsugar.m4'
    k8s: libtoolize: copying file 'm4/ltversion.m4'
    k8s: libtoolize: copying file 'm4/lt~obsolete.m4'
    k8s: configure.ac:16: installing 'build-aux/ar-lib'
    k8s: configure.ac:13: installing 'build-aux/compile'
    k8s: configure.ac:17: installing 'build-aux/config.guess'
    k8s: configure.ac:17: installing 'build-aux/config.sub'
    k8s: configure.ac:11: installing 'build-aux/install-sh'
    k8s: configure.ac:12: installing 'build-aux/missing'
    k8s: iptables/Makefile.am: installing 'build-aux/depcomp'
    k8s: configure.ac: installing 'build-aux/ylwrap'
    k8s: ++ ./configure --disable-nftables --enable-static --enable-shared
    k8s: checking for a BSD-compatible install... 
    k8s: /usr/bin/install -c
    k8s: checking whether build environment is sane... 
    k8s: yes
    k8s: checking for a thread-safe mkdir -p... 
    k8s: /bin/mkdir -p
    k8s: checking for gawk... 
    k8s: gawk
    k8s: checking whether make sets $(MAKE)... 
    k8s: yes
    k8s: checking whether make supports nested variables... 
    k8s: yes
    k8s: checking for gcc... 
    k8s: gcc
    k8s: checking whether the C compiler works... 
    k8s: yes
    k8s: checking for C compiler default output file name... a.out
    k8s: checking for suffix of executables... 
    k8s: checking whether we are cross compiling... 
    k8s: no
    k8s: checking for suffix of object files... 
    k8s: o
    k8s: checking whether we are using the GNU C compiler... 
    k8s: yes
    k8s: checking whether gcc accepts -g... 
    k8s: yes
    k8s: checking for gcc option to accept ISO C89... 
    k8s: none needed
    k8s: checking whether gcc understands -c and -o together... 
    k8s: yes
    k8s: checking for style of include used by make... 
    k8s: GNU
    k8s: checking dependency style of gcc... 
    k8s: gcc3
    k8s: checking for ar... 
    k8s: ar
    k8s: checking the archiver (ar) interface... 
    k8s: ar
    k8s: checking build system type... 
    k8s: x86_64-pc-linux-gnu
    k8s: checking host system type... 
    k8s: x86_64-pc-linux-gnu
    k8s: checking how to print strings... 
    k8s: printf
    k8s: checking for a sed that does not truncate output... 
    k8s: /bin/sed
    k8s: checking for grep that handles long lines and -e... 
    k8s: /bin/grep
    k8s: checking for egrep... 
    k8s: /bin/grep -E
    k8s: checking for fgrep... 
    k8s: /bin/grep -F
    k8s: checking for ld used by gcc... 
    k8s: /usr/bin/ld
    k8s: checking if the linker (/usr/bin/ld) is GNU ld... 
    k8s: yes
    k8s: checking for BSD- or MS-compatible name lister (nm)... 
    k8s: /usr/bin/nm -B
    k8s: checking the name lister (/usr/bin/nm -B) interface... 
    k8s: BSD nm
    k8s: checking whether ln -s works... 
    k8s: yes
    k8s: checking the maximum length of command line arguments... 
    k8s: 1572864
    k8s: checking how to convert x86_64-pc-linux-gnu file names to x86_64-pc-linux-gnu format... 
    k8s: func_convert_file_noop
    k8s: checking how to convert x86_64-pc-linux-gnu file names to toolchain format... 
    k8s: func_convert_file_noop
    k8s: checking for /usr/bin/ld option to reload object files... 
    k8s: -r
    k8s: checking for objdump... 
    k8s: objdump
    k8s: checking how to recognize dependent libraries... 
    k8s: pass_all
    k8s: checking for dlltool... 
    k8s: no
    k8s: checking how to associate runtime and link libraries... 
    k8s: printf %s\n
    k8s: checking for archiver @FILE support... 
    k8s: @
    k8s: checking for strip... 
    k8s: strip
    k8s: checking for ranlib... 
    k8s: ranlib
    k8s: checking command to parse /usr/bin/nm -B output from gcc object... 
    k8s: ok
    k8s: checking for sysroot... 
    k8s: no
    k8s: checking for a working dd... 
    k8s: /bin/dd
    k8s: checking how to truncate binary pipes... 
    k8s: /bin/dd bs=4096 count=1
    k8s: checking for mt... 
    k8s: mt
    k8s: checking if mt is a manifest tool... 
    k8s: no
    k8s: checking how to run the C preprocessor... 
    k8s: gcc -E
    k8s: checking for ANSI C header files... 
    k8s: yes
    k8s: checking for sys/types.h... 
    k8s: yes
    k8s: checking for sys/stat.h... 
    k8s: yes
    k8s: checking for stdlib.h... 
    k8s: yes
    k8s: checking for string.h... 
    k8s: yes
    k8s: checking for memory.h... 
    k8s: yes
    k8s: checking for strings.h... 
    k8s: yes
    k8s: checking for inttypes.h... 
    k8s: yes
    k8s: checking for stdint.h... 
    k8s: yes
    k8s: checking for unistd.h... 
    k8s: yes
    k8s: checking for dlfcn.h... 
    k8s: yes
    k8s: checking for objdir... 
    k8s: .libs
    k8s: checking if gcc supports -fno-rtti -fno-exceptions... 
    k8s: no
    k8s: checking for gcc option to produce PIC... 
    k8s: -fPIC -DPIC
    k8s: checking if gcc PIC flag -fPIC -DPIC works... 
    k8s: yes
    k8s: checking if gcc static flag -static works... 
    k8s: yes
    k8s: checking if gcc supports -c -o file.o... 
    k8s: yes
    k8s: checking if gcc supports -c -o file.o... (cached) yes
    k8s: checking whether the gcc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... 
    k8s: yes
    k8s: checking whether -lc should be explicitly linked in... 
    k8s: no
    k8s: checking dynamic linker characteristics... 
    k8s: GNU/Linux ld.so
    k8s: checking how to hardcode library paths into programs... 
    k8s: immediate
    k8s: checking whether stripping libraries is possible... 
    k8s: yes
    k8s: checking if libtool supports shared libraries... 
    k8s: yes
    k8s: checking whether to build shared libraries... yes
    k8s: checking whether to build static libraries... 
    k8s: yes
    k8s: checking whether the linker accepts -Wl,--no-as-needed... 
    k8s: yes
    k8s: checking whether /usr/bin/ld -m elf_x86_64 knows -Wl,--no-undefined... 
    k8s: yes
    k8s: checking linux/dccp.h usability... 
    k8s: yes
    k8s: checking linux/dccp.h presence... 
    k8s: yes
    k8s: checking for linux/dccp.h... yes
    k8s: checking linux/ip_vs.h usability... 
    k8s: yes
    k8s: checking linux/ip_vs.h presence... 
    k8s: yes
    k8s: checking for linux/ip_vs.h... yes
    k8s: checking linux/magic.h usability... 
    k8s: yes
    k8s: checking linux/magic.h presence... 
    k8s: yes
    k8s: checking for linux/magic.h... yes
    k8s: checking linux/proc_fs.h usability... 
    k8s: no
    k8s: checking linux/proc_fs.h presence... 
    k8s: no
    k8s: checking for linux/proc_fs.h... no
    k8s: checking linux/bpf.h usability... 
    k8s: yes
    k8s: checking linux/bpf.h presence... 
    k8s: yes
    k8s: checking for linux/bpf.h... yes
    k8s: checking size of struct ip6_hdr... 
    k8s: 40
    k8s: checking for pkg-config... /usr/bin/pkg-config
    k8s: checking pkg-config is at least version 0.9.0... 
    k8s: yes
    k8s: checking for libnfnetlink... 
    k8s: yes
    k8s: checking for libnetfilter_conntrack... 
    k8s: no
    k8s: WARNING: libnetfilter_conntrack not found, connlabel match will not be built
    k8s: checking that generated files are newer than configure... 
    k8s: done
    k8s: configure: creating ./config.status
    k8s: config.status: creating Makefile
    k8s: config.status: creating extensions/GNUmakefile
    k8s: config.status: creating include/Makefile
    k8s: config.status: creating iptables/Makefile
    k8s: config.status: creating iptables/xtables.pc
    k8s: config.status: creating iptables/iptables.8
    k8s: config.status: creating iptables/iptables-extensions.8.tmpl
    k8s: config.status: creating iptables/iptables-save.8
    k8s: config.status: creating iptables/iptables-restore.8
    k8s: config.status: creating iptables/iptables-apply.8
    k8s: config.status: creating iptables/iptables-xml.1
    k8s: config.status: creating libipq/Makefile
    k8s: config.status: creating libipq/libipq.pc
    k8s: config.status: creating libiptc/Makefile
    k8s: config.status: creating libiptc/libiptc.pc
    k8s: config.status: creating libiptc/libip4tc.pc
    k8s: config.status: creating libiptc/libip6tc.pc
    k8s: config.status: creating libxtables/Makefile
    k8s: config.status: creating utils/Makefile
    k8s: config.status: creating include/xtables-version.h
    k8s: config.status: creating include/iptables/internal.h
    k8s: config.status: creating config.h
    k8s: config.status: executing depfiles commands
    k8s: config.status: executing libtool commands
    k8s: 
    k8s: Iptables Configuration:
    k8s:   IPv4 support:                                yes
    k8s:   IPv6 support:                                yes
    k8s:   Devel support:                       yes
    k8s:   IPQ support:                         no
    k8s:   Large file support:                  yes
    k8s:   BPF utils support:                   no
    k8s:   nfsynproxy util support:             no
    k8s:   nftables support:                    no
    k8s:   connlabel support:                   no
    k8s: 
    k8s: Build parameters:
    k8s:   Put plugins into executable (static):        yes
    k8s:   Support plugins via dlopen (shared): yes
    k8s:   Installation prefix (--prefix):      /usr/local
    k8s:   Xtables extension directory:         /usr/local/lib/xtables
    k8s:   Pkg-config directory:                        /usr/local/lib/pkgconfig
    k8s:   Host:                                        x86_64-pc-linux-gnu
    k8s:   GCC binary:                          gcc
    k8s: 
    k8s: Iptables modules that will not be built:  connlabel
    k8s: ++ git am ../../0001-Prototype-of-iptables-module.patch
    k8s: Applying: Prototype of iptables module
    k8s: ++ make
    k8s: make  all-recursive
    k8s: make[1]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables'
    k8s: Making all in libiptc
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/libiptc'
    k8s: /bin/bash ../libtool  --tag=CC   --mode=compile gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT       -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include   -Wall -Waggregate-return -Wmissing-declarations      -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -MT libip4tc.lo -MD -MP -MF .deps/libip4tc.Tpo -c -o libip4tc.lo libip4tc.c
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libip4tc.lo -MD -MP -MF .deps/libip4tc.Tpo -c libip4tc.c  -fPIC -DPIC -o .libs/libip4tc.o
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libip4tc.lo -MD -MP -MF .deps/libip4tc.Tpo -c libip4tc.c -o libip4tc.o >/dev/null 2>&1
    k8s: mv -f .deps/libip4tc.Tpo .deps/libip4tc.Plo
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -version-info 1:0:1  -o libip4tc.la -rpath /usr/local/lib libip4tc.lo  
    k8s: libtool: link: gcc -shared  -fPIC -DPIC  .libs/libip4tc.o    -g -O2   -Wl,-soname -Wl,libip4tc.so.0 -o .libs/libip4tc.so.0.1.0
    k8s: libtool: link: (cd ".libs" && rm -f "libip4tc.so.0" && ln -s "libip4tc.so.0.1.0" "libip4tc.so.0")
    k8s: libtool: link: (cd ".libs" && rm -f "libip4tc.so" && ln -s "libip4tc.so.0.1.0" "libip4tc.so")
    k8s: libtool: link: ar cru .libs/libip4tc.a  libip4tc.o
    k8s: ar: 
    k8s: `u' modifier ignored since `D' is the default (see `U')
    k8s: libtool: link: ranlib .libs/libip4tc.a
    k8s: libtool: link: ( cd ".libs" && rm -f "libip4tc.la" && ln -s "../libip4tc.la" "libip4tc.la" )
    k8s: /bin/bash ../libtool  --tag=CC   --mode=compile gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT       -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include   -Wall -Waggregate-return -Wmissing-declarations      -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -MT libip6tc.lo -MD -MP -MF .deps/libip6tc.Tpo -c -o libip6tc.lo libip6tc.c
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libip6tc.lo -MD -MP -MF .deps/libip6tc.Tpo -c libip6tc.c  -fPIC -DPIC -o .libs/libip6tc.o
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libip6tc.lo -MD -MP -MF .deps/libip6tc.Tpo -c libip6tc.c -o libip6tc.o >/dev/null 2>&1
    k8s: mv -f .deps/libip6tc.Tpo .deps/libip6tc.Plo
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -version-info 1:0:1 -Wl,--no-as-needed  -o libip6tc.la -rpath /usr/local/lib libip6tc.lo  
    k8s: libtool: link: gcc -shared  -fPIC -DPIC  .libs/libip6tc.o    -g -O2 -Wl,--no-as-needed   -Wl,-soname -Wl,libip6tc.so.0 -o .libs/libip6tc.so.0.1.0
    k8s: libtool: link: (cd ".libs" && rm -f "libip6tc.so.0" && ln -s "libip6tc.so.0.1.0" "libip6tc.so.0")
    k8s: libtool: link: (cd ".libs" && rm -f "libip6tc.so" && ln -s "libip6tc.so.0.1.0" "libip6tc.so")
    k8s: libtool: link: ar cru .libs/libip6tc.a  libip6tc.o
    k8s: ar: `u' modifier ignored since `D' is the default (see `U')
    k8s: libtool: link: ranlib .libs/libip6tc.a
    k8s: libtool: link: ( cd ".libs" && rm -f "libip6tc.la" && ln -s "../libip6tc.la" "libip6tc.la" )
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -version-info 0:0:0 -Wl,--no-as-needed  -o libiptc.la -rpath /usr/local/lib  libip4tc.la libip6tc.la 
    k8s: libtool: link: gcc -shared  -fPIC -DPIC   -Wl,-rpath -Wl,/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/libiptc/.libs ./.libs/libip4tc.so ./.libs/libip6tc.so  -g -O2 -Wl,--no-as-needed   -Wl,-soname -Wl,libiptc.so.0 -o .libs/libiptc.so.0.0.0
    k8s: libtool: link: (cd ".libs" && rm -f "libiptc.so.0" && ln -s "libiptc.so.0.0.0" "libiptc.so.0")
    k8s: libtool: link: (cd ".libs" && rm -f "libiptc.so" && ln -s "libiptc.so.0.0.0" "libiptc.so")
    k8s: libtool: link: ar cru .libs/libiptc.a 
    k8s: ar: 
    k8s: `u' modifier ignored since `D' is the default (see `U')
    k8s: libtool: link: ranlib .libs/libiptc.a
    k8s: libtool: link: ( cd ".libs" && rm -f "libiptc.la" && ln -s "../libiptc.la" "libiptc.la" )
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/libiptc'
    k8s: Making all in libxtables
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/libxtables'
    k8s: /bin/bash ../libtool  --tag=CC   --mode=compile gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT       -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables   -Wall -Waggregate-return -Wmissing-declarations      -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes     -Winline -pipe -g -O2 -MT libxtables_la-xtables.lo -MD -MP -MF .deps/libxtables_la-xtables.Tpo -c -o libxtables_la-xtables.lo `test -f 'xtables.c' || echo './'`xtables.c
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libxtables_la-xtables.lo -MD -MP -MF .deps/libxtables_la-xtables.Tpo -c xtables.c  -fPIC -DPIC -o .libs/libxtables_la-xtables.o
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libxtables_la-xtables.lo -MD -MP -MF .deps/libxtables_la-xtables.Tpo -c xtables.c -o libxtables_la-xtables.o >/dev/null 2>&1
    k8s: mv -f .deps/libxtables_la-xtables.Tpo .deps/libxtables_la-xtables.Plo
    k8s: /bin/bash ../libtool  --tag=CC   --mode=compile gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT       -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables   -Wall -Waggregate-return -Wmissing-declarations      -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes     -Winline -pipe -g -O2 -MT libxtables_la-xtoptions.lo -MD -MP -MF .deps/libxtables_la-xtoptions.Tpo -c -o libxtables_la-xtoptions.lo `test -f 'xtoptions.c' || echo './'`xtoptions.c
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libxtables_la-xtoptions.lo -MD -MP -MF .deps/libxtables_la-xtoptions.Tpo -c xtoptions.c  -fPIC -DPIC -o .libs/libxtables_la-xtoptions.o
    k8s: libtool: compile:  gcc -DHAVE_CONFIG_H -I. -I.. -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I../iptables -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -MT libxtables_la-xtoptions.lo -MD -MP -MF .deps/libxtables_la-xtoptions.Tpo -c xtoptions.c -o libxtables_la-xtoptions.o >/dev/null 2>&1
    k8s: mv -f .deps/libxtables_la-xtoptions.Tpo .deps/libxtables_la-xtoptions.Plo
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -version-info 12:0:0  -o libxtables.la -rpath /usr/local/lib libxtables_la-xtables.lo libxtables_la-xtoptions.lo -lm  -ldl 
    k8s: libtool: link: gcc -shared  -fPIC -DPIC  .libs/libxtables_la-xtables.o .libs/libxtables_la-xtoptions.o   -lm -ldl  -g -O2   -Wl,-soname -Wl,libxtables.so.12 -o .libs/libxtables.so.12.0.0
    k8s: libtool: link: (cd ".libs" && rm -f "libxtables.so.12" && ln -s "libxtables.so.12.0.0" "libxtables.so.12")
    k8s: libtool: link: (cd ".libs" && rm -f "libxtables.so" && ln -s "libxtables.so.12.0.0" "libxtables.so")
    k8s: libtool: link: ar cru .libs/libxtables.a  libxtables_la-xtables.o libxtables_la-xtoptions.o
    k8s: ar: 
    k8s: `u' modifier ignored since `D' is the default (see `U')
    k8s: libtool: link: ranlib .libs/libxtables.a
    k8s: libtool: link: ( cd ".libs" && rm -f "libxtables.la" && ln -s "../libxtables.la" "libxtables.la" )
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/libxtables'
    k8s: Making all in include
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/include'
    k8s: make[2]: Nothing to be done for 'all'.
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/include'
    k8s: Making all in utils
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/utils'
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include   -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2 -MT nfnl_osf.o -MD -MP -MF .deps/nfnl_osf.Tpo -c -o nfnl_osf.o nfnl_osf.c
    k8s: nfnl_osf.c: In function ‘osf_load_line’:
    k8s: nfnl_osf.c:387:2: warning: ‘nfnl_talk’ is deprecated [-Wdeprecated-declarations]
    k8s:   return nfnl_talk(nfnlh, nmh, 0, 0, NULL, NULL, NULL);
    k8s:   ^~~~~~
    k8s: In file included from nfnl_osf.c:45:0:
    k8s: /usr/include/libnfnetlink/libnfnetlink.h:94:1: note: declared here
    k8s:  nfnl_talk(struct nfnl_handle *, struct nlmsghdr *, pid_t,
    k8s:  ^~~~~~~~~
    k8s: mv -f .deps/nfnl_osf.Tpo .deps/nfnl_osf.Po
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -g -O2   -o nfnl_osf nfnl_osf.o -lnfnetlink 
    k8s: libtool: link: gcc -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -g -O2 -o nfnl_osf nfnl_osf.o  -lnfnetlink
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/utils'
    k8s: Making all in extensions
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/extensions'
    k8s:   GEN      initext.c
    k8s:   CC       initext.o
    k8s:   CC       libxt_AUDIT.o
    k8s:   CC       libxt_CHECKSUM.o
    k8s:   CC       libxt_CLASSIFY.o
    k8s:   CC       libxt_CONNMARK.o
    k8s:   CC       libxt_CONNSECMARK.o
    k8s:   CC       libxt_CT.o
    k8s:   CC       libxt_DSCP.o
    k8s:   CC       libxt_HMARK.o
    k8s:   CC       libxt_IDLETIMER.o
    k8s:   CC       libxt_LED.o
    k8s:   CC       libxt_MARK.o
    k8s:   CC       libxt_NFLOG.o
    k8s:   CC       libxt_NFQUEUE.o
    k8s:   CC       libxt_RATEEST.o
    k8s:   CC       libxt_SECMARK.o
    k8s:   CC       libxt_SET.o
    k8s:   CC       libxt_SYNPROXY.o
    k8s:   CC       libxt_TCPMSS.o
    k8s:   CC       libxt_TCPOPTSTRIP.o
    k8s:   CC       libxt_TEE.o
    k8s:   CC       libxt_TOS.o
    k8s:   CC       libxt_TPROXY.o
    k8s:   CC       libxt_TRACE.o
    k8s:   CC       libxt_addrtype.o
    k8s:   CC       libxt_bpf.o
    k8s:   CC       libxt_cgroup.o
    k8s:   CC       libxt_cluster.o
    k8s:   CC       libxt_comment.o
    k8s: libxt_comment.c: In function ‘comment_xlate’:
    k8s: libxt_comment.c:59:46: warning: ‘%s’ directive output may be truncated writing up to 255 bytes into a region of size 254 [-Wformat-truncation=]
    k8s:    snprintf(comment, XT_MAX_COMMENT_LEN, "\\\"%s\\\"",
    k8s:                                               ^~
    k8s: In file included from /usr/include/stdio.h:862:0,
    k8s:                  from libxt_comment.c:9:
    k8s: /usr/include/x86_64-linux-gnu/bits/stdio2.h:64:10: note: ‘__builtin___snprintf_chk’ output between 5 and 260 bytes into a destination of size 256
    k8s:    return __builtin___snprintf_chk (__s, __n, __USE_FORTIFY_LEVEL - 1,
    k8s:           ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    k8s:         __bos (__s), __fmt, __va_arg_pack ());
    k8s:         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    k8s: libxt_comment.c:62:46: warning: ‘"’ directive output may be truncated writing 1 byte into a region of size between 0 and 255 [-Wformat-truncation=]
    k8s:    snprintf(comment, XT_MAX_COMMENT_LEN, "\"%s\"",
    k8s:                                               ^~
    k8s: In file included from /usr/include/stdio.h:862:0,
    k8s:                  from libxt_comment.c:9:
    k8s: /usr/include/x86_64-linux-gnu/bits/stdio2.h:64:10: note: ‘__builtin___snprintf_chk’ output between 3 and 258 bytes into a destination of size 256
    k8s:    return __builtin___snprintf_chk (__s, __n, __USE_FORTIFY_LEVEL - 1,
    k8s:           ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    k8s:         __bos (__s), __fmt, __va_arg_pack ());
    k8s:         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    k8s:   CC       libxt_connbytes.o
    k8s:   CC       libxt_connlimit.o
    k8s:   CC       libxt_connmark.o
    k8s:   CC       libxt_conntrack.o
    k8s:   CC       libxt_cpu.o
    k8s:   CC       libxt_dccp.o
    k8s:   CC       libxt_devgroup.o
    k8s:   CC       libxt_dscp.o
    k8s:   CC       libxt_ecn.o
    k8s:   CC       libxt_esp.o
    k8s:   CC       libxt_hashlimit.o
    k8s: In file included from /usr/include/x86_64-linux-gnu/bits/libc-header-start.h:33:0,
    k8s:                  from /usr/include/math.h:27,
    k8s:                  from libxt_hashlimit.c:15:
    k8s: /usr/include/features.h:184:3: warning: #warning "_BSD_SOURCE and _SVID_SOURCE are deprecated, use _DEFAULT_SOURCE" [-Wcpp]
    k8s:  # warning "_BSD_SOURCE and _SVID_SOURCE are deprecated, use _DEFAULT_SOURCE"
    k8s:    ^~~~~~~
    k8s:   CC       libxt_helper.o
    k8s:   CC       libxt_hwchiu.o
    k8s:   CC       libxt_ipcomp.o
    k8s:   CC       libxt_iprange.o
    k8s:   CC       libxt_ipvs.o
    k8s:   CC       libxt_length.o
    k8s:   CC       libxt_limit.o
    k8s: In file included from /usr/include/x86_64-linux-gnu/bits/libc-header-start.h:33:0,
    k8s:                  from /usr/include/math.h:27,
    k8s:                  from libxt_limit.c:8:
    k8s: /usr/include/features.h:184:3: warning: #warning "_BSD_SOURCE and _SVID_SOURCE are deprecated, use _DEFAULT_SOURCE" [-Wcpp]
    k8s:  # warning "_BSD_SOURCE and _SVID_SOURCE are deprecated, use _DEFAULT_SOURCE"
    k8s:    ^~~~~~~
    k8s:   CC       libxt_mac.o
    k8s:   CC       libxt_mangle.o
    k8s:   CC       libxt_mark.o
    k8s:   CC       libxt_multiport.o
    k8s:   CC       libxt_nfacct.o
    k8s:   CC       libxt_osf.o
    k8s:   CC       libxt_owner.o
    k8s:   CC       libxt_physdev.o
    k8s:   CC       libxt_pkttype.o
    k8s:   CC       libxt_policy.o
    k8s:   CC       libxt_quota.o
    k8s:   CC       libxt_rateest.o
    k8s:   CC       libxt_recent.o
    k8s:   CC       libxt_rpfilter.o
    k8s:   CC       libxt_sctp.o
    k8s:   CC       libxt_set.o
    k8s:   CC       libxt_socket.o
    k8s:   CC       libxt_standard.o
    k8s:   CC       libxt_statistic.o
    k8s:   CC       libxt_string.o
    k8s:   CC       libxt_tcp.o
    k8s:   CC       libxt_tcpmss.o
    k8s:   CC       libxt_time.o
    k8s:   CC       libxt_tos.o
    k8s:   CC       libxt_u32.o
    k8s:   CC       libxt_udp.o
    k8s:   AR       libext.a
    k8s:   GEN      initext4.c
    k8s:   CC       initext4.o
    k8s:   CC       libipt_CLUSTERIP.o
    k8s:   CC       libipt_DNAT.o
    k8s:   CC       libipt_ECN.o
    k8s:   CC       libipt_LOG.o
    k8s:   CC       libipt_MASQUERADE.o
    k8s:   CC       libipt_NETMAP.o
    k8s:   CC       libipt_REDIRECT.o
    k8s:   CC       libipt_REJECT.o
    k8s:   CC       libipt_SNAT.o
    k8s:   CC       libipt_TTL.o
    k8s:   CC       libipt_ULOG.o
    k8s:   CC       libipt_ah.o
    k8s:   CC       libipt_icmp.o
    k8s:   CC       libipt_realm.o
    k8s:   CC       libipt_ttl.o
    k8s:   AR       libext4.a
    k8s:   GEN      initext6.c
    k8s:   CC       initext6.o
    k8s:   CC       libip6t_DNAT.o
    k8s:   CC       libip6t_DNPT.o
    k8s:   CC       libip6t_HL.o
    k8s:   CC       libip6t_LOG.o
    k8s:   CC       libip6t_MASQUERADE.o
    k8s:   CC       libip6t_NETMAP.o
    k8s:   CC       libip6t_REDIRECT.o
    k8s:   CC       libip6t_REJECT.o
    k8s:   CC       libip6t_SNAT.o
    k8s:   CC       libip6t_SNPT.o
    k8s:   CC       libip6t_ah.o
    k8s:   CC       libip6t_dst.o
    k8s:   CC       libip6t_eui64.o
    k8s:   CC       libip6t_frag.o
    k8s:   CC       libip6t_hbh.o
    k8s:   CC       libip6t_hl.o
    k8s:   CC       libip6t_icmp6.o
    k8s:   CC       libip6t_ipv6header.o
    k8s:   CC       libip6t_mh.o
    k8s:   CC       libip6t_rt.o
    k8s:   AR       libext6.a
    k8s:   GEN      initextb.c
    k8s:   CC       initextb.o
    k8s:   CC       libebt_802_3.o
    k8s:   CC       libebt_ip.o
    k8s:   CC       libebt_log.o
    k8s:   CC       libebt_mark_m.o
    k8s:   AR       libext_ebt.a
    k8s:   GEN      initexta.c
    k8s:   CC       initexta.o
    k8s:   AR       libext_arpt.a
    k8s:   GEN      matches.man
    k8s: -e     + ./libxt_addrtype.man
    k8s: -e     + ./libip6t_ah.man
    k8s: -e     + ./libipt_ah.man
    k8s: -e     + ./libxt_bpf.man
    k8s: -e     + ./libxt_cgroup.man
    k8s: -e     + ./libxt_cluster.man
    k8s: -e     + ./libxt_comment.man
    k8s: -e     + ./libxt_connbytes.man
    k8s: -e     + ./libxt_connlimit.man
    k8s: -e     + ./libxt_connmark.man
    k8s: -e     + ./libxt_conntrack.man
    k8s: -e     + ./libxt_cpu.man
    k8s: -e     + ./libxt_dccp.man
    k8s: -e     + ./libxt_devgroup.man
    k8s: -e     + ./libxt_dscp.man
    k8s: -e     + ./libip6t_dst.man
    k8s: -e     + ./libxt_ecn.man
    k8s: -e     + ./libxt_esp.man
    k8s: -e     + ./libip6t_eui64.man
    k8s: -e     + ./libip6t_frag.man
    k8s: -e     + ./libxt_hashlimit.man
    k8s: -e     + ./libip6t_hbh.man
    k8s: -e     + ./libxt_helper.man
    k8s: -e     + ./libip6t_hl.man
    k8s: -e     + ./libipt_icmp.man
    k8s: -e     + ./libip6t_icmp6.man
    k8s: -e     + ./libxt_iprange.man
    k8s: -e     + ./libip6t_ipv6header.man
    k8s: -e     + ./libxt_ipvs.man
    k8s: -e     + ./libxt_length.man
    k8s: -e     + ./libxt_limit.man
    k8s: -e     + ./libxt_mac.man
    k8s: -e     + ./libxt_mark.man
    k8s: -e     + ./libip6t_mh.man
    k8s: -e     + ./libxt_multiport.man
    k8s: -e     + ./libxt_nfacct.man
    k8s: -e     + ./libxt_osf.man
    k8s: -e     + ./libxt_owner.man
    k8s: -e     + ./libxt_physdev.man
    k8s: -e     + ./libxt_pkttype.man
    k8s: -e     + ./libxt_policy.man
    k8s: -e     + ./libxt_quota.man
    k8s: -e     + ./libxt_rateest.man
    k8s: -e     + ./libipt_realm.man
    k8s: -e     + ./libxt_recent.man
    k8s: -e     + ./libxt_rpfilter.man
    k8s: -e     + ./libip6t_rt.man
    k8s: -e     + ./libxt_sctp.man
    k8s: -e     + ./libxt_set.man
    k8s: -e     + ./libxt_socket.man
    k8s: -e     + ./libxt_state.man
    k8s: -e     + ./libxt_statistic.man
    k8s: -e     + ./libxt_string.man
    k8s: -e     + ./libxt_tcp.man
    k8s: -e     + ./libxt_tcpmss.man
    k8s: -e     + ./libxt_time.man
    k8s: -e     + ./libxt_tos.man
    k8s: -e     + ./libipt_ttl.man
    k8s: -e     + ./libxt_u32.man
    k8s: -e     + ./libxt_udp.man
    k8s:   GEN      targets.man
    k8s: -e     + ./libxt_AUDIT.man
    k8s: -e     + ./libxt_CHECKSUM.man
    k8s: -e     + ./libxt_CLASSIFY.man
    k8s: -e     + ./libipt_CLUSTERIP.man
    k8s: -e     + ./libxt_CONNMARK.man
    k8s: -e     + ./libxt_CONNSECMARK.man
    k8s: -e     + ./libxt_CT.man
    k8s: -e     + ./libxt_DNAT.man
    k8s: -e     + ./libip6t_DNPT.man
    k8s: -e     + ./libxt_DSCP.man
    k8s: -e     + ./libipt_ECN.man
    k8s: -e     + ./libip6t_HL.man
    k8s: -e     + ./libxt_HMARK.man
    k8s: -e     + ./libxt_IDLETIMER.man
    k8s: -e     + ./libxt_LED.man
    k8s: -e     + ./libxt_LOG.man
    k8s: -e     + ./libxt_MARK.man
    k8s: -e     + ./libxt_MASQUERADE.man
    k8s: -e     + ./libxt_NETMAP.man
    k8s: -e     + ./libxt_NFLOG.man
    k8s: -e     + ./libxt_NFQUEUE.man
    k8s: -e     + ./libxt_NOTRACK.man
    k8s: -e     + ./libxt_RATEEST.man
    k8s: -e     + ./libxt_REDIRECT.man
    k8s: -e     + ./libip6t_REJECT.man
    k8s: -e     + ./libipt_REJECT.man
    k8s: -e     + ./libxt_SECMARK.man
    k8s: -e     + ./libxt_SET.man
    k8s: -e     + ./libxt_SNAT.man
    k8s: -e     + ./libip6t_SNPT.man
    k8s: -e     + ./libxt_SYNPROXY.man
    k8s: -e     + ./libxt_TCPMSS.man
    k8s: -e     + ./libxt_TCPOPTSTRIP.man
    k8s: -e     + ./libxt_TEE.man
    k8s: -e     + ./libxt_TOS.man
    k8s: -e     + ./libxt_TPROXY.man
    k8s: -e     + ./libxt_TRACE.man
    k8s: -e     + ./libipt_TTL.man
    k8s: -e     + ./libipt_ULOG.man
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/extensions'
    k8s: Making all in iptables
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/iptables'
    k8s: make  all-am
    k8s: make[3]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/iptables'
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-xtables-multi.o -MD -MP -MF .deps/xtables_multi-xtables-multi.Tpo -c -o xtables_multi-xtables-multi.o `test -f 'xtables-multi.c' || echo './'`xtables-multi.c
    k8s: mv -f .deps/xtables_multi-xtables-multi.Tpo .deps/xtables_multi-xtables-multi.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-iptables-xml.o -MD -MP -MF .deps/xtables_multi-iptables-xml.Tpo -c -o xtables_multi-iptables-xml.o `test -f 'iptables-xml.c' || echo './'`iptables-xml.c
    k8s: mv -f .deps/xtables_multi-iptables-xml.Tpo .deps/xtables_multi-iptables-xml.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-iptables-save.o -MD -MP -MF .deps/xtables_multi-iptables-save.Tpo -c -o xtables_multi-iptables-save.o `test -f 'iptables-save.c' || echo './'`iptables-save.c
    k8s: mv -f .deps/xtables_multi-iptables-save.Tpo .deps/xtables_multi-iptables-save.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-iptables-restore.o -MD -MP -MF .deps/xtables_multi-iptables-restore.Tpo -c -o xtables_multi-iptables-restore.o `test -f 'iptables-restore.c' || echo './'`iptables-restore.c
    k8s: mv -f .deps/xtables_multi-iptables-restore.Tpo .deps/xtables_multi-iptables-restore.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-iptables-standalone.o -MD -MP -MF .deps/xtables_multi-iptables-standalone.Tpo -c -o xtables_multi-iptables-standalone.o `test -f 'iptables-standalone.c' || echo './'`iptables-standalone.c
    k8s: mv -f .deps/xtables_multi-iptables-standalone.Tpo .deps/xtables_multi-iptables-standalone.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-iptables.o -MD -MP -MF .deps/xtables_multi-iptables.Tpo -c -o xtables_multi-iptables.o `test -f 'iptables.c' || echo './'`iptables.c
    k8s: mv -f .deps/xtables_multi-iptables.Tpo .deps/xtables_multi-iptables.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-ip6tables-save.o -MD -MP -MF .deps/xtables_multi-ip6tables-save.Tpo -c -o xtables_multi-ip6tables-save.o `test -f 'ip6tables-save.c' || echo './'`ip6tables-save.c
    k8s: mv -f .deps/xtables_multi-ip6tables-save.Tpo .deps/xtables_multi-ip6tables-save.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-ip6tables-restore.o -MD -MP -MF .deps/xtables_multi-ip6tables-restore.Tpo -c -o xtables_multi-ip6tables-restore.o `test -f 'ip6tables-restore.c' || echo './'`ip6tables-restore.c
    k8s: mv -f .deps/xtables_multi-ip6tables-restore.Tpo .deps/xtables_multi-ip6tables-restore.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-ip6tables-standalone.o -MD -MP -MF .deps/xtables_multi-ip6tables-standalone.Tpo -c -o xtables_multi-ip6tables-standalone.o `test -f 'ip6tables-standalone.c' || echo './'`ip6tables-standalone.c
    k8s: mv -f .deps/xtables_multi-ip6tables-standalone.Tpo .deps/xtables_multi-ip6tables-standalone.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-ip6tables.o -MD -MP -MF .deps/xtables_multi-ip6tables.Tpo -c -o xtables_multi-ip6tables.o `test -f 'ip6tables.c' || echo './'`ip6tables.c
    k8s: mv -f .deps/xtables_multi-ip6tables.Tpo .deps/xtables_multi-ip6tables.Po
    k8s: gcc -DHAVE_CONFIG_H -I. -I..  -D_LARGEFILE_SOURCE=1 -D_LARGE_FILES -D_FILE_OFFSET_BITS=64 -D_REENTRANT         -DXTABLES_LIBDIR=\"/usr/local/lib/xtables\" -DXTABLES_INTERNAL -I../include -I../include -I..      -Wall -Waggregate-return -Wmissing-declarations    -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -MT xtables_multi-xshared.o -MD -MP -MF .deps/xtables_multi-xshared.Tpo -c -o xtables_multi-xshared.o `test -f 'xshared.c' || echo './'`xshared.c
    k8s: mv -f .deps/xtables_multi-xshared.Tpo .deps/xtables_multi-xshared.Po
    k8s: /bin/bash ../libtool  --tag=CC   --mode=link gcc -Wall -Waggregate-return -Wmissing-declarations       -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes   -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2   -o xtables-multi xtables_multi-xtables-multi.o xtables_multi-iptables-xml.o xtables_multi-iptables-save.o xtables_multi-iptables-restore.o xtables_multi-iptables-standalone.o xtables_multi-iptables.o xtables_multi-ip6tables-save.o xtables_multi-ip6tables-restore.o xtables_multi-ip6tables-standalone.o xtables_multi-ip6tables.o xtables_multi-xshared.o ../extensions/libext.a ../libiptc/libip4tc.la ../extensions/libext4.a ../libiptc/libip6tc.la ../extensions/libext6.a ../libxtables/libxtables.la -lm 
    k8s: libtool: link: gcc -Wall -Waggregate-return -Wmissing-declarations -Wmissing-prototypes -Wredundant-decls -Wshadow -Wstrict-prototypes -Winline -pipe -DALL_INCLUSIVE -DENABLE_IPV4 -DENABLE_IPV6 -g -O2 -o .libs/xtables-multi xtables_multi-xtables-multi.o xtables_multi-iptables-xml.o xtables_multi-iptables-save.o xtables_multi-iptables-restore.o xtables_multi-iptables-standalone.o xtables_multi-iptables.o xtables_multi-ip6tables-save.o xtables_multi-ip6tables-restore.o xtables_multi-ip6tables-standalone.o xtables_multi-ip6tables.o xtables_multi-xshared.o  ../extensions/libext.a ../libiptc/.libs/libip4tc.so ../extensions/libext4.a ../libiptc/.libs/libip6tc.so ../extensions/libext6.a ../libxtables/.libs/libxtables.so -lm
    k8s: sed \
    k8s:        -e '/@MATCH@/ r ../extensions/matches.man' \
    k8s:        -e '/@TARGET@/ r ../extensions/targets.man' iptables-extensions.8.tmpl >iptables-extensions.8;
    k8s: make[3]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/iptables'
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables/iptables'
    k8s: make[2]: Entering directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables'
    k8s: make[2]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables'
    k8s: make[1]: Leaving directory '/home/vagrant/network-study/iptables/k8s/module/custom/user/iptables'
    k8s: ++ cd /home/vagrant/network-study/iptables/k8s/module/custom/kernel
    k8s: ++ sudo make
    k8s: make -C /lib/modules/4.15.0-72-generic/build M=/home/vagrant/network-study/iptables/k8s/module/custom/kernel modules
    k8s: make[1]: Entering directory '/usr/src/linux-headers-4.15.0-72-generic'
    k8s:   CC [M]  /home/vagrant/network-study/iptables/k8s/module/custom/kernel/xt_hwchiu.o
    k8s:   Building modules, stage 2.
    k8s:   MODPOST 1 modules
    k8s:   CC      /home/vagrant/network-study/iptables/k8s/module/custom/kernel/xt_hwchiu.mod.o
    k8s:   LD [M]  /home/vagrant/network-study/iptables/k8s/module/custom/kernel/xt_hwchiu.ko
    k8s: make[1]: Leaving directory '/usr/src/linux-headers-4.15.0-72-generic'
    k8s: ++ sudo docker run -d --name debug hwchiu/netutils
    k8s: Unable to find image 'hwchiu/netutils:latest' locally
    k8s: latest: Pulling from hwchiu/netutils
    k8s: 8ee29e426c26: Pulling fs layer
    k8s: 6e83b260b73b: Pulling fs layer
    k8s: e26b65fd1143: Pulling fs layer
    k8s: 40dca07f8222: Pulling fs layer
    k8s: b420ae9e10b3: Pulling fs layer
    k8s: 1cb64f3c9d5a: Pulling fs layer
    k8s: cecb6c199cf6: Pulling fs layer
    k8s: 40dca07f8222: Waiting
    k8s: b420ae9e10b3: Waiting
    k8s: 1cb64f3c9d5a: Waiting
    k8s: cecb6c199cf6: Waiting
    k8s: 6e83b260b73b: Verifying Checksum
    k8s: 6e83b260b73b: Download complete
    k8s: e26b65fd1143: Verifying Checksum
    k8s: e26b65fd1143: Download complete
    k8s: 40dca07f8222: Verifying Checksum
    k8s: 40dca07f8222: Download complete
    k8s: b420ae9e10b3: Verifying Checksum
    k8s: b420ae9e10b3: Download complete
    k8s: 8ee29e426c26: Verifying Checksum
    k8s: 8ee29e426c26: Download complete
    k8s: cecb6c199cf6: Verifying Checksum
    k8s: cecb6c199cf6: Download complete
    k8s: 1cb64f3c9d5a: Verifying Checksum
    k8s: 1cb64f3c9d5a: Download complete
    k8s: 8ee29e426c26: Pull complete
    k8s: 6e83b260b73b: Pull complete
    k8s: e26b65fd1143: Pull complete
    k8s: 40dca07f8222: Pull complete
    k8s: b420ae9e10b3: Pull complete
    k8s: 1cb64f3c9d5a: Pull complete
    k8s: cecb6c199cf6: Pull complete
    k8s: Digest: sha256:f1a3643b8b10c98b4aa9e4ac8269b7587c1d9f415f134ff359f920b8539a6f76
    k8s: Status: Downloaded newer image for hwchiu/netutils:latest
    k8s: 41baad8d5cad9bdb73f8a463ff74a06a64962c717b563c153fdda51518a2c041
    k8s: ++ export KUBE_VERSION=1.17.0
    k8s: ++ KUBE_VERSION=1.17.0
    k8s: ++ export NET_IF_NAME=enp0s8
    k8s: ++ NET_IF_NAME=enp0s8
    k8s: ++ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg
    k8s: ++ sudo apt-key add -
    k8s: Warning: apt-key output should not be parsed (stdout is not a terminal)
    k8s: OK
    k8s: ++ echo 'deb http://apt.kubernetes.io/ kubernetes-xenial main'
    k8s: ++ sudo tee --append /etc/apt/sources.list.d/kubernetes.list
    k8s: deb http://apt.kubernetes.io/ kubernetes-xenial main
    k8s: ++ sudo apt-get update
    k8s: Hit:1 https://download.docker.com/linux/ubuntu bionic InRelease
    k8s: Hit:3 http://security.ubuntu.com/ubuntu bionic-security InRelease
    k8s: Hit:4 http://archive.ubuntu.com/ubuntu bionic InRelease
    k8s: Hit:5 http://archive.ubuntu.com/ubuntu bionic-updates InRelease
    k8s: Get:2 https://packages.cloud.google.com/apt kubernetes-xenial InRelease [8,993 B]
    k8s: Hit:6 http://archive.ubuntu.com/ubuntu bionic-backports InRelease
    k8s: Get:7 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 Packages [35.3 kB]
    k8s: Fetched 44.3 kB in 1s (33.3 kB/s)
    k8s: Reading package lists...
    k8s: ++ sudo apt-get install -y kubeadm=1.17.0-00 kubelet=1.17.0-00 kubectl=1.17.0-00 kubernetes-cni=0.7.5-00
    k8s: Reading package lists...
    k8s: Building dependency tree...
    k8s: 
    k8s: Reading state information...
    k8s: The following additional packages will be installed:
    k8s:   conntrack cri-tools socat
    k8s: The following NEW packages will be installed:
    k8s:   conntrack cri-tools kubeadm kubectl kubelet kubernetes-cni socat
    k8s: 0 upgraded, 7 newly installed, 0 to remove and 92 not upgraded.
    k8s: Need to get 51.6 MB of archives.
    k8s: After this operation, 272 MB of additional disk space will be used.
    k8s: Get:1 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 cri-tools amd64 1.13.0-00 [8,776 kB]
    k8s: Get:4 http://archive.ubuntu.com/ubuntu bionic/main amd64 conntrack amd64 1:1.4.4+snapshot20161117-6ubuntu2 [30.6 kB]
    k8s: Get:2 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubernetes-cni amd64 0.7.5-00 [6,473 kB]
    k8s: Get:7 http://archive.ubuntu.com/ubuntu bionic/main amd64 socat amd64 1.7.3.2-2ubuntu2 [342 kB]
    k8s: Get:3 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubelet amd64 1.17.0-00 [19.2 MB]
    k8s: Get:5 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubectl amd64 1.17.0-00 [8,742 kB]
    k8s: Get:6 https://packages.cloud.google.com/apt kubernetes-xenial/main amd64 kubeadm amd64 1.17.0-00 [8,059 kB]
    k8s: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    k8s: Fetched 51.6 MB in 9s (5,705 kB/s)
    k8s: Selecting previously unselected package conntrack.
    k8s: (Reading database ... 
(Reading database ... 60%e ... 5%
    k8s: (Reading database ... 65%
    k8s: (Reading database ... 70%
    k8s: (Reading database ... 75%
    k8s: (Reading database ... 80%
    k8s: (Reading database ... 85%
    k8s: (Reading database ... 90%
    k8s: (Reading database ... 95%
(Reading database ... 77830 files and directories currently installed.)
    k8s: Preparing to unpack .../0-conntrack_1%3a1.4.4+snapshot20161117-6ubuntu2_amd64.deb ...
    k8s: Unpacking conntrack (1:1.4.4+snapshot20161117-6ubuntu2) ...
    k8s: Selecting previously unselected package cri-tools.
    k8s: Preparing to unpack .../1-cri-tools_1.13.0-00_amd64.deb ...
    k8s: Unpacking cri-tools (1.13.0-00) ...
    k8s: Selecting previously unselected package kubernetes-cni.
    k8s: Preparing to unpack .../2-kubernetes-cni_0.7.5-00_amd64.deb ...
    k8s: Unpacking kubernetes-cni (0.7.5-00) ...
    k8s: Selecting previously unselected package socat.
    k8s: Preparing to unpack .../3-socat_1.7.3.2-2ubuntu2_amd64.deb ...
    k8s: Unpacking socat (1.7.3.2-2ubuntu2) ...
    k8s: Selecting previously unselected package kubelet.
    k8s: Preparing to unpack .../4-kubelet_1.17.0-00_amd64.deb ...
    k8s: Unpacking kubelet (1.17.0-00) ...
    k8s: Selecting previously unselected package kubectl.
    k8s: Preparing to unpack .../5-kubectl_1.17.0-00_amd64.deb ...
    k8s: Unpacking kubectl (1.17.0-00) ...
    k8s: Selecting previously unselected package kubeadm.
    k8s: Preparing to unpack .../6-kubeadm_1.17.0-00_amd64.deb ...
    k8s: Unpacking kubeadm (1.17.0-00) ...
    k8s: Setting up conntrack (1:1.4.4+snapshot20161117-6ubuntu2) ...
    k8s: Setting up kubernetes-cni (0.7.5-00) ...
    k8s: Setting up cri-tools (1.13.0-00) ...
    k8s: Setting up socat (1.7.3.2-2ubuntu2) ...
    k8s: Setting up kubelet (1.17.0-00) ...
    k8s: Created symlink /etc/systemd/system/multi-user.target.wants/kubelet.service → /lib/systemd/system/kubelet.service.
    k8s: Setting up kubectl (1.17.0-00) ...
    k8s: Setting up kubeadm (1.17.0-00) ...
    k8s: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    k8s: ++ sudo swapoff -a
    k8s: ++ sudo sysctl -w vm.swappiness=0
    k8s: vm.swappiness = 0
    k8s: ++ sudo sed /vagrant--vg-swap/d -i /etc/fstab
    k8s: ++ sudo kubeadm init --kubernetes-version v1.17.0 --apiserver-advertise-address=172.17.8.111 --pod-network-cidr=10.244.0.0/16
    k8s: W0506 06:49:35.632701   25037 validation.go:28] Cannot validate kubelet config - no validator is available
    k8s: W0506 06:49:35.632831   25037 validation.go:28] Cannot validate kube-proxy config - no validator is available
    k8s: [init] Using Kubernetes version: v1.17.0
    k8s: [preflight] Running pre-flight checks
    k8s:        [WARNING IsDockerSystemdCheck]: detected "cgroupfs" as the Docker cgroup driver. The recommended driver is "systemd". Please follow the guide at https://kubernetes.io/docs/setup/cri/
    k8s: [preflight] Pulling images required for setting up a Kubernetes cluster
    k8s: [preflight] This might take a minute or two, depending on the speed of your internet connection
    k8s: [preflight] You can also perform this action in beforehand using 'kubeadm config images pull'
    k8s: [kubelet-start] Writing kubelet environment file with flags to file "/var/lib/kubelet/kubeadm-flags.env"
    k8s: [kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
    k8s: [kubelet-start] Starting the kubelet
    k8s: [certs] Using certificateDir folder "/etc/kubernetes/pki"
    k8s: [certs] Generating "ca" certificate and key
    k8s: [certs] Generating "apiserver" certificate and key
    k8s: [certs] apiserver serving cert is signed for DNS names [k8s-dev kubernetes kubernetes.default kubernetes.default.svc kubernetes.default.svc.cluster.local] and IPs [10.96.0.1 172.17.8.111]
    k8s: [certs] Generating "apiserver-kubelet-client" certificate and key
    k8s: [certs] Generating "front-proxy-ca" certificate and key
    k8s: [certs] Generating "front-proxy-client" certificate and key
    k8s: [certs] Generating "etcd/ca" certificate and key
    k8s: [certs] Generating "etcd/server" certificate and key
    k8s: [certs] etcd/server serving cert is signed for DNS names [k8s-dev localhost] and IPs [172.17.8.111 127.0.0.1 ::1]
    k8s: [certs] Generating "etcd/peer" certificate and key
    k8s: [certs] etcd/peer serving cert is signed for DNS names [k8s-dev localhost] and IPs [172.17.8.111 127.0.0.1 ::1]
    k8s: [certs] Generating "etcd/healthcheck-client" certificate and key
    k8s: [certs] Generating "apiserver-etcd-client" certificate and key
    k8s: [certs] Generating "sa" key and public key
    k8s: [kubeconfig] Using kubeconfig folder "/etc/kubernetes"
    k8s: [kubeconfig] Writing "admin.conf" kubeconfig file
    k8s: [kubeconfig] Writing "kubelet.conf" kubeconfig file
    k8s: [kubeconfig] Writing "controller-manager.conf" kubeconfig file
    k8s: [kubeconfig] Writing "scheduler.conf" kubeconfig file
    k8s: [control-plane] Using manifest folder "/etc/kubernetes/manifests"
    k8s: [control-plane] Creating static Pod manifest for "kube-apiserver"
    k8s: [control-plane] Creating static Pod manifest for "kube-controller-manager"
    k8s: W0506 06:50:10.781810   25037 manifests.go:214] the default kube-apiserver authorization-mode is "Node,RBAC"; using "Node,RBAC"
    k8s: [control-plane] Creating static Pod manifest for "kube-scheduler"
    k8s: W0506 06:50:10.783037   25037 manifests.go:214] the default kube-apiserver authorization-mode is "Node,RBAC"; using "Node,RBAC"
    k8s: [etcd] Creating static Pod manifest for local etcd in "/etc/kubernetes/manifests"
    k8s: [wait-control-plane] Waiting for the kubelet to boot up the control plane as static Pods from directory "/etc/kubernetes/manifests". This can take up to 4m0s
    k8s: [apiclient] All control plane components are healthy after 20.003072 seconds
    k8s: [upload-config] Storing the configuration used in ConfigMap "kubeadm-config" in the "kube-system" Namespace
    k8s: [kubelet] Creating a ConfigMap "kubelet-config-1.17" in namespace kube-system with the configuration for the kubelets in the cluster
    k8s: [upload-certs] Skipping phase. Please see --upload-certs
    k8s: [mark-control-plane] Marking the node k8s-dev as control-plane by adding the label "node-role.kubernetes.io/master=''"
    k8s: [mark-control-plane] Marking the node k8s-dev as control-plane by adding the taints [node-role.kubernetes.io/master:NoSchedule]
    k8s: [bootstrap-token] Using token: hnul3j.54q0y82oxnq544gg
    k8s: [bootstrap-token] Configuring bootstrap tokens, cluster-info ConfigMap, RBAC Roles
    k8s: [bootstrap-token] configured RBAC rules to allow Node Bootstrap tokens to post CSRs in order for nodes to get long term certificate credentials
    k8s: [bootstrap-token] configured RBAC rules to allow the csrapprover controller automatically approve CSRs from a Node Bootstrap Token
    k8s: [bootstrap-token] configured RBAC rules to allow certificate rotation for all node client certificates in the cluster
    k8s: [bootstrap-token] Creating the "cluster-info" ConfigMap in the "kube-public" namespace
    k8s: [kubelet-finalize] Updating "/etc/kubernetes/kubelet.conf" to point to a rotatable kubelet client certificate and key
    k8s: [addons] Applied essential addon: CoreDNS
    k8s: [addons] Applied essential addon: kube-proxy
    k8s: 
    k8s: Your Kubernetes control-plane has initialized successfully!
    k8s: 
    k8s: To start using your cluster, you need to run the following as a regular user:
    k8s: 
    k8s:   mkdir -p $HOME/.kube
    k8s:   sudo cp -i 
    k8s: /etc/kubernetes/admin.conf
    k8s:  $HOME/.kube/config
    k8s:   sudo chown $(id -u):$(id -g) $HOME/.kube/config
    k8s: 
    k8s: You should now deploy a pod network to the cluster.
    k8s: Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
    k8s:   https://kubernetes.io/docs/concepts/cluster-administration/addons/
    k8s: Then you can join any number of worker nodes by running the following on each as root:
    k8s: kubeadm join 172.17.8.111:6443 --token hnul3j.54q0y82oxnq544gg \
    k8s:     --discovery-token-ca-cert-hash sha256:148d12d99981bdc7ea8090182bed76bdf1332faf420365df62d2bfc0d38408d7 
    k8s: ++ mkdir -p /home/vagrant/.kube
    k8s: ++ sudo cp -i /etc/kubernetes/admin.conf /home/vagrant/.kube/config
    k8s: +++ id -u
    k8s: +++ id -g
    k8s: ++ sudo chown 1000:1000 /home/vagrant/.kube/config
    k8s: ++ kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/2140ac876ef134e0ed5af15c65e414cf26827915/Documentation/kube-flannel.yml
    k8s: podsecuritypolicy.policy/psp.flannel.unprivileged created
    k8s: clusterrole.rbac.authorization.k8s.io/flannel created
    k8s: clusterrolebinding.rbac.authorization.k8s.io/flannel created
    k8s: serviceaccount/flannel created
    k8s: configmap/kube-flannel-cfg created
    k8s: daemonset.apps/kube-flannel-ds-amd64 created
    k8s: daemonset.apps/kube-flannel-ds-arm64 created
    k8s: daemonset.apps/kube-flannel-ds-arm created
    k8s: daemonset.apps/kube-flannel-ds-ppc64le created
    k8s: daemonset.apps/kube-flannel-ds-s390x created
    k8s: ++ kubectl taint nodes --all node-role.kubernetes.io/master-
    k8s: node/k8s-dev untainted
```