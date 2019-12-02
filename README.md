# Análise de dados socioeconômicos ENCCEJA

Aálise basica de questionario do ENCCEJA de anos de 2014 até 2018.

## Instalação

Utilizar o gerenciador de pacotes [pip](https://pip.pypa.io/en/stable/) para instalar as dependências.

```bash
pip install jupyterlab
pip install pandas
pip install matplotlib
```

## Utilização
### Agrupamento de questões


```python
df = pd.DataFrame() # Cria um dataframe para questões iguais
df.insert(0,'2014', df2014['Q002']) # adiciona as de 2014
df.insert(1,'2017', df2017['Q02']) # adiciona as de 2017
df.insert(2,'2018', df2018['Q02']) # adiciona as de 2018
```

### Exibição dos Gráficos
```python
df2 = pd.DataFrame({'Ano': ['2014','2017','2018'], 
                   'A': [(df['2014'] == 'A').sum(), (df['2017'] == 'A').sum(), (df['2018'] == 'A').sum()],
                   'B': [(df['2014'] == 'B').sum(), (df['2017'] == 'B').sum(), (df['2018'] == 'B').sum()], 
                   'C': [(df['2014'] == 'C').sum(), (df['2017'] == 'C').sum(), (df['2018'] == 'C').sum()], 
                   'D': [(df['2014'] == 'D').sum(), (df['2017'] == 'D').sum(), (df['2018'] == 'D').sum()]})
df2.set_index('Ano')
df2.set_index('Ano').plot.bar();
```

## Base de dados
Baixar microdados através do site do [INEP](http://portal.inep.gov.br/microdados) para adquirir os respectivos dados do ENCCEJA.

# Feito por:

Luis Gabriel dos Santos Belo e Matheus Froes Cinachi
