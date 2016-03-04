#Fedora 安装之后的配置
1. 安装源
rpm -Uvh http://mirrors.ustc.edu.cn/fedora/rpmfusion/free/fedora/rpmfusion-free-release-22.noarch.rpm
rpm -Uvh http://mirrors.ustc.edu.cn/fedora/rpmfusion/nonfree/fedora/rpmfusion-nonfree-release-22.noarch.rpm

2. 安装解码器
dnf install gstreamer-plugins-bad gstreamer-plugins-bad-free-extras gstreamer-plugins-ugly gstreamer-ffmpeg gstreamer1-libav gstreamer1-plugins-bad-free-extras gstreamer1-plugins-bad-freeworld gstreamer-plugins-base-tools gstreamer1-plugins-good-extras gstreamer1-plugins-ugly gstreamer1-plugins-bad-free gstreamer1-plugins-good gstreamer1-plugins-base gstreamer1

3. 安装常用软件
dnf update -y
dnf install kernel-devel kernel-headers cairo-dock mplayer smplayer vlc qbittorrent bluefish gcc gcc-c++ vim retext octave audacious gnome-tweak-tool graphviz gimp openshot blender mypaint gtk3-devel gtk3-devel-docs mariadb mariadb-server mariadb-devel glib2-doc pitivi gcc gcc-c++ boost boost-devel samba samba-client nginx httpd php


