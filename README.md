# Treinamento Devops ME

## Trilha Introdução:

1. https://www.schoolofnet.com/curso/automacao/vagrant-e-puppet/trabalhando-com-vagrant-rev2/
2. https://www.schoolofnet.com/curso/sistemas-operacionais/terminal/trabalhando-com-windows-subsystem-linuxwsl/
3. https://www.schoolofnet.com/curso/sistemas-operacionais/terminal/terminal-no-linux-v2/
4. https://www.schoolofnet.com/curso/sistemas-operacionais/terminal/terminal-no-linux-pt02/
5. https://www.schoolofnet.com/curso/git/controle-de-versao/git-e-github/

<br> 

## Dicas do curso Trabalhando com Vagrant.
---

Esta é a localização das suas boxes quando se utiliza host windows: `C:/Users/USERNAME/.vagrant.d/boxes`

Para você ja iniciar um VagrantFile baseado numa imagem pode-se executar o seguinte comando: `vagrant init hashicorp/precise64` posteriormente depois de feito o download da box `vagrant up`.

Uma outra dica para este curso é que, a imagem utilizada como base para as aulas é a [hashicorp/precise64](https://app.vagrantup.com/hashicorp/boxes/precise64) mas aparentemente a mesma não é uma versão LTS do Ubuntu, o que pode gerar alguns problemas nos endereços dos pacotes de instalação, uma imagem melhor para se usar é a [ubuntu/trusty64](https://app.vagrantup.com/ubuntu/boxes/trusty64)

<br>

### Posts, Tutoriais e etc:
---
- https://www.tutorialworks.com/linux-vm-vagrant/
- https://www.taniarascia.com/how-to-install-apache-php-7-1-and-mysql-on-ubuntu-with-vagrant/

<br>

### Comandos
---
Documentação da [CLI](https://developer.hashicorp.com/vagrant/docs/cli]) Vagrant.

- vagrant add box [box_name]
- vagrant init [box_name]
- vagrant up
- vagrant destroy -f
- vagrant reload provision

<br> 

#### Helpers
---
- Verificar o PID de um porta especifica: `netstat -ano | findstr :<PORT>`
- Matar o processo pelo PID: `taskkill /PID <PID> /F`