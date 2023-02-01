# k3sup

Vorrausetzung auf dem künftigen MasterNode

      apt update
  
      apt install ssh curl 
  
hostnamectl set-hostname <neuer Hostname> --> neustarten

/etc/ssh/sshd.config
  
      PermitRootLogin yes

      systemctl restart ssh

ip a --> IP-Adresse notieren

Arbeitsrechner:

#IP-Adresse des MasterNode's einpflegen und einen DNS-Namen vergeben, hier im Beispiel nennen wir ihn "master"
/etc/hosts

#ssh Schlüssel erzeugen
      ssh-keygen

#ssh-Schlüssel auf den MasterNode 
      ssh-copy-id -i ./ssh/id_rsa master 

#Installation arkade aus dem Git-Repository
# https://github.com/alexellis/k3sup#create-a-multi-master-ha-setup-with-embedded-etcd
      curl -sLS https://get.arkade.dev | sudo sh

#Installation von kubectl, helm, k3sup und yq
      arkade get kubectl helm k3sup yq

#Github zu k3sup: https://github.com/alexellis/k3sup#create-a-multi-master-ha-setup-with-embedded-etcd

