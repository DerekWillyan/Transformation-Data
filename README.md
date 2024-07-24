# Transformar Dados em SQL

Este projeto é um script em Python que permite transformar dados de arquivos JSON, CSV e XML em uma tabela SQL no MySQL. O usuário especifica o caminho do arquivo, o script identifica o tipo de arquivo, exibe as colunas e, se desejado, insere os dados em uma tabela MySQL.

## Funcionalidades

- Aceita arquivos JSON, CSV e XML como entrada.
- Identifica automaticamente o tipo de arquivo.
- Exibe os nomes das prováveis colunas para armazenamento no banco de dados SQL.
- Insere os dados na tabela MySQL especificada pelo usuário.

## Requisitos

- Python 3.x
- pandas
- mysql-connector-python

## Instalação

1. Clone o repositório:

  ```bash
  git clone https://github.com/DerekWillyan/Transformation-Data.git
  cd Transformation-Data
   ```
2. Instale os pacotes necessários:

  ```bash
  pip install pandas mysql-connector-python
  ```
# Uso
Execute o script:

  ```bash
  python transform_to_sql.py
  ```
Siga as instruções fornecidas pelo script:
- Especifique o caminho do arquivo (JSON, CSV ou XML).
- O script identificará o tipo de arquivo e exibirá os nomes das colunas.
- Decida se deseja transformar os dados para SQL.
- Se optar por continuar, forneça as credenciais do MySQL e o nome da tabela onde os dados serão inseridos.
  
# Estrutura do Código
- get_file_path(): Solicita ao usuário o caminho do arquivo.
- identify_file_type(file_path): Identifica o tipo de arquivo com base na extensão.
- get_columns(file_path, file_type): Lê o arquivo e converte os dados em um DataFrame do pandas.
- transform_to_sql(df, columns): Conecta-se ao banco de dados MySQL e insere os dados na tabela especificada.
- main(): Gerencia o fluxo principal do script.

# Tratamento de Valores NaN
Antes de inserir os dados no MySQL, o script substitui os valores NaN por None, que é interpretado como NULL no MySQL:

  ```python
  df = df.where(pd.notnull(df), None)
  ```
# Contribuição
Se você quiser contribuir com este projeto, sinta-se à vontade para abrir uma issue ou enviar um pull request.

# Licença
Este projeto está licenciado sob a Licença MIT. Veja o arquivo LICENSE para mais detalhes.

Feito por Derek Willyan
