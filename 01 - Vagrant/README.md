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
- vagrant suspend
- vagrant halt

<br> 

#### Helpers
---
- Verificar o PID de um porta especifica: `netstat -ano | findstr :<PORT>`
- Matar o processo pelo PID: `taskkill /PID <PID> /F`

<br> 

## Vagrant - Casos de Uso

## Caso 01:

Provisionamento de ambiente com 4 máquinas, um load balancer, 2 aplicações .net rodando em S.O Linux e se conectando ao banco de dados:

---

### **Maquina 1:**
Servidor Ngnix atuando como um distribuidor de carga entre as aplicações das maquinas 2 e 3.

### **Maquina 2 e 3:**
Aplicações .net que mostram o ip da máquina ao qual esta sendo executada, e a cada solicitação na raiz é gravado um histórico no banco de dados que pode ser acessado no endpoint /history.

### **Maquina 4:**
Servidor com o banco de dados Postgres para armazenamento ao qual pode somente receber solicitações das máquinas 2 e 3.
