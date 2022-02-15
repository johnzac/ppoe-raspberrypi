Sets up a raspberry pi to work as a gatway to dsl over pppoe. It's assumed the wan link will be connected to the ethernet port of the pi and the remaining devices will be accessing internet via usb connectrs. Pi will run a dnsmasq that is responsible for dhcp, so once the anible playbook is run and the pi rebooted, we should be able to plug in any device via usb and start accessing the internet. Depending on the values set in roles/pppoe-raspberrypi/vars ,  the playbook can optionally set up a hotspot on the pi and also setup some basic monitoring( promethus + nodeexporter + grafana). I have used https://grafana.com/grafana/dashboards/1860 for displaying node metrics in grafana. Check out the vars file to know how to configure these. 

To run, simply modify the hosts file with the ip address and password for your pi and run "ansible-playbook playbook-pi.yml" from the git root directory. 

Verified on raspbian buster - linux-5.4.51, systemd - 241

You can find an extensive writeup on what the playbook does here: https://medium.com/@zacharia.john92/learning-basic-linux-networking-with-a-raspberry-pi-3d57ddc959a4
