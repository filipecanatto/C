PARA QUE SERVE ESSE PROGRAMA ?.
Esse programa tem a finalidade de mostrar como funciona o conceito de biblioteca estatica em ambientes Linux.

OVERVIEW DE CONCEITOS:
Uma lib (biblioteca) � um agrupamento de arquivos (.c e .h) isolados em um unico arquivo. 
O agrupamento dos arquivos � feito na fase de compilac�o. O compilador e o linkador (linker) s�o responsaveis 
em transformar o c�digo fonte do programa principal (cliente) e o c�digo fonte servidor (aquele que faz a implementa��o das fun��es) em um unico arquivo.

QUAL O BENEFICIO ?.
- Organiza��o do codigo fonte;
- Reuso de c�digo;

TRY IT OUT:

gcc -c matlib.c matlib2.c
Realiza a compila��o dos arquivos que ir�o compor a lib.
- O parametro "-c" indica ao compilador que ele n�o deve tentar gerar um arquivo executavel.

ar crv libmat.a matlib.o matlib2.o
Agrupa os arquivos .o gerados em um unico arquivo (ou seja, cria uma lib).

gcc -c teste_matlib.c
Compila o programa principal (cliente).

gcc -o teste_matlib teste_matlib.o libmat.a
Transforma o programa cliente e a lib em um unico arquivo. Ap�s isso o programa pode ser executado.
- O parametro "-o" diz ao compilador para criar o arquivo final com o nome "teste_matlib".

TESTE FINAL:
./teste_matlib

OBSERVA��ES:
- Os programas cliente e servidor foram tranformados em um unico arquivo;
- Podemos apagar a lib sem impactar o programa final (opcional).
