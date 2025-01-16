# Configuração de Ambiente com Vagrant

## Descrição do Projeto

Este projeto utiliza o Vagrant para criar e configurar uma máquina virtual baseada no Ubuntu 20.04 (focal64). A máquina é configurada para usar uma rede em modo bridge, permitindo acesso à rede local. Além disso, uma pasta é sincronizada entre o host e a máquina virtual para facilitar o compartilhamento de arquivos. O projeto também define recursos de hardware personalizados, como nome, memória RAM e número de CPUs.

## Requisitos do Sistema

- Vagrant instalado ([Instale através do link ->](https://developer.hashicorp.com/vagrant/downloads))
- VirtualBox instalado ([Instale através do link ->](https://www.virtualbox.org/))

## Configurações

- Sistema Operacional da VM: Ubuntu 20.04 (focal64).
- Rede: Modo bridge, configurado para usar "en0: Wi-Fi".  //Ajuste com base na sua rede
- Pasta sincronizada: `./shared-files` no host para `/vagrant_data` na VM.
- Recursos da VM:
  - Nome: `VagrantVM1`
  - Memória RAM: 1 GB
  - CPU: 1 núcleo

## Instruções para Iniciar a Máquina Virtual

1. Certifique-se de que o Vagrant e o VirtualBox estejam instalados no sistema.
2. Navegue até o diretório onde está localizado o arquivo `Vagrantfile`.
   ```bash
   cd /yuri/Desktop/Vagrant-ubuntu       //ajuste com o caminho real de sua máquina
   ```
3. Inicie a máquina virtual com o seguinte comando:
   ```bash
   vagrant up
   ```
4. O Vagrant irá baixar a box (caso ainda não tenha sido baixada) e configurar a máquina virtual automaticamente.

## Como Acessar a Máquina Virtual via SSH

Após iniciar a máquina virtual:

1. Acesse a máquina virtual usando o comando:
   ```bash
   vagrant ssh
   ```
2. Você estará logado na VM com o usuário padrão configurado pelo Vagrant.

## Sobre a Pasta Sincronizada

- A pasta sincronizada permite compartilhar arquivos entre o host (seu computador) e a máquina virtual.
- No host, a pasta configurada é `./shared-files` (no mesmo nível do Vagrantfile).
- Na máquina virtual, os arquivos dessa pasta estarão acessíveis em `/vagrant_data`.

### Como Utilizar:

1. Coloque os arquivos que deseja compartilhar na pasta `./shared-files` no seu host.
2. Acesse os mesmos arquivos na máquina virtual dentro do diretório `/vagrant_data`:
   ```bash
   cd /vagrant_data
   ls
   ```
3. Para validar o conteúdo do arquivo, afim de conferir se foi devidamente sincronizado, rode o comando:
    ```bash
    cat /vagrant_data/hello.php
    ```
4. Qualquer alteração realizada nos arquivos da pasta sincronizada será refletida em ambos os lados (host e VM).
---
