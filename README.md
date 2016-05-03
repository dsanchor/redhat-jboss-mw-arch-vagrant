# redhat-jboss-mw-arch-vagrant

Vagrant multimachine demo environment for redhat-jboss-mw-arch-demo

###Prerequisites

Host manager plugin => https://github.com/devopsgroup-io/vagrant-hostmanager
Landrush plugin => https://github.com/vagrant-landrush/landrush

** Linux users: ** follow next steps in order to make landrush work:

Add following to /etc/dnsmasq.conf
listen-address=127.0.0.1

Create /etc/dnsmasq.d/vagrant-landrush file with following content
server=/.arch.redhat.dev/127.0.0.1#10053

Restart dnsmasq service and check status (Should be active)
sudo systemctl start dnsmasq.service 
sudo systemctl status dnsmasq.service

Include the following at first place in /etc/resolve.conf
nameserver 127.0.0.1

###Demo apps

Copy binaries of the demo applications under ./jbdc01/jbossshare/demo/apps
Uncomment line #$JBOSS_HOME/bin/jboss-cli.sh --connect controller=$DOMAIN_CONTROLLER_HOST:9999 --user=$USER --password=$PASSWORD --file=$JBOSSSHARE_HOME/demo/scripts/deploy-apps.cli in ./jbdc01/provision.sh 





