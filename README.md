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

Após isso iremos abrir o nosso banco de dados através do SQL Server Management Studio, na minha maquina estava instalado o 2012, segue link para download.  Feita a instalação iremos informar localhost\SQLEXPRESS em nome do servidor e na autenticação deixaremos a opção “Autenticação do Windows”

1. [Microsoft® SQL Server® 2012 Express](https://www.microsoft.com/pt-br/download/details.aspx?id=29062&ranMID=24542&ranEAID=TnL5HPStwNw&ranSiteID=TnL5HPStwNw-Tw4bOq6_8wxpfO5dZTfzZQ&epi=TnL5HPStwNw-Tw4bOq6_8wxpfO5dZTfzZQ&irgwc=1&OCID=AID2000142_aff_7593_1243925&tduid=%28ir__vvhkeoklh9kfqn99kk0sohzjxu2xs2dix2dtccz300%29%287593%29%281243925%29%28TnL5HPStwNw-Tw4bOq6_8wxpfO5dZTfzZQ%29%28%29&irclickid=_vvhkeoklh9kfqn99kk0sohzjxu2xs2dix2dtccz300)
2. [SSMS 18.6 **Versão Atualizada**](https://docs.microsoft.com/pt-br/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-4.png?w=660)


Se tudo der certo irá aparecer a seguinte tela


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-5.png?w=660)


Dentro da pasta Banco de Dados iremos criar o banco **“TOTVS12”** de forma bem padrão **para criar o banco basta clicar com o botão direito do mouse em cima de banco de dados e selecionar novo banco**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-6.png?w=660)


Com o banco configurado com sucesso, agora é hora de criarmos uma conexão ODBC com o nosso querido banco de dados **“TOTVS12”** para o **TOTVS DBACESS**, Vamos acessa o _painel de controle_ > _Ferramentas Administrativas:_


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-7.png?w=660)

Logo em seguida a opção **“Fonte de Dados ODBC (64bits)”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-8.png?w=660)


Após aberto, clicar em **“Adicionar”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-9.png?w=660)


Iremos selecionar a opção **“SQL Server”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-10.png?w=660)


Nessa parte temos que informar o nome para a conexão ODBC, eu utilizei  **“TOTVS12”** o mesmo do banco de dados porem você pode colocar o nome que mais lhe agrada como **“Producao ou desenv”** já na instância você deve seguir o padrão criado na instalação do banco o meu foi **“localhost\SQLEXPRESS01”** ou **“localhost\SQLEXPRESS”** que é mais comun


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-11.png?w=660)


Nessa parte iremos informar o usuário de autenticação do banco. Na instalação básica é utilizado o usuário do Windows para ser o administrador do banco (_resumindo, logou com esse usuário na maquina Pode Realizar qualquer alteração dentro do banco de dados_), então é só selecionar **“Autenticação WINDOWS NT”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-12.png?w=660)


Após clicar em avançar iremos marcar a opção **“Alterar o banco de dados padrão para”** e selecionaremos o nosso querido banco de dados **“TOTVS12”** e caso não estejam marcadas as opções favor selecionar **“Usar identificadores entre aspas ANSI”**  e  **“Usar nulos, preenchimentos e avisos ANSI”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-13.png?w=660)


Irá aparecer uma tela revisando todos os dados de conexão ODBC


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-14.png?w=660)

Vamos clicar em **“Testar fonte de dados”** e se aparecer a seguinte mensagem _TESTES CONCLUIDOS COM ÊXITO!_ indica que você fez tudo corretamente


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-15.png?w=660)


Clicamos em OK e depois OK e aparecerá a nossa queria conexão ODBC, favor guardar o nome dela  porque usaremos no **TOTVS DBACESS**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-16.png)


### Passo 1 concluido Agora iremos para a parte divertida


# Passo 2: Configuração do nosso TOTVS DBACESS 64bits

Bom para começarmos sugiro que você baixe o pacote que montei do TOTVS ERP, onde contem tudo para a gente configurar o ERP. O arquivo é um pouco pesado “799Mb” zipado em winrar e você não precisa ter uma conta do gmail. (TOTVS Protheus 12.1.17) ou (TOTVS Protheus 12.1.23)

1. [TOTVS Protheus 12.1.17](https://drive.google.com/file/d/1nuhgcclm-DPwm4Ps4hQuLkvpdOBgd5Ik/view?usp=sharing)
2. [TOTVS Protheus 12.1.23]()



#### Observação


1. Descompactar a pasta **TOTVS12** a pasta se encontra dentro da pasta TOTVS12_1_17 dependendo da forma ou do programa que utilizar
2. O protheus só ira funcionar se estiver em **"C:\"**



Após ter baixado o arquivo favor descompactar e copiar a pasta **“TOTVS12”** para o **“C:\”.** Com os arquivos extraidos teremos a seguinte visão

1. protheus
2. protheus_data
3. Totvs Dbacess x64


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-18-e1532203987266.png?w=660)


Abriremos a pasta **“Totvs DBAccess x64”** e dentro dela teremos o executável **“TOTVS 12 – DBAccess64.exe”** onde criaremos um atalho para execução em console, basta clicar com o botão direito do mouse e selecionar **criar atalho**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-19.png?w=660)


Com o atalho criado iremos clicar com o botão direito do mouse em cima de **“TOTVS 12 – DBAccess64.exe – Atalho”** e selecionar a opção **propriedades**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-20.png?w=660)

Na tela de propriedades na opção **“Destino:”** iremos ate o final após as aspas duplas e incluiremos o parâmetro do MS-DOS _windows_ conhecido como **“-CONSOLE”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-21.png?w=660)


Após clicar em **“OK”** basta executar dois cliques no atalho criado e aparecera a mensagem do **“Windows Defender Firewall”**. Na qual devemos permitir a comunicação das redes para o Dbacess ser visto pelo Appserver e a comunicação ODBC, basta copiar a tela abaixo e clicar em **“permitir acesso”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-22.png?w=660)


É temos o nosso DbAcess Online ✅


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-23.png?w=660)


Logo em seguida iremos minimizar a tela do DbAcess64 e executaremos um duplo clique em **“DBMonitor.exe”**, aparecerá a tela de conexão do monitor onde informaremos o Servidor e a Porta. **“Servidor:localhost”** , **“Porta:7890”** depois é só clicar **“OK”** 


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-25.png?w=660)


A senha para logar é **“Usuario:admin”** e a senha pode deixar em branco e clicar **“OK”** (lembrando que em Usuario o **“admin”** é minúsculo):


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-24.png?w=660)


Informando a identificação aparecerá a tela inicial do **DBMonitor**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-26.png?w=660)

 lembra que a gente efetuou uma forma de conexão ODBC 64bits onde a autenticação é feita pelo usuário logado ? Com isso não precisamos ir em **“Configurações”** e depois **“Microsoft SQL”**  para configurar usuário e senha do banco. (Caso você já tenha o banco de dados instalado basta seguir os seguintes passos. Clicar na aba **“Configurações”** e depois na aba **“Microsoft SQL”** e depois no botão **“Novo”** e informar o nome igual da conexão ODBC 64bits e depois na caixa Usuário informar o nome e senha do usuário do banco de dados. **”_dica nome_ e usuário é o mesmo que você usa para acessar o SQL Server Management Studio”**)

Após isso iremos acessar aba **“Assistentes”** para testar a conexão ODBC


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-29.png?w=660)


Vamos clicar em **“Validação de Conexão”** e depois em **“Avançar”** e aparecerá a opção para escolhermos o banco de dados **“Microsoft SQL”**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-30.png?w=660)


Após clicar em **“Avançar”** vamos escrever o nome da instância criada na conexão ODBC 64bits, **“TOTVS12”:**


![](https://depurandoadvpl.files.wordpress.com/2018/01/foto-321.png?w=660)








