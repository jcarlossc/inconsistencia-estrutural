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
* ```import io```, ```df = pd.read_csv(io.StringIO(csv_data))```. O valor ```Unnamed: 0``` será adicionado à coluna vazia. Após isto, este valor poderá ser trocado por um nome mais adequado.
* ```df.drop(columns={'coluna'})```. Apaga coluna.
* ```df = df.rename(columns={'coluna' : 'nova_coluna'})```. Renomea coluna.
* ```df = df.rename(columns={'coluna': 'nova_coluna', 'coluna': 'nova_coluna'})```. Renomea várias colunas.
* ```df.set_axis(['coluna1', 'coluna2', 'coluna3'], axis=1, inplace=True)```. Renomea com método set_axis.
* ```df.columns = [col.replace('_', ' ').title() for col in df.columns]```. Renomea com list comprehension.
* ```df = df.rename(columns={2: 'coluna'})```. Renomea com índice.
* ```df.columns = ['coluna1', 'coluna2', 'coluna3']```. Renomea através de uma lista de novas colunas.
## ✅ Tipos de dados incorretos (ex: datas como texto, números como string)
* ```df['hora'] = pd.to_datetime(df['hora'], format='%H:%M:%S', errors='coerce')```. Converter hora no formato string para datetime.
* ```df['data'] = pd.to_datetime(df['data'], errors='coerce')```. Converter data no formato string para datetime.
* ```df['data_hora'] = pd.to_datetime(df['data_hora'], errors='coerce')```. Converter data e hora simultâneamente.
  * ```df['hora'] = df['data_hora'].dt.time```. Extrai hora de data_hora.
  * ```df['data'] = df['data_hora'].dt.date```. Extrai data de data_hora.
* ```df['hora_hora'] = pd.to_datetime(df['data_hora'], errors='coerce').dt.hour```. Tudo em um: converter para datetime e imprime as horas.
* ```df['hora_minutos'] = pd.to_datetime(df['data_hora'], errors='coerce').dt.minute```. Tudo em um: converter para datetime e imprime os minutos.
* ```df['hora_segundos'] = pd.to_datetime(df['data_hora'], errors='coerce').dt.second```. Tudo em um: converter para datetime e imprime os segundos.
* ```df['data_dia'] = pd.to_datetime(df['data'], errors='coerce').dt.day```. Tudo em um: converter para datetime e imprime os dias.
* ```df['data_mes'] = pd.to_datetime(df['data'], errors='coerce').dt.month```. Tudo em um: converter para datetime e imprime os meses.
* ```df['data_ano'] = pd.to_datetime(df['data'], errors='coerce').dt.year```. Tudo em um: converter para datetime e imprime o ano.
* ```df['idade_'] = pd.to_numeric(df['idade'], errors='coerce')```. Converte string para numérico.
* ```df['preco'] = df['preco'].str.replace('R\$', '', regex=True).str.replace(',', '.').str.strip()```. Corrigir preços com símbolo e vírgula.
## ✅ Index desalinhado ou perdido
* ✅ Arquivos quebrados ou mal formatados (ex: CSV mal separado)
