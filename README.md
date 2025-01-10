# Configurando um ataque phishing no Kali Linux para captura de senhas do Facebook

## Aviso Importante
Esse guia é só para aprendizado ou testes autorizados. Fazer isso sem permissão é errado e pode trazer problemas sérios, como processos judiciais.

### Ferramentas necessárias

Para esta simulação, você precisará do sistema operacional abaixo instalado e configurado em um ambiente de teste virtual:

- *Kali Linux*: Sistema operacional especializado em testes de segurança e penetração.
- *SET Toolkit* (Social-Engineer Toolkit): ferramenta pré-instalada no Kali Linux para engenharia social.

### Passo a Passo

**1. Ativando o modo administrador (root)**  
Para realizar o teste, você precisará de acesso de administrador (root) do Kali Linux. Dessa forma, terá as permissões necessárias para executar os comandos:
- Abra o terminal;
- Digite: **sudo su** pressione a tecla ENTER e informe a senha (caso seja solicitado).
<p>
  <img width="259" height="79" src="images/01-login.png">
</p>  

**2. Executando a ferramenta SET Toolkit**  
Essa ferramenta open source serve para auxiliar os profissionais de segurança a realizar testes de engenharia social:  
- No terminal, digite: **setoolkit** e pressione a tecla ENTER;
<p>
  <img width="848" height="288" src="images/02-setoolkit.png">
</p>  

- *__Nota:__* se aparecer uma mensagem pedindo confirmação, **digite Y** e pressione a tecla ENTER;
- No menu que será exibido, digite **1** e pressione a tecla ENTER. Essa opção seleciona o **Social Engineering Attacks** (ataques de engenharia social);  

<p>
  <img width="326" height="356" src="images/03-set-option1.png">
</p> 

- No próximo menu, selecione o vetor de ataque que refere-se a como o phishing irá funcionar. Para este teste, digite **2** (Web Site Attack Vectors) e pressione a tecla ENTER;

<p>
  <img width="326" height="346" src="images/04-03-set-option2.png">
</p> 

- No próximo menu, selecione o método de captura que será como o phishing pegará as informações da vítica. Para este teste, digite **3** (Credential Harvester Attack Method) e pressione a tecla ENTER;

<p>
  <img width="953" height="307" src="images/05-set-option3.png">
</p> 

- No próximo menu, digite **2** (Site Cloner) e pressione a tecla ENTER;

<p>
  <img width="546" height="264" src="images/06-set-option2.png">
</p> 

- Será necessário informar o endereço IP da máquina que está executando o Kali Linux. Note que, o endereço IP da máquina já será informado no prompt (**para descobrir o endereço IP no Kali Linux vide o passo 3**). Para confirmar o endereço IP exibido, pressione a tecla ENTER;

<p>
  <img width="661" height="319" src="images/07-confirm-ip.png">
</p> 

- No prompt exibido, digite o site a ser clonado, nesse caso: **http://www.facebook.com** pressione a tecla ENTER. A ferramenta SET Toolkit criará uma cópia do site e começará a capturar as informações das conexões recebidas para este site clonado assim como, os dados de login e senha das pessoas que digitarem na tela de login.

<p>
  <img width="553" height="66" src="images/08-enter-url.png">
</p> 
<p>
  <img width="882" height="356" src="images/09-captura-dados.png">
</p> 

**3. Descobrindo o endereço IP da sua máquina Kali Linux**  
- Abra um novo terminal;
- Na tela exibida, digite **ifconfig** e pressione a tecla ENTER;
- Anote o número que será exibido ao lado de *INET*.

<p>
  <img width="663" height="449" src="images/ifconfig.png">
</p> 

**4. Realizando um teste**  
- Utilizando outra máquina, abra qualquer navegador (de preferência utilize uma guia anônima) e na barra de endereços digite o endereço IP da sua máquina Kali Linux;
- Será exibida a "tela de login" do site clonado;

<p>
  <img src="images/teste-navegador.png">
</p> 

- Neste momento, se consultar o terminal no Kali Linux perceberá que o endereço IP do equipamento que acessou o site clonado será apresentado e as demais informações como login e senha serão capturadas assim que o usuário realizar a tentativa de login no site.

<p>
  <img width="618" height="387" src="images/captura-dados.png">
</p> 

### Outras informações
- Para concluir o processo de captura da ferramenta SET Toolkit, **pressione as teclas CTRL + C e em seguida, pressione a tecla ENTER. Um arquivo XML será gerado para análise posterior**;

<p>
  <img width="619" height="182" src="images/encerrar-captura-setoolkit.png">
</p> 

- Para fechar a ferramenta SET Toolkit, **digite 99 e pressione a tecla ENTER até retornar ao terminal**.

<p>
  <img width="405" height="238" src="images/fechar-setoolkit.png">
</p> 
