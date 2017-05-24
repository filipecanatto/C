PARA QUE SERVE ESSE PROGRAMA ?.
Esse programa tem a finalidade de mostrar como funciona o conceito de biblioteca estatica em ambientes Linux.

OVERVIEW DE CONCEITOS:
Uma lib (biblioteca) é um agrupamento de arquivos (.c e .h) isolados em um unico arquivo. 
O agrupamento dos arquivos é feito na fase de compilacão. O compilador e o linkador (linker) são responsaveis 
em transformar o código fonte do programa principal (cliente) e o código fonte servidor (aquele que faz a implementação das funções) em um unico arquivo.

QUAL O BENEFICIO ?.
- Organização do codigo fonte;
- Reuso de código;

TRY IT OUT:

gcc -c matlib.c matlib2.c
Realiza a compilação dos arquivos que irão compor a lib.
- O parametro "-c" indica ao compilador que ele não deve tentar gerar um arquivo executavel.

ar crv libmat.a matlib.o matlib2.o
Agrupa os arquivos .o gerados em um unico arquivo (ou seja, cria uma lib).

gcc -c teste_matlib.c
Compila o programa principal (cliente).

gcc -o teste_matlib teste_matlib.o libmat.a
Transforma o programa cliente e a lib em um unico arquivo. Após isso o programa pode ser executado.
- O parametro "-o" diz ao compilador para criar o arquivo final com o nome "teste_matlib".

TESTE FINAL:
./teste_matlib

OBSERVAÇÕES:
- Os programas cliente e servidor foram tranformados em um unico arquivo;
- Podemos apagar a lib sem impactar o programa final (opcional).
