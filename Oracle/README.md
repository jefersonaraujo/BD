# Oracle


##### Unidades Físicas
###### Arquivos de parâmetros - São os arquivos lidos no momento que um banco de dados sobe, ou seja, no momento em que ele fica operacional. Como parâmetros, são por exemplo a quantidade de memória, parâmetros de sessão,etc.

###### São dois tipos de arquivo :
###### SPFILE - A instância do banco de dados lê esse arquivo no momento da inicialização. Esse arquivo é binário e deixa os parâmetros persistentes.

###### PFILE - É um arquivo idêntico ao SPFILE, porém é um arquivo texto e pode ser editado manualmente pelo usuário.

##### EX:  Necessita realizar uma manutenção porque eu necessito que o banco suba de determinado modo porém não utilizarem tão cedo o Banco da mesma forma. Então vamos supor que eu quero fazer um teste de performance. Eu quero que esse banco suba ocupando o 60 por cento da memória da minha máquina. Em vez de tornar o parâmetro permanente nesse perfil eu posso apenas editar o perfil que é o arquivo de texto.

##### Escopos
###### 1 - Na memória
###### 2 - Na reinicialização
###### 3 - No mesmo momento

######  Em memória - É alterado automaticamente, para isso necessita ser dinâmico. SCOPE = MEMORY.
###### SPFILE - Alteração válida somente após reinicialização e não vai estar em memória. Por mais que seja dinâmico, não desejo fazer no mesmo momento. 
