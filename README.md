# VCF-para-anotações

## Primeiramente fazer o download do VCF(WP312.filtered.vcf.tsv)

## Instalar o VEP:

###### 1.instalar as dependências
###### 2.download da release ensembl-ref 105. no github
###### 3.descompactar o arquivo .tar.gz
###### 4.entrar noo diretório
###### 5.rodar o script

```
%%bash
sudo apt install unzip curl git libmodule-build-perl libdbi-perl libdbd-mysql-perl build-essential zlib1g-dev
wget -c https://github.com/Ensembl/ensembl-vep/archive/refs/tags/105.0.tar.gz
tar -zxvf 105.0.tar.gz
cd ensembl-vep-105.0
./INSTALL.pl --NO_UPDATE
```
###### Nota: "NO_UPDATE" - para que o script seja processado sem pausas ou aceitações do usuário.
```
%%bash
cd ensembl-vep-105.0
./vep
```
```
%%bash
./ensembl-vep-105.0/vep  \
  --fork 3 \
	-i /content/drive/Shareddrives/T4-2022/homo_sapiens_refseq/105_GRCh37/WP312.filtered.vcf.gz \
	-o WP312.filtered.vcf.tsv \
  --dir_cache /content/drive/Shareddrives/T4-2022 \
  --fasta /content/drive/Shareddrives/T4-2022/homo_sapiens_refseq/Homo_sapiens_assembly19.fasta \
  --cache --offline --assembly GRCh37 --refseq  \
	--pick --pick_allele --force_overwrite --tab --symbol --check_existing --variant_class --everything --filter_common \
  --fields "Uploaded_variation,Location,Allele,Existing_variation,HGVSc,HGVSp,SYMBOL,Consequence,IND,ZYG,Amino_acids,CLIN_SIG,PolyPhen,SIFT,VARIANT_CLASS,FREQS" \
  --individual all
```



```
!pip install pandas
```

```
import pandas as pd
import csv
tabela = pd.read_csv('/content/WP312.filtered.vcf.tsv', sep='\t', skiprows=38)
df = pd.DataFrame(tabela)
df
```

