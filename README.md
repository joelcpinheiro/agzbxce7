# Instalando/Removendo Zabbix Agent 4.0 LTS no CentOS 7 via Ansible

Esta é uma maneira prática(pra não falar ágil, rs) de instalar/remover o Zabbix Agent no CentOS 7 utilizando Ansible.

## Intruções Iniciais

Acessar o Servidor ARG-VLCEANSIBLE via SSH e entrar no diretório onde está o projeto(`/etc/ansible/agzbxce7/`).

**OBS**: Não esqueça de checar se a porta 10050 está aberta no Host de destino, pois o Zabbix Server irá acessar por esta porta.

### Pré-requisitos

É muito tranquilo, basta seguir os 3 passos abaixo :)


Permitir o acesso SSH para que o Ansible consiga efetuar a operação, enviando a chave pública do Host Ansible para Host de destino e inserir o IP ou nome do Host no playbook, os passos são:

1. Executar o comando no ARG-VLCEANSIBLE `ssh-copy-id root@iphostdestino`;
2. Editar o playbook `install.yml` e no campo hosts inserir o IP ou nome do host de destino;
3. Não esqueça de inserir o IP do host de destino dentro do hosts do Ansible, em `/etc/ansible/hosts` para fazer com que o playbook funcione com sucesso.


## Efetuando a instalação

Dentro do diretório inicial do projeto, executar o comando abaixo, logo após basta acompanhar as tarefas sendo executadas.

```sh
$ ansible-playbook install.yml
```


**OBS**: Após instalado basta acessar o painel administrativo do Zabbix Server e cadastrar o novo host

## Efetuando a DESinstalação

Dentro do diretório inicial do projeto, executar o comando abaixo, ele irá remover os o pacote zabbix-release e o diretório `/etc/zabbix`.


```sh
$ ansible-playbook uninstall.yml
```

## Versão

2.0

## Autor

* **Joel Pinheiro** - *Github* - [joelcpinheiro](https://github.com/joelcpinheiro)


## License

Use onde achar que irá contribuir :)
