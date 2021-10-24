Reference
        ↓ -> https://git-scm.com/docs

       git download -> https://git-scm.com/download/linux

 Resumo 
   
00 Git configurações / instalação
  * install   https://git-scm.com/downloads
  
	* Global

     git config --global user.name "nome aqui"	 
     git config --global user.email "email aqui"
	   git config --global core.editor "nome do editor usado"
     
	* Local <no repositorio especifico>

		 git config user.name "nome aqui"	 
     git config user.email "email aqui"
	   git config core.editor "nome do editor usado"

  * Revelando as configurações 

	  git config user.name  -> mostra o nome do usuário configurado!
    git config user.email -> mostra o email do usuário configurado!
    git config --list -> mostra todas as configurações 

   
01 INIT ->  Iniciando um repositório local 
   

	 git init      <No diretório do projeto>       inicializa um novo repositório local

02 ADD
   git add . ou - A                                 add todos arquivos/alterações ao próximo commit
	 git add nome.ex                                  adicionando um arquivo especifico..
      
03 Verificando o estado do repositório 

	 git status                                       mostra o status/estado atual do rep. git 
	 git log                                          mostra todos os commit's + detalhes
	 git reflog                                       mostras todos commit's apenas index...
	 git diff                                         mostra o que foi modificado nos arquivos <conteudo>
	 git diff arquivo.tal                             mostra o que foi modificado no arquivo.tal  <conteudo>
	 git diff --name-only                             mostras apenas os nomes dos arquivos modificados				                        
	 git diff --name-only   arquivo.tal               mostras apenas o nome do arquivo.tal modificado 		

04 Commit  <empacotar alterações em nova versão uma foto de um dado momento>

	 git commit -m "mensagem do commit"               cria um novo commit com uma msn
	 git commit -am "msn do commit"                   add alterações pendentes <apenas dos arquivos já add> e commit ao mesmo tempo

05 Repositorio remoto 
   Gerando uma chave ssh 	
   -> https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

  Configuração  - repositório remoto 
   git remote add origin "url ssh do repositório remoto"
   git remote add origin "url do repositório remoto"

  primeiro push
   git push --set-upstream origin master
	 git push                                        envia as atualizações/alterações para nuvem <da branch ativa>
	 git pull                                        atualiza a <branch local> ativa com os dados da nuvem
	 git remote                                      Mostrar informação sobre o repositorio remoto
   git remote -v                                   Com + detalhes

06 Branch <linha temporal um ramo do repositorio>
   git branch                                           lista as branch's e mostra a ativa
	 git branch   "novo branch"                           criar um novo branch     
	                                                      a nova branch é um clone  da branch ativa ou alvo                         
	 git checkout  nome da branch                         permite mudar para outra branch
	 git checkout -b "branch de origem" "nova branch"     permite criar é já tornar ativa a nova branch!

 6.1 Removendo uma brach remoto 
      Na branch local correspondente a branch remoto.
       git push origin :"nome da branch"	

 6.2 Removendo um branch local 

    Fora da branch que vai ser removida
     git branch -D "nome do branch a ser removido"
		                 


07  MERGE -> acrescentando/atualizando um branch com dados de outra branch

   git merge "branch q vai doar o merge"            fazer um merge entre a branch ativa com uma outra branch
	 git merge  <nome_da_branch que vai mesclar com a branch corrente!>  
    
	 	  1 git pull da branch principal 
			2 gerar uma branch a partir da branch principal
				git checkout na branch "nova branch" 
			3 trabalhar/adicionar novas funcionalidades na nova branch
			4 finalizar o trabalho na branch temporária 
			5 git checkout na branch principal 
			6 git pull					
			7 Merge (unir) o código da branch temp com a branch principal (depois dos testes...)					 
        git checkout  <branch que vai receber o merge> 
				git merge <branch doadora>
			8 git push da branch principal 	 
      
08 Transitando entre as versões no mesmo branch * Revertendo Modificações
 8.1 RESET
    git reset          
	           --hard        retorna exatamente ao ponto escolhido ignorando tudo <arquivos, add e modificações> anteriores 
	           --soft        retorna a um passo anterior ao ponto de retorno escolhido depois do git add 'commit-less' 
             --mixed       retorna a um passo anterior ao ponto de retorno escolhido antes do git add 'commit-less' 

 8.2 RESTORE

     git restore          arquivo.tal        restaurando o arquivo.tal 
		 git checkout HEAD -- arquivo.tal           

     git restore .                          restaurando todos os arquivos 
		 git checkout HEAD -- .  

8.3 REVERT --revertendo sem perder o código  salvando a sexta-feira

  git revert --no-edit <id do commit>
  produz um novo commit revertendo as alterações do commit atual..
	 depois é só voltar ao commit que deu problema e corrigir...
      
9 GITIGNORE ignorando arquivos/pastas
  touch .gitignore                 criando o arquivo .gitignore
  O que tiver nesse arquivo será ignorado pelo git 
	arquivo.tal     -> o arquivo.tal será ignorado pelo git
        *.tal     -> todos arquivos com a  extensão .tal serão ignorados 
 nome_da_pasta    -> pasta e tudo dentro será ignorado
 nome_da_pasta/  

  exemplos: -> https://github.com/github/gitignore
    https://docs.github.com/pt/get-started/getting-started-with-git/ignoring-files

-------------------------------------------------------------------------------------------------------------------------------------------

------------------------------- Curso de Git e Github COMPLETO 2021 [Iniciantes] + Desafios + Muita Prática ------------------------------- 

01 - O que irá aprender neste curso    -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=0s

02 - Pré-requisitos                    -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=54s

03 - O que é git e github              -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=73s

04 - Como instalar Git                 -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=247s

05 - Como criar uma conta no Github    -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=330s

06 - Como Inicializar um repositório  -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=475s   

07 - Como adicionar arquivos ao controle de versão
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=660s  

08 - Como criar versões do código com commit              
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=802s

09 - Como enviar alterações usando git push               
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=930s

10 - Ciclo de atualização de código   -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=1224s

11 - Como verificar histórico de atualizações             
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=1352s
				 
12 - Como navegar entre versões do seu código             
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=1388s

13 - O que são branches e como criar uma                  
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=1561s

14 - Git merge - Como unir o código   -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=2019s
  
15 - Pull request - um merge democrático                  
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=2469s
         
16 - Gitignore - ignorar arquivos do controle de versão   
                                      -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=2751s

17 - Considerações Finais             -> https://www.youtube.com/watch?v=kB5e-gTAl_s&t=2951s

-------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------- CURSO COMPLETO DE GIT (2 HORAS E 30 MINUTOS) ↓----------------------------------------------
                                            -> https://www.youtube.com/watch?v=OuOb1_qADBQ

01 - O que é, pra que serve, como funciona? ↓ 
                              -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=281s

02 - Instalando o GIT         ->  https://www.youtube.com/watch?v=OuOb1_qADBQ&t=910s
 
03 - Configurando o GIT       -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=1302s

04 - Iniciando um repositório -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=1628s

 4.1 Pequena introdução a linha de comando! ↓ 
                              -> https://youtu.be/OuOb1_qADBQ?t=1709
05 - Branch, Readme, Commit   -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=2184s

06 - Revertendo Modificações  -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=3119s

07 - Trabalhando com diferentes Branches ↓
                             -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=3893s

08 - Diferença entre arquivos -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=4649s

09 - Criando um repositório no Github ↓
                              -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=5241s

10 - Conectando repositório local ao remoto ↓
                              -> 01:33:10 - Conectando repositório local ao remoto

11 - Fazendo alterações no repositório remoto ↓
                             -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=6379s

12 - Ignorando arquivos do repositório (gitignore) ↓
                             -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=6941s
 
13 - Revertendo sem perder o código ↓
                            -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=7257s

14 - Deletando branches locais e remotos ↓
                            -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=7617s

15 - Puxando alterações de outras pessoas (pull) ↓
                            -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=8019s

16 - Clonando repositórios remotos (clone) ↓
                            -> https://www.youtube.com/watch?v=OuOb1_qADBQ&t=8434s

17 - Contribuindo com outros repositórios (fork / pul request) ↓
                           ->https://www.youtube.com/watch?v=OuOb1_qADBQ&t=8770s