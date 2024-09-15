Análise de Dados com PostgreSQL
Este repositório contém o trabalho de extensão realizado para a faculdade, onde foi utilizada a ferramenta pgAdmin 4 para realizar uma análise de dados. O objetivo principal foi calcular estatísticas descritivas como média, desvio padrão, valor máximo e valor mínimo dos dados fornecidos.

Descrição do Projeto
Neste projeto, foram realizadas análises estatísticas utilizando o PostgreSQL através do pgAdmin 4. As seguintes análises foram realizadas:

Cálculo da Média: Determinação da média dos dados em questão.
Cálculo do Desvio Padrão: Avaliação da dispersão dos dados em relação à média.
Cálculo do Valor Máximo: Identificação do maior valor presente nos dados.
Cálculo do Valor Mínimo: Identificação do menor valor presente nos dados.

Arquivos
tijucarana.csv: Arquivo CSV com os dados para análise.
backup.sql: Script SQL contendo a estrutura e os dados da tabela analisada.

Como Executar:

1. Instalar o PostgreSQL
Passo 1: Baixar o Instalador do PostgreSQL
Visite o Site Oficial do PostgreSQL:

Acesse PostgreSQL Downloads.
Escolha a Versão e o Instalador:

Clique no link para o instalador do Windows (geralmente disponível através da EnterpriseDB).
Baixe o Instalador:

Selecione a versão mais recente (ou a versão desejada) e clique no link para baixar o instalador.
Passo 2: Instalar o PostgreSQL
Execute o Instalador:

Localize o arquivo baixado e execute o instalador.
Siga o Assistente de Instalação:

Welcome Screen: Clique em Next.
Installation Directory: Escolha o diretório de instalação ou mantenha o padrão e clique em Next.
Select Components: Certifique-se de que PostgreSQL Server, pgAdmin 4, e outras ferramentas desejadas estão selecionadas. Clique em Next.
Data Directory: Escolha o diretório onde os dados do PostgreSQL serão armazenados ou mantenha o padrão. Clique em Next.
Password: Defina a senha do superusuário postgres. Lembre-se desta senha, pois será necessária para acessar o PostgreSQL. Clique em Next.
Port: O padrão é 5432. Mantenha o padrão e clique em Next.
Locale: Selecione a localidade desejada ou mantenha a padrão e clique em Next.
Pre-Installation Summary: Revise as configurações e clique em Next para iniciar a instalação.
Complete a Instalação:

Após a conclusão, clique em Finish.
Passo 3: Configurar o pgAdmin 4
Iniciar o pgAdmin 4:

O pgAdmin 4 deve ser iniciado automaticamente após a instalação. Caso contrário, você pode iniciá-lo manualmente através do menu iniciar ou localizando o atalho na área de trabalho.
Configurar o pgAdmin 4:

Primeira Execução: Na primeira vez que o pgAdmin 4 for iniciado, você será solicitado a definir uma senha mestra. Esta senha é usada para criptografar as senhas de conexão salvas e outras informações sensíveis.
Adicionar Servidor: Clique com o botão direito em Servers no painel esquerdo e selecione Create > Server.
Configurar Conexão:
General: Dê um nome para o servidor.
Connection: Preencha os seguintes campos:
Host: localhost
Port: 5432 (ou a porta que você configurou durante a instalação)
Maintenance database: postgres
Username: postgres
Password: A senha que você definiu durante a instalação do PostgreSQL.
Clique em Save.
Passo 4: Verificar a Instalação
Verificar no pgAdmin 4:

Após adicionar o servidor, você deve conseguir visualizar e acessar o banco de dados PostgreSQL através do pgAdmin 4.
Criar um Banco de Dados:

No pgAdmin 4, clique com o botão direito em Databases e selecione Create > Database.
Dê um nome ao banco de dados e clique em Save.



2. Criar uma Tabela e Importar Dados
Para criar uma tabela no PostgreSQL e importar dados usando o pgAdmin 4, siga estas etapas:

Abra o pgAdmin 4 e conecte-se ao servidor PostgreSQL.

Criar um Novo Banco de Dados (se necessário):

No painel à esquerda, clique com o botão direito em Databases e selecione Create > Database.
Preencha o nome do banco de dados e clique em Save.
Criar uma Nova Tabela:

Expanda o banco de dados que você criou e clique com o botão direito em Tables, depois selecione Create > Table.
Preencha os detalhes da tabela:
Na aba General, forneça um nome para a tabela (tijucarana).
Na aba Columns, adicione as colunas necessárias com os seguintes detalhes:
Nome: cadeia, Tipo: INTEGER.
Nome: data, Tipo: DATE.
Nome: hora, Tipo: TIME WITHOUT TIME ZONE.
Nome: ncclique, Tipo: INTEGER.
Nome: freq, Tipo: INTEGER.
Nome: spl, Tipo: INTEGER.
Nome: dur, Tipo: INTEGER.
Nome: inc, Tipo: INTEGER.
Clique em Save para criar a tabela.
Importar Dados:

Abra o Query Tool (Ferramenta de Consulta) no pgAdmin 4.

Execute o seguinte comando para importar os dados do arquivo CSV para a tabela criada:


COPY public.tijucarana 
FROM 'C:\Tabelas para analisar Biologia\Nova tabela\tijucarana.csv'
DELIMITER ','
CSV HEADER;
3. Executar Análises
Calcular a Média:


SELECT 
    AVG(ncclique) AS media_ncclique,
    AVG(freq) AS media_freq,
    AVG(spl) AS media_spl,
    AVG(dur) AS media_dur,
    AVG(inc) AS media_inc
FROM 
    tijucarana;
Calcular o Desvio Padrão:


SELECT 
    STDDEV(ncclique) AS desvio_padrao_ncclique,
    STDDEV(freq) AS desvio_padrao_freq,
    STDDEV(spl) AS desvio_padrao_spl,
    STDDEV(dur) AS desvio_padrao_dur,
    STDDEV(inc) AS desvio_padrao_inc
FROM 
    tijucarana;
Calcular o Valor Máximo:


SELECT 
    MAX(ncclique) AS valor_maximo_ncclique,
    MAX(freq) AS valor_maximo_freq,
    MAX(spl) AS valor_maximo_spl,
    MAX(dur) AS valor_maximo_dur,
    MAX(inc) AS valor_maximo_inc
FROM 
    tijucarana;
Calcular o Valor Mínimo:


SELECT
    MIN(ncclique) AS valor_minimo_ncclique,
    MIN(freq) AS valor_minimo_freq,
    MIN(spl) AS valor_minimo_spl,
    MIN(dur) AS valor_minimo_dur,
    MIN(inc) AS valor_minimo_inc
FROM
    tijucarana;
    
Contribuições
Se você deseja contribuir para este projeto, sinta-se à vontade para fazer um fork e criar um pull request com suas sugestões ou melhorias.

Licença
Este projeto está licenciado sob a Licença MIT.

Contato
Se você tiver alguma dúvida ou sugestão, entre em contato com Fernando Campos.
