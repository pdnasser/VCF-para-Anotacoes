# VCF-para-anotações

## Primeiramente importar o o VCF 
```
from google.colab import drive
drive.mount('/content/drive')
```
## Instalar o VEP

###### 1.instalar as dependências
###### 2.download da release ensembl-ref 105. no github
###### 3.descompactar o arquivo .tar.gz
###### 4.entrar dentro do diretório
###### 5.rodar os scripts
```
%%bash
sudo apt install unzip curl git libmodule-build-perl libdbi-perl libdbd-mysql-perl build-essential zlib1g-dev
wget -c https://github.com/Ensembl/ensembl-vep/archive/refs/tags/105.0.tar.gz
tar -zxvf 105.0.tar.gz
cd ensembl-vep-105.0
./INSTALL.pl --NO_UPDATE
```
