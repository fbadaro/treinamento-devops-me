## Dicas do curso Terminal Linux
---

- [Documentação dos comandos.](https://github.com/fbadaro/101-linux-commands-ebook)
- [A arte da linha de comando.](https://github.com/jlevy/the-art-of-command-line/blob/master/README-pt.md)

<br>

### Permissão de Arquivos
---
Como o Linux é um sistema operacional multiusuário, é necessário fornecer segurança para impedir que as pessoas acessem os arquivos confidenciais umas das outras. Assim, o Linux divide a autorização em 2 níveis.

1. Ownership: Cada arquivo ou diretório foi atribuído a 3 tipos de proprietários.
- Usuário: Proprietário do arquivo que o criou. 
- Grupo: Grupo de usuários com as mesmas permissões de acesso ao arquivo ou diretório. 
- Outro: Aplica-se a todos os outros usuários do sistema.

2. Permissions: Cada arquivo ou diretório tem as seguintes permissões para os 3 tipos de proprietários acima.
- Read: Dá a você autoridade para abrir e ler um arquivo e lista seu conteúdo para um diretório.
- Erite: Dá a você autoridade para modificar o conteúdo de um arquivo e adicionar, remover e renomear arquivos armazenados no diretório.
- Execute: Dá a você autoridade para executar o programa em Unix/Linux.

<br>

As permissões são indicadas com os caracteres abaixo:

```
  r = read permission

  w = write permission

  x = execute permission

  \- = no permission
```
<br>

#### Alterando as permissões
O comando `chmod` é usado para alterar o modo de acesso de um arquivo. Este comando é usado para definir permissões (ler, escrever, executar) em um arquivo/diretório para o proprietário, grupo e outros grupos.

```
chmod [reference][operator][mode] file...

Example
chmod ugo-rwx test.txt
```
<br>

Existem 2 maneiras de usar este comando,

1 - Modo absoluto: As permissões do arquivo serão representadas em um número octal de três dígitos.

| Permission Type | Number |  Symbol |
| ------------- | ----- | ----- |
| No Permission | 0 | --- |
| Execute | 1 | --x |
| Write | 2 | -w- |
| Execute + Write | 3 | -wx |
| Read | 4 | r-- |
| Read + Execute | 5 | r-x |
| Read + Write | 6 | rw- |
| Read + Write + Execute | 7 | rwx |

Vamos atualizar as permissões no modo absoluto com um exemplo abaixo.

```
chmode 764 test.txt
```
<br>

2 - Modo simbólico: O modo simbólico, você pode modificar as permissões de um proprietário específico ao contrário do modo absoluto.

| Owner | Description |
| ----- | ----- |
| u | user/owner |
| g | group |
| o | other |
| a | all |

E a lista de símbolos matemáticos para modificar as permissões de arquivo da seguinte forma,

| Operator | Description |
| ------------- | ----- |
| + | Adds permission |
| - | Removes the permission |
| = | Assign the permission |