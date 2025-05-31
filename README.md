# Inconsistencia Estrutural
Estudo sobre inconsistência estrutural de dados

## ✅ Colunas duplicadas
* ```df.T.duplicated()``` - Retorna uma série com valores True e False das colunas duplicadas e não duplicadas respectivamemte.
* ```df.T.duplicated().sun()``` - Conta colunas duplicados.
* ```df.T.drop_duplicates()``` - Apaga colunas duplicadas.
## ✅ Linhas duplicadas
* ```df.duplicated()``` - Retorna uma série com valores True e False das linhas duplicadas e não duplicadas respectivamemte.
  * Parâmetros:
  * ```df.duplicated(subset=[coluna])``` ou ```df.duplicated(subset=[[coluna, coluna]])```. Opcional. Uma string, ou uma lista, dos nomes das colunas a serem incluídas ao procurar por duplicatas.
  * ```df.duplicated(keep='first')```. Opcional, padrão 'first'. Especifica como lidar com duplicatas: 'first' significa definir a primeira ocorrência como False, as demais como True. 'last' significa definir a última ocorrência como False, as demais como True. False significa definir todas as ocorrências como True.
* ```df.duplicated().sun()``` - Conta linhas duplicados.
* ```df.drop_duplicates()``` - Apaga linhas duplicadas.
  * Parâmetros:
  * ```df.drop_duplicates(subset=[coluna])``` ou ```df.duplicated(subset=[[coluna, coluna]])```. Opcional. Uma string, ou uma lista, dos nomes das colunas a serem incluídas ao procurar por duplicatas.
  * ```df.drop_duplicates(keep='first')```. Opcional, padrão 'first'. Especifica como lidar com duplicatas: 'first' significa definir a primeira ocorrência como False, as demais como True. 'last' significa definir a última ocorrência como False, as demais como True. False significa definir todas as ocorrências como True.
  * ```df.drop_duplicates(inplace=False)```. Opcional, padrão Falso. Se Verdadeiro: a remoção é feita no DataFrame atual. Se Falso: retorna uma cópia onde a remoção foi feita.
  * ```df.drop_duplicates(ignore_index=False)```. Opcional, padrão Falso. Especifica se deve rotular 0, 1, 2 etc., ou não.
* ```df.drop_duplicates().sum()``` - Retorna a soma das linhas não duplicadas.
## ✅ Colunas sem nome / nomes genéricos (ex: Unnamed: 0)
* ✅ Tipos de dados incorretos (ex: datas como texto, números como string)
* ✅ Index desalinhado ou perdido
* ✅ Arquivos quebrados ou mal formatados (ex: CSV mal separado)
