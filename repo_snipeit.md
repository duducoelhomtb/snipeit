
Procedimento para instalação do Snipe-IT no Windows;

Programas Necessários para rodar o Snipe it;

Xampp; https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/8.2.12/xampp-windows-x64-8.2.12-0-VS16-installer.exe

Banco de dados (Mysql ou Maria DB);
PHP =>8.1.0 ou superior tanto pra windows ou linux.

Composer; https://getcomposer.org/Composer-Setup.exe

Notepad ++; https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v8.7.6/npp.8.7.6.Installer.x64.exe

Snipe IT; https://github.com/snipe/snipe-it/archive/refs/tags/v8.0.4.zip

Passo a Passo (Seguir fielmente o passo a passo).

1º Passo;
Instalar o Xampp da maneira normal no caminho c:\xampp.

2º Passo;
Baixar o pacote do SNIPE-IT e extrair em c:\xampp\htdocs\;
Interessante renomear a pasta para snipeit;

![image](https://github.com/user-attachments/assets/d2300585-49be-43a5-b7e1-df68d9b0566a).

3º Passo;
Instalar o Composer para todos os usuários ;

Executar o instalador;

Clicar em (instalar para todos os usuários);

Clicar em sim;

Não marcar DEveloper mode e clicar em next;

Na próxima tela observar que ele vai trazer o caminho do php já instalado no composer;

Marcar a opção "add this php to your path?" e clicar em next;

Next ;

Install;

Next;

Finish.

4ºPasso;
Instalar o notepad ++;
Modo normal de instalação.

5ºPasso;
Ver A versão do php no prompt dentro do diretório do snipeit;

dentro do prompt de comando;

acessar o caminho;

cd c:\xampp\htdocs\snipeit;

php -v;

![image](https://github.com/user-attachments/assets/6edf03b8-7951-43d1-9871-0543999fb997).

6ªPasso;

Verificar a versão do composer dentro do mesmo diretório;

composer -v;

![image](https://github.com/user-attachments/assets/65b55cc5-492d-4e10-98b4-0e6b625f2f66).

7ºPasso;

Rodar o comando do composer install ainda dentro do diretório;

composer install --no-dev --prefer-source;

vai retornar com o seguinte erro;

"your lock file does not contain a compatible set of packages.Please run composer update.";

Essa falha ocorrerá porque as extensões gd, sodium e zip estão inabilitadas.

8ºPasso;

Habilitar as extensões;

gd,sodium e zip;

Abrir o xampp e clicar e no modulo do APACHE clicar em config;

Abrir o arquivo do PHP.ini;

Dentro do bloco de notas procurar pelas extensões comentadas;

remover o ponto e vírgula para habilitar as extensoes GD, SODIUM e ZIP apenas, fechar e salvar o arquivo de texto;

![image](https://github.com/user-attachments/assets/8f97f3ef-c755-48c3-bc21-2a3f0eec3d88);

![image](https://github.com/user-attachments/assets/2f4d968d-83eb-4444-82f5-91aae5c9f96e).

9º Passo;

Rodar o comando novamente dentro do diretório;

composer install --no-dev --prefer-source;

Aguardar o processo, pois é demorado.

10ºPasso;

Configurar a URL do SnipeIT;

Acessar c:\xampp\htdocs\snipeit;

copiar o arquivo .env.example e colar dentro do mesmo diretório;

Renomear o arquivo copiado para .env e clicar em SIM quando aparecer o alerta "se a extensão de arquivo for alterada o arquivo poderá se tornar...";

Editar o arquivo .env com o Notepad;

alterar a linha APP URL;

APP_URL=http://127.0.0.1:8000 clicar em salvar;

Para Gerar a Chave da Aplicação precisa rodar o seguinte comando dentro do promtp;

Não necessita fechar o notepad;

Rodar o comando: php artisan key:generate;

Assim que rodar o comando acima, vai retornar a seguinte mensagem:;

Are you sure you want to run this command?;

colocar YES;

Ao voltar pro notepad vai retornar com a seguinte mensage:;

Este arquivo foi modificado por outro programa, deseja recarregalo?;

Clicar em sim e observar se a linha "APP_KEY" que fica acima de APP_URL mudou.

11ºPAsso;

Acessar o PHp My admin;

no painel de controle do xampp;

startar o apache e o mysql;

liberar o firewall caso apareça os alertas tanto para o apache quanto para o mysql.

12ºPasso;

abrir o navegador e acessar o db;

http://localhost;

clica em phpmyadmin;

clicar em novo nomear com snipeit ou qualquer outro nome;

Após criar o arquivo ;

configurar o banco dentro do arquivo .env;

Alterar as linhas;

DB_DATABASE=snipeit;

DB_USERNAME=root;

DB_PASSWORD=pode deixar em branco ou a sua escolha;

após as alterações clicar em salvar.

13ºPAsso;

Como a aplicação é baseada em laravael, precisa Rodar o comando php artisan serve;

dentro do diretorio c:\xamp\htdocs\snipeit> php artisan serve.

14ºPasso;

Abrir o navegador e acessar;

127.0.0.1:8000;

Clicar em next:create database tables;

next: create user;

Preencher as informações de acordo com o seu projeto;

Site name, moeda, linguagem, nome, sobrenome, etc, usuario e senha;

clicar em next:save User.






