Vagrant.configure("2") do |config|
  # Choix de la box (systeme d'exploitation)
  config.vm.box = "ubuntu/jammy64"

  # Configuration de la mémoire
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end

  # Configuration du réseau pour permettre l'appel sous le nom 'docker'
  config.vm.hostname = "docker"

  config.vm.network "forwarded_port", guest:80, host:80
  config.vm.network "private_network", ip:"192.168.0.2"
  
# Provisionnement avec un script shell pour installer Docker
  config.vm.provision "shell", inline: <<-SHELL
    # Commande installation docker shell


# Exécutez la commande suivante pour désinstaller tous les packages en conflit :

for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Commandes réferentiel docker

sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Ajout du repo apt source
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update


# Installation de la dernière version de docker

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

# Ajout de vagrant dans le groupe docker pour pouvoir piloté le demon docker

sudo usermod -aG docker vagrant

    
  SHELL
end
