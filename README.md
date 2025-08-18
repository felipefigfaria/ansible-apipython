## API Python - Ansible 
Projeto com o objetivo de provisionar e implantar uma API simples em Python de forma automatizada, utilizando o Ansible.  
O fluxo contempla as seguintes etapas:

1. Conexão com a máquina de destino;
2. Atualização dos pacotes do sistema operacional;
3. Instalação do Docker;
4. Instalação do Docker Compose;
5. Clonagem do repositório da API;
6. Autenticação no Docker Hub;
7. Build, criação da tag e push da imagem para o repositório;
8. Inicialização da aplicação em container. 


## 1. Conexão com a máquina de destino

Conexão feita via chave `ssh` e configurada no arquivo `./hosts`

## 2. Atualização dos pacotes do sistema operacional

Com o projeto organizado em `roles`, a primeira a ser executada será responsável por atualizar os pacotes do sistema operacional.

## 3. Instalação do Docker

Na segunda `role`, serão instaladas as dependências necessárias e o Docker Engine. Em seguida, será verificado se o serviço está em execução e, por fim, o usuário será adicionado ao grupo `docker`.

## 4. Instalação do Docker Compose

Na sequência, será instalado o Docker Compose e criado o respectivo link simbólico para seu uso.

## 5. Clonagem do repositório da API; Autenticação no Docker Hub; Build, tag e push da imagem; Up da API

Na quarta e última `role`, será realizada a implantação da aplicação. Primeiramente, o repositório será clonado no diretório `home` do usuário. Em seguida, será efetuado o login no Docker Hub para permitir o `build` da imagem a partir do código clonado, seguido da criação da `tag` e do `push` para o repositório. 

Por fim, a `role` executará a `task` responsável por iniciar a API em um container.