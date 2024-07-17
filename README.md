# firewall_fail2ban
## Objectif
Configuration d'un firewall sous linux et configuration
d"un outil de prévention d'intrusion.

## Etape 1: configuration demandée
- OS: Debian version "BUSTER" sans GUI
- Services:
    - sshd
    - proftpd
    - httpd
    - mysqld

Commentaire: Debian version "Buster" (10.0) a été initialement
publiée le 8 juillet 2019. La dernière révision 10.13 a été
publiée le 10 septembre 2022. Les mises à jours de sécurités
sont arrêtés depuis le 30 juin 2022. Le supportà LTS est assuré
jusqu'au 30 juin 2024 (ref: [Debian](https://www.debian.org/releases/buster/))

Vu le peu de temps qu'il reste à cette version, et sans aucune mise à jour
de sécurité, nous décidons d'installer une verion "Bookworm" (12.5) au moment
de l'écriture de ce tutorial. Evidement cela va avoir un impact sur le choix
du pare-feux puisque le couple iptables/netfilter est en mode legalcy et qu'il
est très officiellement remplacé par le couple netfilter/nftables.

### Installation du système
Installation minimale d'une Vm Debian "Bookworm" (12)
sur VirtualBox
Pour les besoins de ce tutorial:
- Configuration de la VM:
    - vCPU: 2
    - RAM: 6549Mio
    - Disk: 20.00 Gio
- Installation:
    - Minimale

### Mise à jour et configuration des premiers services
'''Shell
sudo apt install -y vim bash-completion &&
sudo apt install -y apache2 openssh-server proftpd-core default-mysql-server
'''
Ports ouverts:
- 80, 443 tcp
- 20, 21 tcp
- 22 tcp
- 3306 tcp



