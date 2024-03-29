# Install Graphic driver
## Install Nvidia driver on CentOS (Option for Nvidia graphic card)
1. go to nvidia site and download the driver (www.nvidia.com/object/unix.html)
   * Latest Long Lived Branch version
2. make the file executable
    ```
    $ cd ~/Downloads
    $ chmod +x NVIIDA-Linux-x86_64-3xx.run
    ```
3. change booting mode and reboot 
    ```
    $ sudo systemctl set-default multi-user.target
    ```
4. install cuda with multi-user.target
    ```
    $ sudo sh cuda_9.2.xx.run
    ```
4. install driver with multi-user.target
    ```
    $ sudo ./NVIIDA-Linux-x86_64-3xx.run
    ```
5. you can see an error message, and Nvidia will create the modprobe to make blacklist of nouveau
    * select accept
6. disable nouveau
    ```
    $ sudo mv /boot/initramfs-$(uname -r).img /boot/initramfs-$(uname -r)-nvidia.img
    $ sudo dracut /boot/initramfs-$(uname -r).img $(uname -r)
    ```
7. reboot and install driver again

## Install Nvidia driver (Ubuntu 18.04v2)
1. add ppa:graphics-drivers/ppa
    ```
    $sudo add-apt-repository ppa:graphics-drivers/ppa
    ```
2. install graphic driver
    ```
    $sudo apt install nvidia-driver-418
    ```
3. install cuda driver
 - https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal
    ```
    $sudo dpkg -i cuda-repo-ubuntu1804-10-1-local-10.1.168-418.67_1.0-1_amd64.deb
    $sudo apt-key add /var/cuda-repo-<version>/7fa2af80.pub
    $sudo apt-get update
    $sudo apt-get install cuda
    ```

# Update Repository
1. update yum 
    ```
    $ sudo yum -y update
    $ sudo yum -y install yum-utils
    ```
2. install epel repository
    ```
    $ sudo yum -y install epel-release
    ```
3. install ius repository
    ```
    $ sudo yum -y install https://centos7.iuscommunity.org/ius-release.rpm
    ```
4. update yum again
    ```
    $ sudo yum -y update
    ```
5. install default environment
    ```
    $ sudo yum groupinstall "Development Tools" "Development Libraries"
    ```
    For Ubuntu,
    ```
    $ sudo apt install build-essential
    $ sudo apt install ubuntu-restricted-extras (to intall extra media codecs)
    ```
 *** important ***
 *** after update and upgrade, do step.0 process again

# Install Cmake
0. install curl-devel zlib-devel (the cmake with Https support is needed for installing opencv) 
https://github.com/opencv/opencv_contrib/issues/1131 (check skvark's comment and ./bootstrap --system-curl. from the version of Cmake-3.12, --system-curls might be not needed for Https support)
    ```
    $ sudo yum -y install curl-devel zlib-devel
    ```
    For Ubuntu,
    ```
    $ sudo apt install libcurl4-openssl-dev zlib1g-dev
    ```
1. goto https://cmake.org, and download the latest stable install file
2. tar -zxvf cmake-xxxversionxxx.tar.gz
3. cd cmake-xxxversionxxx
4. install
    ```
    $ ./bootstrap --system-curl
    $ sudo make
    $ sudo make install
    ```

# Install Java(openjdk), and modify environment 
1. search and install openjdk
    ```
    $ yum search openjdk
    $ sudo yum install java-1.8.0-openjdk
    $ sudo yum install java-1.8.0-openjdk-devel
    ```
2. add the below to .bash_profile
    ```
    $ JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk (or /etc/alternatives/java_sdk_1.8.0_openjdk)
    $ export JAVA_HOME
    ```

# Install Maven
1. goto maven webpage(https://maven.apache.org), and download the binary install file
2. copy to /opt, and unzip the file
    ```
    $ sudo cp ~/Downloads/apache-maven-xxx.tar.gz /opt/
    $ cd opt
    $ sudo tar -zxvf apache-maven-xxx.tar.gz
    ```
3. make the link, and update environment
    ```
    $ sudo ln -s apache-maven-xxx maven
    $ vi ~/.bash_profile
    $ MAVEN_HOME=/opt/maven
    $ export PATH=$MAVEN_HOME/bin:$PATH
    ```

# Install Ant
1. goto ant webpage(https://ant.apache.org), and download the binary install file
2. copy to /opt, and unzip the file
    ```
    $ sudo cp ~/Downloads/apache-ant-xxx.tar.gz /opt/
    $ cd opt
    $ sudo tar -zxvf apahce-ant-xxx.tar.gz
    ```
    For Ubuntu,
    You can just install ant with apt on Ubuntu18.04. Check the installed path if you use apt.
    ```
    $ sudo apt install ant
    ```
3. make the link, and update environment
    ```
    $ sudo ln -s apache-ant-xxx ant
    $ vi ~/.bash_profile
    $ ANT_HOME=/opt/ant
    $ export PATH=$ANT_HOME/bin:$PATH
    ```
    
# Update Source
 * Centos: .bash_profile, Ubuntu: .profile
    ```
    $ source ~/.bash_profile
    ```

# Install Environment(Python, other libraries) to install opencv
1. upgrade and update
    ```
    $ sudo yum update
    $ sudo yum upgrade
2. install python2xx and tools
    ```
    $ sudo yum install python-devel
    $ sudo yum install python-pip
    ```
3. install python36 and tools
 * CentOS7: python36u, Ubutu18.04: python3
    ```
    $ sudo yum -y install python36
    $ sudo yum -y install python36-devel
    $ sudo yum -y install python36-pip
    ```
4. install python packages
    ```
    $ python --version (check the version of python2x)
    $ sudo pip install numpy (this is for version 2.7x)
    $ python3.6 --version (check the version of python3x)
    $ sudo pip3.6 install numpy (this is for version 3.6x)
    ```
# Install Virtual Envirionment
https://wsvincent.com/install-python3-mac/
## install virtualenv and set environment
```
$sudo apt install pip3 python3-dev (python36 for CentOS)
$pip3 install (--userId) virtualenv (check PermissionError can be occurred without 'userId')
$cd ~/
$mkdir virtualenvs
$cd virtualenvs
$source .profile (if path is not updated)
$virtualenv --python=python3.6 your_virtualenv_name
```
## run virtualenv
```
$source ./your_virtualenv_name/bin/activate
$pip3 install ...
...
$which python3
/home/your_id/virtualenvs/your_virtialenv_name/bin/python3 (important!!)
$deactivate
```

# Install OpenCV
1. install additional packages for opencv (CentOS, check the newest way)
    ```
    $ sudo yum install curl-devel zlib-devel
    $ sudo yum install gtk+-devel gtk2-devel gtk3-devel
    $ sudo yum install git pkgconfig (they might be installed)
    $ sudo yum install libpng-devel libjpeg-turbo-devel jasper-devel openexr-devel libtiff-devel libwebp-devel (to support various image format)
    $ sudo yum install libdc1394-devel libv4l-devel (for video format)
    $ sudo yum install gstreamer-dev gstreamer-plugins-base-devel gstreamer1-dev gstreamer1-plugins-base-devel 
    $ sudo yum install tbb-devel eigen3-devel
    $ sudo yum install epel-release (might be installed in the environment setting step)
    $ sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm 
    $ sudo yum install ffmpeg ffmpeg-dev (for libavcodec libavformat libavutil libswscale libavresample)

    ```
    For Ubuntu,
    ```
    $ sudo apt install git pkg-config (default for development)
    $ sudo apt install libcurl4-gnutls-dev libcurl4-openssl-dev
    $ sudo apt install libgtk-3-dev libgtk2.0-dev
    $ sudo apt install libpng-dev libjpeg-dev libjpeg-turbo8-dev libtiff-dev libwebp-dev
    $ sudo apt install libdc1394-22-dev libv4l-dev 
    $ sudo apt install libavcodec-dev libavformat-dev ***
    $ sudo apt install libxvidcore-dev libx264-dev ***
    $ sudo apt-get install gstreamer1.0-opencv libgstreamer1.0-dev 
    $ sudo apt install libtbb-dev libeigen3-dev
    $ sudo apt install ffmpeg libswscale-dev
    $ sudo apt install libavcodec-dev libavformat-dev libavutil-dev libswscale-dev libavresample-dev
    $ sudo apt install libatlas-base-dev gfortran ***
    $ sudo apt install libgoogle-glog-dev
    ```
2. set virtual envirionment for opencv
3. prepair install file
    ```
    $ mkdir opencv
    $ cd opencv
    $ git clone https://github.com/opencv/opencv_contrib.git
    $ git clone https://github.com/opencv/opencv.git
    $ mkdir build (this is <opencv_build_derectory> as the below)
    ```
3. install opencv-contrib (you can use xfeature2 with opencv_contrib version), https://github.com/opencv/opencv_contrib
    ```
    $ cd <opencv_build_directory>
    $ cmake -DOPENCV_EXTRA_MODULES_PATH=<opencv_contrib>/modules <opencv_source_directory> -DOPENCV_ENABLE_NONFREE=ON
    $ make -j5
    $ sudo make install
    ```
# How to fix locale error
Edit /etc/environment and add the following. Replace en_US with your actual locale if you are not using en_US:
```
LC_ALL="en_US.UTF-8"
LC_CTYPE="en_US.UTF-8"
LANGUAGE="en_US.UTF-8"
```

# Install Boost and Thrift
1. install additional packages for thrift
    ```
    $ sudo yum install wget autoconf automake bison (might be installed) (flex?)
    $ sudo yum install libevent-devel
    $ sudo yum install zlib-devel
    $ sudo yum install openssl-devel
    $ sudo yum install nodejs
    ```
    For Ubuntu,
    ```
    $ sudo apt install git wget autoconf automake bison
    $ sudo apt install libevent-dev zlib1g-dev libcurl4-openssl-dev
    $ sudo apt install libtool
    $ sudo apt install pkg-config curl flex
    $ sudo apt install libssl-dev
    $ sudo apt install nodejs
    ```
2. go to the boost site (http://www.boost.org), and download the install file
3. unzip the downloaed file
    ```
    $ tar -zxvf boost_1_6xx.tar.gz
    ```
4. install boost
    ```
    $ cd boost_1_6xx
    $ sudo ./bootstrap.sh
    $ sudo ./b2 install
    $ sudo ./b2 --with-test --prefix=/opt/boost install (building the unit test framework and install boost at $boost_installation_prefix)
    ```
5. install thrift
    ```
    $ git clone https://github.com/apache/thrift
    $ cd thrift
    $ ./bootstrap.sh
    $ ./configure --with-boost=/opt/boost (--without-ruby --without-lua)
    $ make
    $ sudo make install
    ```
    
    The default ruby version of CentOS is 2.0, but thrift 0.12 needs over 2.3.
    It is not easy to install ruby 2.3 with other libraries, such as bundler...
    So, I recommend --without-ruby
    If you meet bundler version problem (version down could be needed) during make, uninstall bundler and reinstall
    ```
    $ gem uninstall bundler
    $ gem install bundler --version '1.11'
    ```
