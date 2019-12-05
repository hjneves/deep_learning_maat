# Deep Learning e Redes Neuronais na arte

Benvindo ao workshop de Deep Learning e Redes Neuronais na Arte. Aqui vai encontrar um conjunto de instruções de configuração do seu computador para utilização no workshop.

# Requisitos
Não é necessário ter conhecimentos de programação para participar neste workshop, mas vai ser necessário instalar algmas peças de software.
- FloydHub Account
- Git
- Python 2 (e PIP)
- VirtualEnv

Para executar os comandos indicados nestas instruções devera usar um terminal
- Em macOS usar o 'terminal'
- Em Windows usar o 'cmd'

## FloydHub account
Para a execução dos modelos de deep learning vamos usar a plataforma ![Floydhub](https://www.floydhub.com). A plataforma FloydHub disponibiliza acesso a hardware e software pré-configurado para a execução de modelos de deep learning.
Deverão criar uma conta ![aqui](https://www.floydhub.com/signup)


## Git
Git é uma ferramenta de gestão de versões de projectos que vai utilizada para garantir a sincronização dos ficheiros de imagens que vamos usar e produzir.

Verifique se já tens o *git* instalado através do seguinte comando `git --version`: 

![](https://github.com/hjneves/deep_learning_maat/blob/master/readme/Screen%20Shot%202019-12-04%20at%2010.50.32.png)


## Python 2 e PIP
O python é a ferramenta que dá suporte ao treino e aplicação dos modelos de redes neuronais quevão ser a base da criação artistica sobre as fotografias utilizadas.

Verifique qse já tem o *python* intaladas através do seguinte comando `python -V`
O PIP é uma ferramenta de gestão de pacotes do python. Se o python já estiver instalado o PIP também já deverá estar. Pode verificar a versão corrente do pip através do comando `pip -V`

![](https://github.com/hjneves/deep_learning_maat/blob/master/readme/Screen%20Shot%202019-12-05%20at%2018.07.17.png)
Caso não tenha intalado, pode efectuar a instalação [aqui](https://www.python.org/downloads/release/python-2717/)

## VirtualEnv

O virtualenv é um ambiente sandbox que permite a utilização de um conjunto de pacotes python sem interferir com a configuração actual do sistema. Os passos seguintes permitem criar o ambiente que vamos utilizar no workshop:
- Instalação do virtualenv: `sudo pip install virtualenv`
- Criar directoria de trabalho: `virtualenv ./floyd`
- Activação do ambiente: `source ./floyd/bin/activate`
- No final deveraNow we have (floyd) prepended on the terminal. 
- Instalar o floyd-cli: `pip install -U floyd-cli`


