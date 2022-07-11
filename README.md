# ANP Fuel Sales ETL
Transformação de dados a partir de uma planilha disponibilizada no site da ANP (Agência Nacional do Petróleo, Gás Natural e Biocombustíveis)


É disponibilizado um arquivo no formato .xlx contemplando várias tabelas dinâmicas como no exemplo a seguir na imagem:


![stack Overflow](https://raw.githubusercontent.com/raizen-analytics/data-engineering-test/master/images/pivot.png)

A partir do arquivo base seria necessário fazer transformação para o schema que consiste na tabela abaixo.


| Column     | Type      |
|------------|-----------|
| year_month | date      |
| uf         | string    |
| product    | string    |
| unit       | string    |
| volume     | double    |
| created_at | timestamp |
