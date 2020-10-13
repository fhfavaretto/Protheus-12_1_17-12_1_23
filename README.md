# Protheus-1.7-23-lobo-guara

## Entendendo arquitetura TOTVS PROTHEUS 12

 1. **Client**: responsável pela apresentação da aplicação (Front-End).
 2. **Application Server** : encarregada de todo processamento das regras de negócio.
 3. **Banco de Dados**: cuida do gerenciamento dos dados no Sistema.

O Application Server é um middleware preparado para a arquitetura SOA, e conceito de distribuição de software online SaaS, atuante como um intérprete e facilitador, “traduzindo” e conectando os comandos da linguagem com o Framework da linha TOTVS Protheus. Além disto, esta camada funciona sobre um ambiente de balanceamento de carga. O Framework da Linha Microsiga fornece diversos facilitadores e aceleradores de desenvolvimento baseados na arquitetura MVC.

### Passo 1: Instalação do banco de dados

_Caso você tenha alguma instalação do SQL SERVER em sua maquina  basta criar um banco de dados vazio chamado TOTVS12 e uma conexão ODBC  64bits e pular para o passo 2_ :).

O Banco de Dados escolhido é o SQL Server Express Edition 2017 caso queira outro banco eu aconselho acessar o link TDN. Para efetuar o download basta navegar no seguinte link SQL SERVER ou pesquisar no Google SQL Server Express.

1. [TDN](https://tdn.totvs.com/display/public/PROT/Linha+Microsiga+Protheus+Home)
2. [SQL SERVER](https://www.microsoft.com/pt-br/sql-server/sql-server-2019)

Após efetuar o download pelo link e executar o programa SQLServer2017-SSEI-Expr.exe, aparecera a seguinte imagem

![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-1.png?w=660)

**A forma de instalação fica a seu critério eu utilizei o “Básico”**

Logo em seguida é perguntado o diretório para instalação do Banco de dados, eu deixei padrão porem fica a seu critério:

![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-2.png?w=660)

Após a instalação básica ser concluída, aparecera as informações do seu banco de dados instalado. Minha instalação ficou assim, instância é  **SQLEXPRESS**  e o administrador sql é meu usuário de login do WINDOWS:  

![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-32.png?w=660)



