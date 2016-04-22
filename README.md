# os-installation
## Ubuntu 14.04 (trusty) amd64
### LAN内へのインストールミラー構築
複数台に展開したい・迅速に展開したい場合は，インストールミラーをローカルに構築すると良いでしょう．

```

# apt-get install apt-mirror
# vi /etc/apt/mirror.list

参照するミラーを以下の3行のみにする
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty main restricted main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty-updates main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu trusty-security main/debian-installer restricted/debian-installer multiverse/debian-installer

# apt-mirror (10GB程度のファイルをDLする)

/var/spool/apt-mirror以下の所定の場所にdists/とpool/が作成されるので，Webサーバに配置する
配置のやり方は http://jp.archive.ubuntu.com/ubuntu/ を参考にすること

```

### preseedによるインストール自動化
Ubuntuはpreseedというインストール自動化機構を持っています．preseedを利用すると，インストールに利用したミラーをインストール後も参照するため，
ローカルのミラーではパッケージが不足して問題が発生します．

そのため，インストールの最終段階で， late_command 構文を使って参照するミラーを書き換えています．この部分は配置したWebサーバ等に依存するため，
自身の環境に合わせて適宜書き換えてください．


## Ubuntu 16.04 (xenial) amd64
上のtrustyをxenialに置き換えただけで動く

### LAN内へのインストールミラー構築
複数台に展開したい・迅速に展開したい場合は，インストールミラーをローカルに構築すると良いでしょう．

```

# apt-get install apt-mirror
# vi /etc/apt/mirror.list

参照するミラーを以下の3行のみにする
deb-amd64 http://jp.archive.ubuntu.com/ubuntu xenial main restricted main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu xenial-updates main/debian-installer restricted/debian-installer multiverse/debian-installer
deb-amd64 http://jp.archive.ubuntu.com/ubuntu xenial-security main/debian-installer restricted/debian-installer multiverse/debian-installer

# apt-mirror (10GB程度のファイルをDLする)

/var/spool/apt-mirror以下の所定の場所にdists/とpool/が作成されるので，Webサーバに配置する
配置のやり方は http://jp.archive.ubuntu.com/ubuntu/ を参考にすること

```

### preseedによるインストール自動化
Ubuntuはpreseedというインストール自動化機構を持っています．preseedを利用すると，インストールに利用したミラーをインストール後も参照するため，
ローカルのミラーではパッケージが不足して問題が発生します．

そのため，インストールの最終段階で， late_command 構文を使って参照するミラーを書き換えています．この部分は配置したWebサーバ等に依存するため，
自身の環境に合わせて適宜書き換えてください．







