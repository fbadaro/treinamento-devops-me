**Glossário**

[TOC]

# O que é um container Linux

Um [container Linux®](https://www.redhat.com/pt-br/topics/containers) é um conjunto **de um ou mais processos organizados isoladamente** do sistema. Todos os arquivos necessários para executá-los são fornecidos por uma imagem distinta. Na prática, os containers Linux são portáteis e consistentes durante toda a migração entre os ambientes de desenvolvimento, teste e produção. Essas características os tornam uma opção muito mais rápida do que os pipelines de desenvolvimento, que dependem da replicação dos ambientes de teste tradicionais. Os [containers também são uma parte importante da segurança da TI](https://www.redhat.com/pt-br/topics/security) por conta da popularidade e da facilidade de uso deles.



## Como funcionam os containers Linux

Imagine que você esteja desenvolvendo uma aplicação. Você trabalha em um laptop, e o seu ambiente tem uma configuração específica. Outros desenvolvedores podem ter configurações um pouco diferentes. A aplicação desenvolvida é baseada nessa configuração e depende de bibliotecas, dependências e arquivos específicos. Ao mesmo tempo, a empresa em que você trabalha tem ambientes de desenvolvimento e de produção padronizados com uma configuração própria e conjuntos de arquivos auxiliares. Você deseja emular esses ambientes localmente, sem a necessidade de recriar os ambientes do servidor. Então, como fazer a aplicação funcionar em ambientes diferentes, ser aprovada pela garantia de qualidade e implantá-la sem muito esforço, sem a necessidade de reescrever ou realizar reparos no código? A resposta é: containers.

O container que contém a aplicação tem as bibliotecas, dependências e arquivos necessários para migrá-la para a produção sem maiores problemas. Na verdade, você deve pensar no conteúdo de uma imagem de container como uma instalação de uma distribuição Linux, pois essa imagem é completa com pacotes RPM, arquivos de configuração e outros elementos. No entanto, é muito mais fácil lidar com uma distribuição de imagem de container do que instalar novas cópias de sistemas operacionais. Dessa forma, evita-se o conflito e todos ficam satisfeitos.

Esse foi um exemplo simples. No entanto, é possível usar os containers [Linux](https://www.redhat.com/pt-br/topics/linux/what-is-linux) em diversas situações problemáticas das mais variadas maneiras, sempre que for necessário obter o máximo de portabilidade, configurabilidade e isolamento. Com containers Linux, seu negócio desenvolve mais rapidamente e atende às necessidades empresariais conforme elas surgem. Em alguns casos, como a [transmissão de dados em tempo real com o Apache Kafka](https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka), os containers são essenciais, pois são a única maneira de dar a escalabilidade que a aplicação precisa. Seja qual for o tipo de infraestrutura, on-premise, na [nuvem](https://www.redhat.com/pt-br/topics/cloud) ou híbrida, os containers atendem a qualquer demanda. E vale lembrar, escolher a plataforma de container ideal é tão importante quanto os próprios containers.

![O que é um container](https://github.com/fbadaro/treinamento-devops-me/blob/main/00%20-%20Bonus/assets/what-is-a-container.png)



## Qual é a diferença entre virtualização e os containers Linux?

As duas tecnologias são distintas porém complementares. Veja uma maneira fácil de distinguir ambas:

- Com a [virtualização](https://www.redhat.com/pt-br/topics/virtualization), é possível executar sistemas operacionais (Windows ou Linux) simultaneamente em um único sistema de hardware.
- Os containers compartilham o mesmo kernel do sistema operacional e isolam os processos da aplicação do restante do sistema. Por exemplo, os sistemas ARM Linux executam containers ARM Linux, os sistemas x86 Linux executam containers x86 Linux e os sistemas x86 Windows executam containers x86 Windows. Os containers Linux são extremamente portáteis, mas devem ser compatíveis com o sistema subjacente.

![virtualização x containers](https://github.com/fbadaro/treinamento-devops-me/blob/main/00%20-%20Bonus/assets/virtualization-vs-containers.png)

O que isso significa? Para começar, a virtualização usa um hipervisor para emular o hardware, o que permite executar vários sistemas operacionais simultaneamente. Essa não é uma solução tão leve quanto o uso de containers. Quando a capacidade e os recursos são limitados, é necessário usar aplicações leves que possam ser implantadas densamente. Os containers Linux são executados de maneira nativa no sistema operacional, compartilhando-o com todos os outros containers. Assim, as aplicações e os serviços permanecem leves e são executados em paralelo com agilidade.

Os containers Linux são mais um salto evolucionário no desenvolvimento, implantação e gerenciamento de aplicações. Com as imagens de containers Linux, é possível ter portabilidade e controle de versão. Isso ajuda a garantir que os trabalhos contidos no laptop do desenvolvedor sejam executados corretamente no ambiente de produção. Em comparação com as máquinas virtuais, executar containers Linux consome menos recursos, oferece uma interface padrão (início, interrupção, variáveis de ambiente etc.), mantém o isolamento da aplicação e facilita o gerenciamento dos processos, como parte de uma aplicação maior (vários containers). Além disso, é possível orquestrar as aplicações em vários containers em diversas nuvens.



## O que é o  LXC?

O [projeto Linux Containers (LXC)](https://linuxcontainers.org/) é uma plataforma de container open source que fornece um conjunto de ferramentas, modelos, bibliotecas e associações de linguagem. O LXC conta com uma interface de linha de comando simples que melhora a experiência do usuário ao inicializar containers.

Além disso, ele oferece um ambiente de virtualização no nível do sistema operacional disponível para ser instalado em vários sistemas baseados no Linux. O LXC pode estar disponível na sua distribuição Linux por meio do repositório do pacote dela.



## Breve História dos Containers

A ideia do que atualmente chamamos de tecnologia de containers surgiu em 2000 como [jails do FreeBSD](https://www.freebsd.org/doc/handbook/jails.html), uma tecnologia que permite particionar um sistema [FreeBSD](https://www.freebsd.org/) em vários subsistemas ou celas (por isso o nome "jails"). Os jails foram desenvolvidos como ambientes seguros que podiam ser compartilhados por um administrador de sistemas com vários usuários internos ou externos à empresa.

Em 2001, Jacques Gélinas deu o primeiro passo para a implementação de ambientes isolados em Linux por meio de seu [projeto VServer](http://linux-vserver.org/Welcome_to_Linux-VServer.org). Após essa base ser estabelecida para vários espaços de usuário controlados em Linux, as peças começaram a se encaixar para formar o container Linux de hoje.

Em pouquíssimo tempo, mais tecnologias foram combinadas para tornar essa abordagem isolada uma realidade. Os grupos de controle ([cgroups](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Resource_Management_Guide/ch01.html)) são uma funcionalidade de kernel que controla e limita o uso de recursos por um processo ou grupo de processos. E o [systemd](https://www.freedesktop.org/wiki/Software/systemd/), um sistema de inicialização que configura o espaço do usuário e gerencia processos, é usado por cgroups para dar mais controle sobre os processos isolados. Ambas as tecnologias, além de adicionarem um controle geral ao Linux, serviram como estrutura para a separação eficaz de ambientes.



## O Docker entra em cena

Em 2008, o Docker entrou em cena ([por meio do dotCloud](https://blog.docker.com/2013/10/dotcloud-is-becoming-docker-inc/)) com sua tecnologia de container homônima. A tecnologia Docker adicionou muitos dos novos conceitos e ferramentas: uma interface de linha de comando simples para executar e criar novas imagens em camadas, um daemon de servidor, uma biblioteca de imagens de container pré-criadas e o conceito de servidor de registros. Combinadas, essas tecnologias possibilitaram aos usuários criar novos containers em camadas com rapidez e compartilhá-los facilmente com outras pessoas.

Há três padrões principais que garantem a interoperabilidade das tecnologias de container: as especificações [Image](https://github.com/opencontainers/image-spec/), Distribution e [Runtime](https://github.com/opencontainers/runtime-spec/) da OCI. A combinação dessas especificações permite que projetos da comunidade, soluções corporativas e provedores de nuvem criem tecnologias de container interoperáveis. Por exemplo, pense em uma situação em que você precisa introduzir imagens personalizadas no servidor de registro do provedor de nuvem. Atualmente, a Red Hat e o Docker, além de muitas outras organizações, são membros da [Open Container Initiative](https://www.opencontainers.org/) (OCI), cujo objetivo é padronizar as tecnologias de containers no setor open source.



# O que é Docker?

Docker se refere a muitas coisas. Isso inclui: um projeto da comunidade open source; as ferramentas resultantes desse projeto; a empresa Docker Inc., principal apoiadora do projeto; e as ferramentas compatíveis formalmente com a empresa. O fato de que as tecnologias e a empresa têm o mesmo nome pode causar uma certa confusão.

Veja uma simples explicação:

- O software de TI "Docker” é uma tecnologia de containerização para criação e uso de [containers Linux®](https://www.redhat.com/pt-br/topics/containers).
- A [comunidade open source do Docker](https://forums.docker.com/) trabalha gratuitamente para melhorar essas tecnologias para todos os usuários.
- A empresa [Docker Inc.](https://www.docker.com/) se baseia no trabalho realizado pela comunidade do Docker, tornando-o mais seguro, e compartilha os avanços com a comunidade em geral. Depois, ela oferece aos clientes corporativos o suporte necessário para as tecnologias que foram aprimoradas e fortalecidas.

Com o Docker, é possível lidar com os containers como se fossem máquinas virtuais modulares e extremamente leves. Além disso, os containers oferecem maior flexibilidade para você criar, implantar, copiar e migrar um container de um ambiente para outro. Isso [otimiza as aplicações na cloud](https://www.redhat.com/pt-br/topics/cloud-native-apps).



## Como o Docker funciona?

A tecnologia Docker usa o kernel do Linux e recursos do kernel como [Cgroups](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Resource_Management_Guide/ch01.html) e [namespaces](https://lwn.net/Articles/528078/) para segregar processos. Assim, eles podem ser executados de maneira independente. O objetivo dos containers é criar essa independência: a habilidade de executar diversos processos e aplicações separadamente para utilizar melhor a infraestrutura e, ao mesmo tempo, [manter a segurança](https://www.redhat.com/pt-br/topics/security) que você teria em sistemas separados.

As ferramentas de container, incluindo o Docker, fornecem um modelo de implantação com base em imagem. Isso facilita o compartilhamento de uma aplicação ou conjunto de serviços, incluindo todas as dependências deles em vários ambientes. O Docker também automatiza a implantação da aplicação (ou de conjuntos de processos que constituem uma aplicação) dentro desse ambiente de container.

Essas ferramentas baseadas nos containers Linux (o que faz com que o Docker seja exclusivo e fácil de usar) oferecem aos usuários acesso sem precedentes a aplicações, além da habilidade de implantar com rapidez e de ter total controle sobre as versões e distribuição.



## O Docker utiliza a mesma tecnologia que os containers Linux tradicionais?

Não, a tecnologia Docker foi desenvolvida inicialmente com base na tecnologia [LXC](https://linuxcontainers.org/), que a maioria das pessoas associa aos containers Linux "tradicionais". No entanto, desde então, essa tecnologia tornou-se independente. O LXC era útil como uma [virtualização](https://www.redhat.com/pt-br/topics/virtualization) leve, mas não oferecia uma boa experiência para usuários e desenvolvedores. A tecnologia Docker oferece mais do que a habilidade de executar containers: ela também facilita o processo de criação e construção de containers, o envio e o controle de versão de imagens, dentre outras coisas.

![Linux containers vs docker](https://github.com/fbadaro/treinamento-devops-me/blob/main/00%20-%20Bonus/assets/traditional-linux-containers-vs-docker_0.png)

Os containers Linux tradicionais usam um sistema init capaz de gerenciar vários processos. Isso significa que aplicações inteiras são executadas como uma. A tecnologia Docker incentiva que as aplicações sejam segregadas em processos separados e oferece as ferramentas para fazer isso. Essa abordagem granular tem algumas vantagens.



## As vantagens dos containers Docker

### Modularidade

A abordagem do Docker para a containerização se concentra na habilidade de desativar uma parte de uma aplicação, seja para reparo ou atualização, sem interrompê-la totalmente. Além dessa abordagem baseada em microsserviços, é possível compartilhar processos entre várias aplicações da mesma maneira como na [arquitetura orientada a serviço](https://www.redhat.com/pt-br/topics/cloud-native-apps/what-is-service-oriented-architecture) (SOA).

### Camadas e controle de versão de imagens

Cada arquivo de imagem Docker é composto por uma série de camadas. Elas são combinadas em uma única imagem. Uma nova camada é criada quando há alteração na imagem. Toda vez que um usuário especifica um comando, como *executar* ou *copiar*, uma nova camada é criada.

O Docker reutiliza essas camadas para a construção de novos containers, o que torna o processo de criação muito mais rápido. As alterações intermediárias são compartilhadas entre imagens, o que melhora ainda mais [a velocidade, o tamanho e a eficiência](http://developers.redhat.com/blog/2016/03/09/more-about-docker-images-size/). O controle de versões é inerente ao uso de camadas. Sempre que é realizada uma nova alteração, é gerado um changelog integrado, o que fornece controle total sobre as imagens do container.

### Reversão

Talvez a melhor vantagem da criação de camadas seja a habilidade de reverter quando necessário. Toda imagem possui camadas. Não gostou da iteração atual de uma imagem? Simples, basta reverter para a versão anterior. Esse processo é compatível com uma abordagem de desenvolvimento ágil e possibilita as práticas de [integração e implantação contínuas (CI/CD)](https://www.redhat.com/pt-br/topics/devops/what-is-ci-cd) em relação às ferramentas.

### Implantação rápida

Antigamente, colocar novo hardware em funcionamento, provisionado e disponível, levava dias. E as despesas e esforço necessários para mantê-lo eram onerosos. Os containers baseados em docker podem reduzir o tempo de implantação de horas para segundos. Ao criar um container para cada processo, é possível compartilhar rapidamente esses processos similares com novos aplicativos. Como não é necessário inicializar um sistema operacional para adicionar ou mover um container, o tempo de implantação é substancialmente menor. Além disso, com a velocidade de implantação, é possível criar dados e destruir os criados pelos containers sem nenhuma preocupação e com facilidade e economia.

Em resumo, a tecnologia Docker é uma abordagem mais granular, controlável e baseada em microsserviços que valoriza a eficiência.



## Vantagens em se utilizar o Docker

O Docker traz uma API para gerenciamento de contêineres, um formato de imagem e a possibilidade de usar um registro remoto para compartilhar contêineres. Este esquema beneficia desenvolvedores e administradores de sistema com vantagens como:

- **Implementação rápida de aplicativos** - os contêineres incluem os requisitos mínimos de tempo de execução do aplicativo, reduzindo seu tamanho e permitindo que sejam implementados rapidamente.
- **Portabilidade entre máquinas** - um aplicativo e todas as suas dependências podem ser agrupados em um único contêiner que é independente da versão do host do kernel Linux, distribuição de plataforma ou modelo de implantação. Este contêiner pode ser transferido para outra máquina que executa o Docker e executado lá sem problemas de compatibilidade.
- **Controle de versão e reutilização de componentes** - você pode rastrear versões sucessivas de um contêiner, inspecionar diferenças ou reverter para versões anteriores. Os contêineres reutilizam componentes das camadas anteriores, o que os torna notavelmente leves.
- **Compartilhamento** - você pode usar um repositório remoto para compartilhar seu contêiner com outras pessoas. A Red Hat fornece um registro para esse propósito, e também é possível configurar seu próprio repositório privado.
- **Tamanho leve e sobrecarga mínima** - as imagens do Docker são geralmente muito pequenas, o que facilita a entrega rápida e reduz o tempo para implantar novos contêineres de aplicativos.
- **Manutenção simplificada** - o Docker reduz o esforço e o risco de problemas com dependências de aplicativos.



## Há limitações no uso do docker?

Por si só, o Docker é excelente para gerenciar containers únicos. No entanto, quando você começa a usar cada vez mais containers e aplicações em containers segregados em centenas de partes, o gerenciamento e a orquestração podem se tornar um grande desafio. Eventualmente, será necessário recuar e agrupar os containers para oferecer serviços como rede, segurança, telemetria etc. em todos eles. É aí que o Kubernetes entra em cena.

O Docker não fornece as mesmas funcionalidades parecidas com UNIX que os containers Linux tradicionais oferecem. Isso inclui a capacidade de usar processos como cron ou syslog dentro do container, junto à aplicação. O Docker também tem algumas limitações em questões como a limpeza de processos netos (grandchild) após o encerramento dos processos filhos (child), algo que é processado de forma natural nos containers Linux tradicionais. Essas desvantagens podem ser mitigadas ao modificar o arquivo de configuração e configurar essas funcionalidade desde o início, algo que não está imediatamente óbvio em um primeiro momento.

Além disso, há outros subsistemas e dispositivos do Linux sem espaço de nomes. Incluindo os dispositivos [SELinux](https://www.redhat.com/pt-br/topics/linux/what-is-selinux), Cgroups e /dev/sd*. Isso significa que, se um invasor adquirir controle sobre esses subsistemas, o host será comprometido. Para manter-se leve, o compartilhamento do kernel do host com os [containers gera a possibilidade dessa vulnerabilidade na segurança](https://www.redhat.com/pt-br/topics/security/container-security). Isso é diferente nas máquinas virtuais, que são mais firmemente segregadas a partir do sistema host.

O [daemon do Docker](https://docs.docker.com/engine/reference/commandline/dockerd/) também pode representar uma vulnerabilidade à segurança. Para usar e executar os containers Docker, é provável que você use o daemon do Docker, um ambiente de execução persistente para containers. O daemon do Docker requer privilégios de raiz. Portanto, é necessário ter um cuidado maior ao escolher as pessoas que terão acesso a esse processo e o local onde ele residirá. Por exemplo, um daemon local tem menos chances de sofrer um ataque do que um daemon em um local mais público, como um servidor web.



# Kubernetes e a tecnologia de containers

O Kubernetes, ou “kube”, para aqueles que gostam de ser concisos, é uma plataforma open source que automatiza as operações dos [containers Linux](https://www.redhat.com/pt-br/topics/containers/whats-a-linux-container). Essa plataforma elimina grande parte dos processos manuais necessários para implantar e escalar as aplicações em containers. Em outras palavras, se você desejar agrupar em clusters os hosts executados nos containers Linux, o Kubernetes ajudará a gerenciar esses clusters com facilidade e eficiência. Esses clusters podem incluir hosts em [nuvem pública](https://www.redhat.com/pt-br/topics/cloud-computing/what-is-public-cloud), [nuvem privada](https://www.redhat.com/pt-br/topics/cloud-computing/what-is-private-cloud) ou [nuvem híbrida](https://www.redhat.com/pt-br/topics/cloud-computing/what-is-hybrid-cloud). Por isso, o Kubernetes é a plataforma ideal para hospedar [aplicações nativas em nuvem](https://www.redhat.com/pt-br/topics/cloud-native-apps) que exigem escalabilidade rápida, como a transmissão de dados em tempo real por meio do[ Apache Kafka](https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka).

Originalmente, o Kubernetes foi criado e desenvolvido pelos engenheiros do Google. O Google foi um dos [pioneiros no desenvolvimento da tecnologia de containers Linux](https://en.wikipedia.org/wiki/Cgroups). Além disso, a empresa já revelou publicamente que [tudo no Google é executado em containers](https://speakerdeck.com/jbeda/containers-at-scale) (inclusive, essa é a tecnologia por trás dos serviços em cloud da empresa). O Google gera mais de 2 bilhões de implantações de containers por semana, viabilizadas por uma plataforma interna: [Borg](http://blog.kubernetes.io/2015/04/borg-predecessor-to-kubernetes.html). O Borg foi o antecessor do Kubernetes. As lições aprendidas ao longo dos anos de desenvolvimento do Borg foram a principal influência para o desenvolvimento da tecnologia do Kubernetes.

*Uma curiosidade sobre o Kubernets é que os sete raios do logotipo fazem referência ao nome original do projeto, “[Project Seven of Nine](https://cloudplatform.googleblog.com/2016/07/from-Google-to-the-world-the-Kubernetes-origin-story.html)” (Projeto Sete de Nove).*

A Red Hat foi uma das primeiras empresas a trabalhar com o Google no desenvolvimento do Kubernetes, antes mesmo do lançamento da plataforma. Foi assim que nos tornamos o [segundo maior colaborador](https://www.stackalytics.com/cncf?module=kubernetes) com o projeto upstream dessa tecnologia. Em 2015, o Google [doou o projeto Kubernetes](https://techcrunch.com/2015/07/21/as-kubernetes-hits-1-0-google-donates-technology-to-newly-formed-cloud-native-computing-foundation-with-ibm-intel-twitter-and-others/) à [Cloud Native Computing Foundation](https://www.cncf.io/), recém-formada na época.



## Por que o Kubernetes é essencial?

Aplicações de produção abrangem múltiplos containers. Eles devem ser implantados em vários hosts do servidor. A [segurança dos containers](https://www.redhat.com/pt-br/topics/security/container-security) tem várias camadas e pode ser complexa. É aí que o Kubernetes entra em cena. Ele oferece os recursos de orquestração e gerenciamento necessários para implantar containers em escala para essas cargas de trabalho. Com a orquestração do Kubernetes, é possível criar serviços de aplicações que abrangem múltiplos containers, programar o uso deles no cluster, escalá-los e gerenciar a integridade deles com o passar do tempo. Com o Kubernetes, você toma medidas reais para aprimorar a [segurança da TI](https://www.redhat.com/pt-br/topics/security).

Também é necessário integrar o Kubernetes com os serviços de rede, [armazenamento](https://www.redhat.com/pt-br/topics/data-storage), segurança, telemetria e outros para oferecer uma infraestrutura de containers global.

![diagrama Kubernetes](https://github.com/fbadaro/treinamento-devops-me/blob/main/00%20-%20Bonus/assets/kubernetes-diagram-902x416.png)

No entanto, isso obviamente depende do uso que cada empresa faz dos containers em seus próprios ambientes. Uma aplicação rudimentar dos containers Linux os trata como máquinas virtuais rápidas e eficientes. Quando escalado para um ambiente de produção e diversas aplicações, fica claro que é necessário ter vários containers alocados funcionando em conjunto para disponibilizar serviços individuais. Isso multiplica substancialmente o número de containers no ambiente. À medida que eles se acumulam, a complexidade também aumenta.

O Kubernetes corrige vários problemas comuns que ocorrem com a proliferação de containers, organizando-os em "pods". Os pods adicionam uma camada de abstração aos containers agrupados. Assim, é mais fácil programar as cargas de trabalho e fornecer os serviços necessários a esses containers, como rede e armazenamento. Outros componentes do Kubernetes são úteis no balanceamento de carga entre os pods. Com isso, é possível garantir que o número de containers em execução seja suficiente para oferecer suporte às cargas de trabalho.

Com a implementação correta do Kubernetes (e a ajuda de outros projetos open source, como [Atomic Registry](http://www.projectatomic.io/), [Open vSwitch](http://openvswitch.org/), [heapster](https://github.com/kubernetes/heapster), [OAuth](https://oauth.net/) e [SELinux](https://selinuxproject.org/page/Main_Page)), as empresas podem orquestrar todas as partes da infraestrutura de containers.



## Como o Kubernetes funciona e para que serve?

A principal vantagem que as empresas garantem ao usar o Kubernetes, especialmente se estiverem [otimizando o desenvolvimento de aplicações para a cloud](https://www.redhat.com/pt-br/topics/cloud-native-apps), é que elas terão uma plataforma para programar e executar containers em clusters de máquinas físicas ou virtuais. Em termos mais abrangentes, com o Kubernetes, é mais fácil implementar e confiar totalmente em uma infraestrutura baseada em containers para os ambientes de produção. Como o propósito do Kubernetes é automatizar completamente as tarefas operacionais, ele permite que os containers realizem muitas das tarefas possibilitadas por outros sistemas de gerenciamento ou plataformas de aplicações.

O Kubernetes possibilita:

- Orquestrar containers em vários hosts.
- Aproveitar melhor o hardware para maximizar os recursos necessários na execução das aplicações corporativas.
- Controlar e automatizar as implantações e atualizações de aplicações.
- Montar e adicionar armazenamento para executar aplicações com monitoração de estado.
- Escalar rapidamente as aplicações em containers e recursos relacionados.
- Gerenciar serviços de forma declarativa, garantindo que as aplicações sejam executadas sempre da mesma maneira como foram implantadas.
- Verificar a integridade e autorrecuperação das aplicações com posicionamento, reinício, replicação e escalonamento automáticos.



No entanto, o Kubernetes depende de outros projetos para oferecer plenamente esses serviços orquestrados. Com a inclusão de outros projetos open source, é possível atingir a capacidade total do Kubernetes. Dentre esses projetos necessários, incluem-se:

- Registro, como o Atomic Registry ou o Docker Registry.
- Rede, como o OpenvSwitch e roteamento de borda inteligente.
- Telemetria, como o heapster, o kibana, o hawkular e o elastic.
- Segurança, como o LDAP, o SELinux, o RBAC e o OAUTH com camadas de multilocação.
- Automação, com a adição de playbooks do Ansible para a instalação e o gerenciamento do ciclo de vida do cluster.
- Serviços, oferecidos em um catálogo variado de conteúdos previamente criados de padrões de aplicações populares.



## Aprenda a linguagem do Kubernetes

Assim como qualquer tecnologia, há vários termos específicos que podem representar uma barreira inicial. Vamos explicar alguns dos termos mais comuns para ajudar você a entender melhor o Kubernetes.

**Master:** a máquina que controla os nós do Kubernetes. É nela que todas as atribuições de tarefas se originam.

**Nó:** são máquinas que realizam as tarefas solicitadas e atribuídas. A máquina mestre do Kubernetes controla os nós.

**Pod:** um grupo de um ou mais containers implantados em um único nó. Todos os containers em um pod compartilham o mesmo endereço IP, IPC, nome do host e outros recursos. Os pods separam a rede e o armazenamento do container subjacente. Isso facilita a movimentação dos containers pelo cluster.

**Controlador de replicações:** controla quantas cópias idênticas de um pod devem ser executadas em um determinado local do cluster.

**Serviço:** desacopla as definições de trabalho dos pods. Os proxies de serviço do Kubernetes automaticamente levam as solicitações de serviço para o pod correto, independentemente do local do pod no cluster ou se foi substituído.

**Kubelet:** um serviço executado nos nós que lê os manifestos do container e garante que os containers definidos foram iniciados e estão em execução.

**kubectl:** a ferramenta de configuração da linha de comando do Kubernetes.

Mais em: https://kubernetes.io/docs/reference/



## Uso do Kubernets em produção

O Kubernetes é uma tecnologia open source. Por isso, ele não conta com uma estrutura de suporte formal em que as empresas podem confiar totalmente. Problemas com a implantação do Kubernetes durante a execução no ambiente de produção podem representar uma grande dor de cabeça para você e os seus clientes.

Para isso, existe o [Red Hat OpenShift](https://www.redhat.com/pt-br/technologies/cloud-computing/openshift). Essa é uma solução de nível corporativo que oferece o Kubernetes e muito mais. O OpenShift vem com todos os elementos extras que tornam o Kubernetes potente e viável para as empresas, incluindo componentes de registro, rede, telemetria, segurança, automação e serviços. Com o Red Hat OpenShift, os desenvolvedores da sua empresa poderão criar novas aplicações em containers, hospedá-las e implantá-las na cloud. Tudo isso com a escalabilidade, o controle e a orquestração necessários para transformar boas ideias em negócios valiosos de forma rápida e fácil.

Além disso, a maior vantagem dessa solução é que essa plataforma foi desenvolvida e conta com o suporte da Red Hat, a empresa líder global em tecnologia open source.

![diagrama do Kubernetes na infraestrutura](https://github.com/fbadaro/treinamento-devops-me/blob/main/00%20-%20Bonus/assets/kubernetes-diagram-2-824x437.png)

O Kubernetes é executado em um sistema operacional (por exemplo, no [Red Hat Enterprise Linux Container Host](https://www.redhat.com/pt-br/technologies/linux-platforms/old-enterprise-linux)) e interage com pods de containers executados em nós. A máquina mestre do Kubernetes aceita os comandos de um administrador (ou equipe de DevOps) e retransmite essas instruções aos nós subservientes. Essa retransmissão é realizada em conjunto com vários serviços para automaticamente decidir qual nó é o mais adequado para a tarefa. Depois, são alocados os recursos e atribuídos os pods do nó para cumprir a tarefa solicitada.

Portanto, do ponto de vista da infraestrutura, são poucas as mudanças em comparação com a forma como você já gerencia os containers. O controle sobre os containers acontece em um nível superior, tornando-o mais refinado, sem a necessidade de microgerenciar cada container ou nó separadamente. Será necessário realizar algum trabalho, mas em sua maioria trata-se somente de uma questão de atribuir um master do Kubernetes e definir os nós e pods.



## E quanto ao docker?

A tecnologia do [docker](https://www.redhat.com/pt-br/topics/containers/what-is-docker) ainda realiza as mesmas tarefas do seu objetivo original. Quando o Kubernetes programa um pod para um nó, o kubelet no nó instruirá o docker a iniciar os containers especificados. O kubelet, então, continuamente coleta do docker os status desses containers e agrega as informações no master. O docker insere os containers nesse nó e os inicia e interrompe normalmente. A diferença é que um sistema automatizado solicita que o Docker realize essas tarefas em todos os nós de todos os containers, em vez do administrador fazer essas solicitações manualmente.



# O que é orquestração de containers?

A orquestração automatiza a implantação, o gerenciamento, a escala e a rede dos containers. Ela é perfeita para as empresas que precisam implantar e gerenciar centenas de milhares de hosts e [containers Linux®](https://www.redhat.com/pt-br/topics/containers/whats-a-linux-container). 

É possível usar a orquestração em todos os ambientes em que você usa os containers. Com ela, você implanta a mesma aplicação em ambientes diferentes sem precisar reprojetá-la. Além disso, com os [microsserviços](https://www.redhat.com/pt-br/topics/microservices/what-are-microservices) em containers, é mais fácil orquestrar serviços, incluindo armazenamento, rede e segurança. 

Os containers oferecem às aplicações baseadas em microsserviços uma unidade de implantação e um ambiente de execução autônomo ideais. Eles possibilitam a execução independente de várias partes de uma aplicação em microsserviços no mesmo hardware, com um controle muito maior sobre os componentes individuais e ciclos de vida.

Usar a orquestração no gerenciamento do ciclo de vida dos containers também oferece suporte às equipes de DevOps que integram fluxos de trabalho de CI/CD a ele. Com as [interfaces de programação de aplicações (APIs)](https://www.redhat.com/pt-br/topics/api/what-are-application-programming-interfaces) e as equipes de DevOps, os microsserviços em containers são os pilares das [aplicações nativas em nuvem](https://www.redhat.com/pt-br/topics/cloud-native-apps).



## Qual é a finalidade da orquestração de containers?

Use a orquestração de containers para automatizar e gerenciar tarefas como:

- Provisionamento e implantação
- Configuração e programação 
- Alocação de recursos
- Disponibilidade dos containers 
- Escala ou remoção de containers com base no balanceamento de cargas de trabalho na infraestrutura
- Balanceamento de carga e roteamento de tráfego 
- Monitoramento da integridade do container
- Configuração da aplicação com base no container em que ela será executada
- Proteção das interações entre os containers



## Ferramentas de orquestração de containers

As ferramentas de orquestração de containers fornecem um framework para gerenciar arquiteturas de microsserviços e containers em escala. Muitas delas podem ser usadas no gerenciamento do ciclo de vida dos containers. Algumas opções conhecidas são o Kubernetes, Docker Swarm e Apache Mesos.

O [Kubernetes](https://www.redhat.com/pt-br/topics/containers/what-is-kubernetes) é uma ferramenta open source de orquestração de containers projetada e desenvolvida originalmente por engenheiros do Google. Em 2015, o [Google doou](https://techcrunch.com/2015/07/21/as-kubernetes-hits-1-0-google-donates-technology-to-newly-formed-cloud-native-computing-foundation-with-ibm-intel-twitter-and-others/) o projeto Kubernetes à recém-formada [Cloud Native Computing Foundation](https://www.cncf.io/).

Com a capacidade de orquestração do Kubernetes, é possível criar serviços de aplicações que abrangem múltiplos containers, programar o uso dos containers no cluster, escalá-los e gerenciar a integridade deles ao longo do tempo.

O Kubernetes elimina grande parte dos processos manuais necessários para implantar e escalar aplicações em container. É possível agrupar em clusters os hosts, sejam eles físicos ou máquinas virtuais, executados nos containers Linux. Com o Kubernetes, você tem uma plataforma para gerenciar esses clusters com facilidade e eficiência. 

Em termos mais abrangentes, com o Kubernetes, é mais fácil implementar e confiar totalmente em uma infraestrutura baseada em containers para os ambientes de produção.

Esses clusters podem abranger hosts em nuvens públicas, privadas ou híbridas. Por isso, o Kubernetes é a plataforma ideal para hospedar aplicações nativas em nuvem que exigem escalabilidade rápida.

O Kubernetes também ajuda com o balanceamento de carga e a portabilidade de cargas de trabalho, possibilitando a migração de aplicações sem precisar reprojetá-las. 



## Como a orquestração de containers funciona?

Ao usar uma ferramenta de orquestração de containers, como o Kubernetes, você define a configuração de uma aplicação usando um arquivo JSON ou YAML. Esse arquivo informa à ferramenta de gerenciamento de configurações o local das imagens do container, como estabelecer uma rede e onde armazenar os registros.

Quando você implanta um novo container, a ferramenta de gerenciamento de containers programa automaticamente esse processo em um cluster e atribui o host adequado, levando em consideração todas as restrições ou requisitos definidos. Depois, a ferramenta de orquestração gerencia o ciclo de vida do container com base nas especificações determinadas no arquivo de composição.

É possível usar os [padrões do Kubernetes](https://www.redhat.com/pt-br/topics/cloud-native-apps/introduction-to-kubernetes-patterns) para gerenciar a configuração, o ciclo de vida e a escalabilidade dos serviços e aplicações baseadas em container. Esses padrões repetíveis são as ferramentas necessárias para que desenvolvedores do Kubernetes criem sistemas completos. 

A orquestração pode ser usada em todos os ambientes que executam containers, incluindo servidores on-premise ou nuvens públicas e privadas.

Fonte:

- https://www.redhat.com/
- https://www.docker.com/
- https://kubernetes.io