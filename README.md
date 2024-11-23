<h1 align="center"> Projeto de Controle de Funcionários - Gerência de Projetos 2024.2 </h1>

Este README fornece um passo a passo detalhado para configurar e instalar as ferramentas necessárias para rodar o Projeto de Controle de Funcionários, desenvolvido como parte da disciplina de Gerência de Projetos (2024.2). O sistema é projetado para facilitar a gestão de colaboradores, oferecendo funcionalidades como autenticação, cadastro, edição, geração de relatórios e visualização de gráficos salariais.

Certifique-se de seguir as etapas na ordem indicada para garantir o funcionamento correto do projeto.

### O sistema utiliza

- JDK - Java Development Kit
- JRE - Java Runtime Environment
- JVM - Máquina virtual Java
- Banco de dados - PostgreSQL
- Servidor de Aplicação, servlets ou web container - Tomcat
- IDE de sua preferência. No nosso caso, utilizamos a IDE Eclipse

<h1 align="center"> Guia de Instalação </h1>

### Passo a Passo: Instalação do JDK

1. **Baixar o JDK**  
   - Acesse o site oficial da Oracle: [Oracle JDK Downloads](https://www.oracle.com/java/technologies/javase-downloads.html).  
   - Escolha a versão do JDK compatível com o seu sistema operacional (Windows, macOS, Linux).  

2. **Instalar o JDK**  
   - Após o download, abra o instalador.  
   - Siga as instruções na tela para instalar o JDK.  
   - Durante a instalação, anote o caminho de instalação (geralmente algo como `C:\Program Files\Java\jdk-XX.X.X`).  

3. **Configurar a Variável de Ambiente `JAVA_HOME`**  
   - **No Windows:**  
     1. Abra o **Painel de Controle** e vá para **Sistema > Configurações Avançadas do Sistema**.  
     2. Clique em **Variáveis de Ambiente**.  
     3. Em **Variáveis do Sistema**, clique em **Novo** e adicione:  
        - **Nome:** `JAVA_HOME`  
        - **Valor:** Caminho para o diretório do JDK (ex.: `C:\Program Files\Java\jdk-XX.X.X`).  
     4. Encontre a variável `Path` nas **Variáveis do Sistema**, clique em **Editar** e adicione:  
        ```
        %JAVA_HOME%\bin
        ```  

   - **No macOS/Linux:**  
     1. Abra o terminal e edite o arquivo `~/.bashrc` (ou `~/.zshrc`):  
        ```bash
        export JAVA_HOME=/caminho/para/o/jdk
        export PATH=$JAVA_HOME/bin:$PATH
        ```  
     2. Salve o arquivo e recarregue o terminal:  
        ```bash
        source ~/.bashrc
        ```  

4. **Verificar a Instalação**  
   - Abra um terminal ou prompt de comando e digite:  
     ```bash
     java -version
     ```  
   - O resultado deve mostrar a versão do JDK instalada.  

5. **Pronto!**  
   Agora, o JDK está configurado no seu sistema e pronto para ser utilizado no projeto.

<h1 align="center"></h1>

### Passo a Passo: Instalação do PostgreSQL e pgAdmin

#### 1. **Baixar o PostgreSQL**
   - Acesse o site oficial: [PostgreSQL Downloads](https://www.postgresql.org/download/).  
   - Escolha o sistema operacional (Windows, macOS, Linux) e siga as instruções para baixar o instalador.

#### 2. **Instalar o PostgreSQL**
   - Execute o instalador baixado.  
   - Siga as etapas de instalação:  
     1. Escolha o local de instalação.  
     2. Selecione os componentes (certifique-se de que o **pgAdmin** esteja marcado).  
     3. Defina a senha do usuário padrão **postgres** (anote esta senha, pois será usada para acessar o banco).  
     4. Escolha a porta padrão do servidor (geralmente **5432**).  
   - Conclua a instalação.  

#### 3. **Configurar o PostgreSQL**
   - Abra o **pgAdmin** (incluído no instalador).  
   - Realize o login utilizando:  
     - **Usuário:** `postgres`  
     - **Senha:** `admin`
   - Para criar um novo banco de dados:  
     1. Clique com o botão direito em **Databases** e selecione **Create > Database**.  
     2. Preencha o nome do banco e clique em **Save**.  

#### 4. **Configurar a Variável de Ambiente (Opcional)**
   - Para facilitar o acesso ao cliente de linha de comando do PostgreSQL, adicione o caminho para a pasta `bin` nas variáveis de ambiente:  
     - **Caminho típico no Windows:**  
       ```
       C:\Program Files\PostgreSQL\XX\bin
       ```  

#### 5. **Verificar a Instalação**
   - Abra um terminal ou prompt de comando e digite:  
     ```bash
     psql --version
     ```  
   - O resultado deve exibir a versão do PostgreSQL instalada.  

#### 6. **Pronto!**
   O PostgreSQL e o pgAdmin estão instalados e configurados. Agora você pode utilizá-los para gerenciar o banco de dados do projeto.

### Passo a Passo: Instalação do Eclipse IDE for Java EE

<h1 align="center"></h1>

#### 1. **Baixar o Eclipse**
   - Acesse o site oficial: [Eclipse Downloads](https://www.eclipse.org/downloads/).  
   - Clique em **Download** e escolha a versão **Eclipse IDE for Enterprise Java and Web Developers** (Java EE).  

#### 2. **Instalar o Eclipse**
   - Após o download, extraia o arquivo (se necessário).  
   - Execute o instalador do Eclipse.  
   - Escolha a opção **Eclipse IDE for Enterprise Java and Web Developers**.  
   - Selecione o local de instalação (ex.: `C:\Eclipse`) e conclua a instalação.  

#### 3. **Configurar o JDK no Eclipse**
   - Certifique-se de que o JDK está instalado no seu sistema (caso não esteja, siga o passo a passo para instalar o JDK).  
   - Abra o Eclipse e configure o JDK:  
     1. Vá em **Window > Preferences** (ou **Eclipse > Preferences** no macOS).  
     2. Navegue até **Java > Installed JREs**.  
     3. Clique em **Add**, selecione **Standard VM** e clique em **Next**.  
     4. Insira o caminho para o JDK (ex.: `C:\Program Files\Java\jdk-XX.X.X`) e clique em **Finish**.  

#### 4. **Configurar o Workspace**
   - Ao iniciar o Eclipse pela primeira vez, escolha o local do **workspace** (diretório onde os projetos serão armazenados).  
   - É recomendado criar uma pasta dedicada, como:  
     ```
     C:\Workspace\ProjetoControleFuncionarios
     ```

#### 5. **Pronto!**
   O Eclipse IDE está instalado e configurado, pronto para o desenvolvimento do projeto de controle de funcionários.

<h1 align="center"> Passo a Passo: Configuração do Projeto com Arquivo ZIP </h1>

Este guia explica como configurar o **Projeto de Controle de Funcionários** utilizando os arquivos fornecidos em um arquivo ZIP. O ZIP contém:  
- A pasta do projeto completo [Controle de Funcionário](https://drive.google.com/drive/u/1/folders/1bvFyhLC-0j2I8lxxb-GNyCGiK1G1G3vH). 
- O servidor **Apache Tomcat**.  
- Um arquivo de backup do banco de dados PostgreSQL.  

#### 1. **Descompactar o Arquivo ZIP**  
   - Baixe o arquivo ZIP fornecido e salve-o em um local de fácil acesso.  
   - Clique com o botão direito no arquivo ZIP e selecione **Extrair Aqui** (ou use ferramentas como WinRAR, 7-Zip ou nativamente no sistema operacional).  
   - Após a extração, você verá as seguintes pastas e arquivos:  
     - `/ProjetoControleFuncionarios` (pasta do projeto para o Eclipse).  
     - `/ApacheTomcat` (servidor Tomcat).  
     - `backup.sql` (arquivo de backup do banco de dados).  

#### 2. **Mover o Apache Tomcat para a Raiz do Disco**  
   - Localize a pasta **ApacheTomcat** extraída.  
   - Copie ou mova a pasta para a raiz do disco principal (ex.: `C:\ApacheTomcat`).  

#### 3. **Abrir o Projeto no Eclipse**  
   - Abra o **Eclipse IDE**.  
   - Selecione o workspace onde deseja importar o projeto (pode ser o padrão ou crie um novo).  
   - Importe o projeto:  
     1. Vá em **File > Import > WAR File**.  
     3. Clique em **Finish** para importar o projeto.  

#### 4. **Configurar o Apache Tomcat no Eclipse**  
   - Adicione o Tomcat como servidor no Eclipse:  
     1. Vá em **Window > Preferences > Server > Runtime Environments**.  
     2. Clique em **Add**, selecione a versão correspondente do Tomcat e clique em **Next**.  
     3. Navegue até o diretório onde o Tomcat foi movido (`C:\ApacheTomcat`) e clique em **Finish**.  
     4. Adicione o servidor no painel de servidores: **File > New > Server**, selecione o Tomcat configurado e clique em **Finish**.  

#### 5. **Restaurar o Backup do Banco de Dados pelo pgAdmin**  
   - Abra o **pgAdmin** e conecte-se ao servidor PostgreSQL utilizando o usuário `postgres` e sua senha.  
   - Crie um novo banco de dados:  
     1. Clique com o botão direito em **Databases** e selecione **Create > Database**.  
     2. Insira um nome `controle_funcionario` e clique em **Save**.  
   - Restaure o backup:  
     1. Clique com o botão direito no banco de dados recém-criado e selecione **Restore**.  
     2. No campo **Filename**, localize o arquivo `backup.sql` extraído do ZIP.  
     3. Clique em **Restore** para carregar os dados no banco de dados, em seguida botão direito e Refresh para atualizar as dependências do pom.xml.  

#### 6. **Testar o Projeto**  
   - Certifique-se de que o Tomcat e o PostgreSQL estão em execução.  
   - No Eclipse, clique com o botão direito no projeto, vá em **Run As > Run on Server** e selecione o Tomcat configurado.  
   - Abra o navegador e acesse:  
     ```
     http://localhost:8080/ProjetoControleFuncionarios
     ```  
   - Verifique se o sistema está funcionando corretamente.  

#### 7. **Pronto!**  
   O projeto está configurado e pronto para uso. Caso tenha dúvidas ou encontre problemas, verifique novamente as etapas ou entre em contato com o grupo responsável.

