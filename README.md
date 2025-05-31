# Inconsistencia Estrutural
Estudo sobre inconsistência estrutural de dados

## ✅ Colunas duplicadas
* ```df.T.duplicated()``` - Retorna uma série com valores True e False das colunas duplicadas e não duplicadas respectivamemte.
* ```df.T.duplicated().sun()``` - Conta colunas duplicados.
* ```df.T.drop_duplicates()``` - Apaga colunas duplicadas.

## ✅ Linhas duplicadas
* ```df.duplicated()``` - Retorna uma série com valores True e False das linhas duplicadas e não duplicadas respectivamemte.
* ```df.duplicated().sun()``` - Conta linhas duplicados.
* ```df.drop_duplicates()``` - Apaga linhas duplicadas.
* ```df.drop_duplicates().sum()``` - Retorna a soma das linhas nãi duplicadas.
  
Parâmetro. subset=['coluna', 'coluna'] : para colunas específicas.
df = df.duplicated(subset=['coluna', 'coluna'])
Parâmetro. keep='first' : (padrão): Mantém a primeira ocorrência e remove as demais.
df = df.duplicated(keep='first')
Parâmetro. keep='last': Mantém a última ocorrência e remove as demais.
df = df.duplicated(keep='last')
Parâmetro. keep=False : Remove todas as ocorrências de duplicatas.
df = df.duplicated(keep=False)
Especifica coluna.
df = df['coluna'].duplicated()



* ✅ Colunas sem nome / nomes genéricos (ex: Unnamed: 0)
* ✅ Tipos de dados incorretos (ex: datas como texto, números como string)
* ✅ Index desalinhado ou perdido
* ✅ Arquivos quebrados ou mal formatados (ex: CSV mal separado)
