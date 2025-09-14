# IBGE - Carga de Dados dos Estados e Municípios do Brasil

Este notebook realiza a extração, transformação e carga (ETL) dos dados de estados e municípios do Brasil, utilizando a API do IBGE disponibilizada pela [BrasilAPI](https://brasilapi.com.br/). O objetivo é criar uma tabela Delta particionada por estado, contendo informações detalhadas sobre cada município e seu respectivo estado.

## Etapas do Processo

1. **Criação da Tabela Delta**  
   Cria a tabela `ibge_brasil` no Databricks, particionada por estado, para armazenar os dados dos municípios e estados.

2. **Extração dos Dados dos Estados**  
   Utiliza a API para obter a lista de todos os estados brasileiros, incluindo informações como nome, sigla, região e identificadores.

3. **Extração dos Dados dos Municípios**  
   Para cada estado, consulta a API para obter a lista de municípios, associando cada município ao seu respectivo estado.

4. **Transformação dos Dados**  
   Padroniza os nomes dos campos e realiza o join entre municípios e estados, adicionando a data de carga.

5. **Carga dos Dados**  
   Escreve os dados finais na tabela Delta criada, sobrescrevendo os dados anteriores.

6. **Otimização da Tabela**  
   Executa o comando de otimização para melhorar a performance das consultas.

---

**Fonte dos dados:** [BrasilAPI - IBGE](https://brasilapi.com.br/)