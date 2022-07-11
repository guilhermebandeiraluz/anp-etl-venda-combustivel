# ANP Fuel Sales ETL
Transformação de dados a partir de uma planilha disponibilizada no site da ANP (Agência Nacional do Petróleo, Gás Natural e Biocombustíveis)

## Desafio

É disponibilizado um arquivo no formato .XLS em uma URL (https://github.com/raizen-analytics/data-engineering-test/raw/master/assets/vendas-combustiveis-m3.xls)  contemplando várias tabelas dinâmicas como no exemplo a seguir na imagem:


![stack Overflow](https://raw.githubusercontent.com/raizen-analytics/data-engineering-test/master/images/pivot.png)

A partir desse arquivo é necesario fazer a transformação das tabelas dinamicas contidas no arquivo na seguinte estrutura de dados
<p></p>


| Column     | Type      |
|------------|-----------|
| year_month | date      |
| uf         | string    |
| product    | string    |
| unit       | string    |
| volume     | double    |
| created_at | timestamp |


## Desenvolvimento da solução proposta

Em um ambiente Linux foi configurado o Jupyter Notebook para o desenvolvimento do script para transformação/ingestão (A ser definido destino). 
* Utilizado a biblioteca urllib para o Download do arquivo contido na URL.
* Com o arquivo salvo do diretorio, foi necessario fazer a transformação dele de XLS para XLSX 
  - CMD: os.system(f'''libreoffice --headless --invisible --convert-to xlsx {vArquivo} --outdir {vCaminho}''')
  
<p></p>
<p>Tomando como base o arquivo transformado foi realizado o export das tabelas dinâmicas e novos arquivos contendo os dados referente as dinâmicas.
  ['DPCache_m3', 'DPCache_m3_2', 'DPCache_m3_3', 'DPCache_m3_4', 'DPCache_m3_5', 'DPCache_m3_6']

<p></p>  
Pelo Python foi analisado o conteúdo de cada arquivo e elencado quais dinâmicas seria utilizado para as manipulações de dados para essas transformações foi utilizado a biblioteca Pandas. 
<p>
Após as transformações a partir do dataframe final, com as duas tabelas necessárias uma para Derivados de Gasolina e outro para Óleo Diesel
</p>

Também está disponivel arquivo .py com o script desenvolvido para solucionar a estruturação das informações contidas no arquivo do ANP.

