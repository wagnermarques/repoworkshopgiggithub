#+Title: ROTEIRO WORKSHOP GIT/GITHUB

* Entrar no GitHub e pedir pra todos criarem uma conta
  https://github.com/microsoft (entrar no usuário da Microsoft, dizer que os projetos estão lá)
  https://github.com/microsoft/vscode (mostrar que o projeto do vscode tá lá)


* Contextualizar o que é Git e GitHub

* Criar um projeto com um arquivo de texto

C:\Users\Admin>mkdir PASTAPROWORKSHOPGITGITHUB

C:\Users\Admin>cd PASTAPROWORKSHOPGITGITHUB

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *code .*

** Diferenciar uma pasta simples com um repositório local

** transformar pasta simple num repoitorio local (git init)

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git init*
Initialized empty Git repository in C:/Users/Admin/PASTAPROWORKSHOPGITGITHUB/.git/

*mostrar que uma pasta é diferente de um repo local*

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>dir /A
 O volume na unidade C não tem nome.
 O Número de Série do Volume é 9603-80E8

 Pasta de C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB

06/04/2026  19:26    <DIR>          .
06/04/2026  19:21    <DIR>          ..
06/04/2026  19:31               249 index.html
               1 arquivo(s)            249 bytes
               2 pasta(s)   31.322.923.008 bytes disponíveis


C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>dir /A
 O volume na unidade C não tem nome.
 O Número de Série do Volume é 9603-80E8

 Pasta de C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB

06/04/2026  19:33    <DIR>          .
06/04/2026  19:21    <DIR>          ..
06/04/2026  19:33    <DIR>          *.git*
06/04/2026  19:31               249 index.html
               1 arquivo(s)            249 bytes
               3 pasta(s)   31.309.258.752 bytes disponíveis

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>


* Comitar e dar push no código inicial

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git status
On branch main

No commits yet

*Untracked files:* (Explicar arquivos untracked)
  (use "git add <file>..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)

Adicionar o arquivo pro controle do git
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git add index.html*


C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git add index.html

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git status*
On branch main

No commits yet

*Changes to be committed:* (q coisa pra ser comitada)
(use "git rm --cached <file>..." to unstage)
        new file:   index.html


Antes de comitar (Identifique-se)
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git config --global user.name "nomedousuarionogithub"*

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git config --global user.email "emaildousuario@dom.com"*

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB> *git commit -am "criei o aquivo"*
[main (root-commit) 55307de] criei o aquivo
 1 file changed, 11 insertions(+)
 create mode 100644 index.html


 C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git status
On branch main
nothing to commit, working tree clean

depois de criar um repo remoto no github,

mostrar que o repo local ainda nao conhece o repo

remoto


C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git remote -v

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git remote add origin https://github.com/wagnermarques/repoworkshopgiggithub.git

Apos adicionar o remote
o repo local conhece seu lado romote
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>
C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git remote -v
origin  https://github.com/wagnermarques/repoworkshopgiggithub.git (fetch)
origin  https://github.com/wagnermarques/repoworkshopgiggithub.git (push)


agora sim podemos dar um push

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git branch

main

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git push origin main
Username for 'https://github.com': wagnermarques
Password for 'https://wagnermarques@github.com':
remote: Invalid username or token. Password authentication is not supported for Git operations.
fatal: Authentication failed for 'https://github.com/wagnermarques/repoworkshopgiggithub.git/'

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git push origin main
Username for 'https://github.com': wagnermarques
Password for 'https://wagnermarques@github.com':
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 391 bytes | 391.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/wagnermarques/repoworkshopgiggithub.git
 * [new branch]      main -> main


* Mostrar que o código foi para o github

* Mostrar que dá pra trabalhar no projeto usando o vscode do github
  Pra abrir usar a tecla . (Ponto)

* atualizar o repo local com o que foi reito remotamente

C:\Users\Admin\PASTAPROWORKSHOPGITGITHUB>git pull origin main
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 7 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (7/7), 2.07 KiB | 84.00 KiB/s, done.
From https://github.com/wagnermarques/repoworkshopgiggithub
 * branch            main       -> FETCH_HEAD
   55307de..08f2eea  main       -> origin/main
Updating 55307de..08f2eea
Fast-forward
 README.md        | 1 +
 index.html       | 3 ++-
 meujavascript.js | 1 +
 3 files changed, 4 insertions(+), 1 deletion(-)
 create mode 100644 README.md
 create mode 100644 meujavascript.js

  

* dsafadf
