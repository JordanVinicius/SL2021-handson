# Git Assignment

**INDIVIDUAL**

**Entrega**: 23-Mar-21

Copie o arquivo em um repositorio que seja seu e coloque as respostas nas caixas abaixo
Abra uma issue nesse repositório aqui indicando o link para o arquivo no seu repo.

### Entenda o repositorio
Baixe o arquivo [handson.zip] (handson.zip) e descompacte-o
A pasta handson é um repositório git. Usando a linha de comando, altere o diretório para "handson/"


As caixas vazias
```

```
representam o conteúdo que você precisa preencher e postar em seu repositório privado

1. Descreva qual é a saída dos seguintes comandos
    -  `git branch` 
    -  `git checkout BRANCH_NAME` (USE THE NAME OF AN EXISTING BRANCH)
    -  `git log --decorate`

```
executando "git branch"
Jordan@DESKTOP-NOFQJGL MINGW64 /e/mestrado/ppgcc/1_desenvolvimento_de_software_livre/handson (master)
$ git branch
  feature-foo
* master

executando "git checkout feature-foo"
Jordan@DESKTOP-NOFQJGL MINGW64 /e/mestrado/ppgcc/1_desenvolvimento_de_software_livre/handson (master)
$ git checkout feature-foo
Switched to branch 'feature-foo'

executando git log --decorate
Jordan@DESKTOP-NOFQJGL MINGW64 /e/mestrado/ppgcc/1_desenvolvimento_de_software_livre/handson (feature-foo)
$ git log --decorate
commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:29:22 2018 -0700

    Adding header of method foo()

commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:27:16 2018 -0700

    Adding class A skeleton

commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:26:44 2018 -0700

    Creating all files (all empty)

```

2. Tente usar `git log --graph --all`. O que acontece?
```
AQUI É "DESENHADO" COM | COMO SE FOSSE UMA LINHA DO TEMPO DO PROJETO... CONTENDO OS COMITS (BRANCHS E MERGES) DE FORMA QUE FACILITE VISUALMENTE A IDENTIFICAÇÃO DESTES EVENTOS.

Jordan@DESKTOP-NOFQJGL MINGW64 /e/mestrado/ppgcc/1_desenvolvimento_de_software_livre/handson (feature-foo)
$ git log --graph --all
* commit f67f266cf420735187053f10d32e2c0f7cbc5a43 (master)
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:30:05 2018 -0700
|
|     Adding class B skeleton
|
| * commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Fri Aug 24 15:29:22 2018 -0700
|
|       Adding header of method foo()
|
* commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:27:16 2018 -0700
|
|     Adding class A skeleton
|
* commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Fri Aug 24 15:26:44 2018 -0700

      Creating all files (all empty)
```

3. Use `git diff BRANCH_NAME`  para ver as diferenças de um ramo e do ramo atual.
   Sumarize as diferenças do master e do outro ramo.

```
Jordan@DESKTOP-NOFQJGL MINGW64 /e/mestrado/ppgcc/1_desenvolvimento_de_software_livre/handson (feature-foo)
$ git diff master
diff --git a/A.java b/A.java
index 3ea227e..674b8ce 100644
--- a/A.java
+++ b/A.java
@@ -1,4 +1,7 @@
 public class A {
-
+
+   public void foo() {
+
+   }

 }
diff --git a/B.java b/B.java
index ae64e6b..e69de29 100644
--- a/B.java
+++ b/B.java
@@ -1,4 +0,0 @@
-public class B {
-
-
-}

```

4. Escreva uma sequencia de comandos para mesclar o ramo não-master no `master`

```
$ git checkout master
Switched to branch 'master'

$ git merge feature-foo
Merge made by the 'recursive' strategy.
 A.java | 5 ++++-
 1 file changed, 4 insertions(+), 1 deletion(-)
```


5. Escreva um comando (ou sequência) para (i) criar um novo ramo chamado `math` (do` master`)
e (ii) mudar para este ramo

```
$ git checkout -b math
Switched to a new branch 'math'

```
   
6. Edite B.java adicionando o código abaixo ao conteúdo do arquivo
```java
System.out.println("I know math, look:")
System.out.println(2+2)
```

7. Escreva o comando (ou sequencia) para realizar o commit de suas mudanças
```
$ git remote add origin https://github.com/JordanVinicius/SL2021-handson.git

$ git commit -a -m "passo 7 do exercicio"
[math cb140af] passo 7 do exercicio
 1 file changed, 2 insertions(+), 1 deletion(-)

```

8. Volte para o branch `master` e mude B.java adicionando o seguinte código-fonte (confirme sua mudança para` master`):
```java
System.out.println("Hello World")

$ git checkout master
Switched to branch 'master'
```

9. Escreva uma sequência de comando para mesclar o branch `math` em` master` e descreva o que aconteceu
```
$ git commit -a -m "passo 9 do exercicio"
[master 4066dce] passo 9 do exercicio
 1 file changed, 1 insertion(+), 1 deletion(-)

$ git merge math
Auto-merging B.java
CONFLICT (content): Merge conflict in B.java
Automatic merge failed; fix conflicts and then commit the result.


```
   
10. Escreva um conjunto de comandos para abortar a mesclagem
```
$ git merge --abort

```
   
11. Agora repita o item 9, mas prossiga com a mesclagem manual (Editando B.java). Todas as funções implementadas são necessárias. Explique o seu procedimento
```
$ git merge math
Auto-merging B.java
CONFLICT (content): Merge conflict in B.java
Automatic merge failed; fix conflicts and then commit the result.

$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   B.java

no changes added to commit (use "git add" and/or "git commit -a")


$ git commit -a -m "passo 11 do exercicio"
[master 51bf05f] passo 11 do exercicio


```

12. Escreva um comando (ou conjunto de comandos) para prosseguir com a mesclagem e atualizar o branch `master`
```
$ git push -u origin master
Enumerating objects: 23, done.
Counting objects: 100% (23/23), done.
Delta compression using up to 8 threads
Compressing objects: 100% (20/20), done.
Writing objects: 100% (23/23), 2.08 KiB | 425.00 KiB/s, done.
Total 23 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/JordanVinicius/SL2021-handson.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.


```


