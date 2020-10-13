# Protheus-1.7-23-lobo-guara
Instalação para desenvolvimento e aprendizado do protheus

## Entendendo arquitetura TOTVS PROTHEUS 12

A linha TOTVS Protheus utiliza a tecnologia By You, a qual opera sobre a estrutura Client/Server nível 5, em que se destacam 3 camadas de aplicação:

*    **Client**: responsável pela apresentação da aplicação (Front-End).
*   **ApplicationServer** : encarregada de todo processamento das regras de negócio.
*   **Banco de Dados**: cuida do gerenciamento dos dados no Sistema.  

O Application Server é um middleware preparado para a arquitetura SOA, e conceito de distribuição de software online SaaS, atuante como um intérprete e facilitador, “traduzindo” e conectando os comandos da linguagem com o Framework da linha TOTVS Protheus. Além disto, esta camada funciona sobre um ambiente de balanceamento de carga. O Framework da Linha Microsiga fornece diversos facilitadores e aceleradores de desenvolvimento baseados na arquitetura MVC.

## Passo 1: Instalação do banco de dados

   **Caso você tenha alguma instalação do SQL SERVER em sua maquina**  basta criar um banco de dados vazio chamado TOTVS12 e uma conexão ODBC  64bits e pular para o passo 2.
    O Banco de Dados escolhido é o SQL Server Express Edition 2017 **É possivel utilizar outras versoes 2012 ou posteriores** caso queira outro banco eu aconselho acessar o link TDN. Para efetuar o download basta navegar no seguinte link SQL SERVER ou pesquisar no Google SQL Server Express.

    Após efetuar o download pelo link e executar o programa SQLServer2017-SSEI-Expr.exe,:
    ![aparecera a seguinte imagem](.\)
