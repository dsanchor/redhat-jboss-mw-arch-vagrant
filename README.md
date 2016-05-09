# redhat-jboss-mw-arch-vagrant

Vagrant multimachine demo environment for redhat-jboss-mw-arch-demo

###Prerequisites

Host manager plugin => https://github.com/devopsgroup-io/vagrant-hostmanager

Landrush plugin => https://github.com/vagrant-landrush/landrush

**Linux users:** follow next steps in order to make landrush work:

First, try: http://lameter.rssing.com/browser.php?indx=1151212&item=14728

Fedora:

1. In /etc/NetworkManager/NetworkManager.conf set dns=dnsmasq under [main] section:

  [main]
  plugins=ifcfg-rh,ibft
  dns=dnsmasq

2. Create file /etc/NetworkManager/dnsmasq.d/vagrant-landrush.conf with following content:

  server=/.arch.redhat.dev/127.0.0.1#10053

3. Restart NetworkManager 

  systemctl restart NetworkManager
