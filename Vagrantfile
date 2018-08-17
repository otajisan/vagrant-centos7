# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  ## 仮想マシンの定義
  # ベースイメージ
  config.vm.box = "centos/7"
  # ホスト名
  config.vm.hostname = "develop"
  # IPアドレス
  config.vm.network :private_network, ip: "192.168.33.10"
  # 端末のディレクトリと仮想マシンのディレクトリの同期設定
  # オプションでファイル転送時のパーミッションを指定
  config.vm.synced_folder ".", "/home/vagrant/sync", mount_options: ['dmode=777','fmode=755']
  config.vm.provision "shell", inline: $script
end

$script = <<SCRIPT
  # epelリポジトリ
  yum -y install epel-release
  # remiリポジトリ
  rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
  # git
  yum -y install git
  # vim
  yum -y install vim
  # wget
  yum -y install wget
  # Apache
  #yum -y install httpd
  #systemctl start httpd.service
  #systemctl enable httpd.service
  #firewalld
  #systemctl start firewalld.service
  #systemctl enable firewalld.service
  #firewall-cmd --zone=public --add-port=80/tcp --permanent
  #firewall-cmd --zone=public --add-port=443/tcp --permanent
  #firewall-cmd --reload
  # phpと関連パッケージ
  #yum -y install --enablerepo=remi,remi-php56 php php-devel php-mbstring php-mcrypt php-mysql phpunit
  # MySQL5.6
  #yum -y install http://dev.mysql.com/get/mysql-community-release-el6-5.noarch.rpm
  #yum -y install mysql-community-server
SCRIPT
