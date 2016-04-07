# os-installation
## Ubuntu 14.04 (trusty)
インストール用のローカルミラーを作りたい場合は，事前に別のUbuntuマシンで以下の作業を行うこと

```
# apt-get install apt-mirror
# vi /etc/apt/mirror.list

参照するミラーを以下の3行のみにする
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty main restricted main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty-updates main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty-security main/debian-installer restricted/debian-installer multiverse/debian-installer

# apt-mirror
/var/spool/apt-mirror以下にインストール用のデータが複製されるので，Webサーバに適当に配置する
```