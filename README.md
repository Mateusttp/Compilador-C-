# Compilador-C-
Compilador para a linguagem C- desenvolvido como projeto da disciplina de Compiladores do curso de Engenharia de Computação da UNIFESP.

Este compilador realiza a análise léxica, sintática e semântica do código-fonte. A geração de código intermediário e otimização ainda não foi implementada.


# Compilação do Compilador C-
Para realizar a compilação do COmpilador C- é necessário primeiramente executar o Yacc/Bison e o Flex a fim de gerar os arquivos em C do Analisador Léxico e Analisador Sinático.
Após a criação dos analisadores mencionados, é realizada a compilação dos arquivos.

Comandos para criação do Compilador C- "cminus"
```
bison -d parser.y
flex scanner.l
gcc -c *.c
gcc -o cminus *.o
```

Cabe notar que o esse projeto foi desenvolvido no Windows e foi necessário a definição de uma macro ``` #define yywrap() 1``` no arquivo de análise sintática ```scanner.l``` a fim de compilar no Windows sem a necessiadade de colocar a flag ```-lfl``` no comando de compilação do GCC. A ausência do macro gera um erro de compilação pois a biblioteca a ser "linkada" a partir da flag ```-lfl```  não é presente por padrão ao realizar o download do GCC para Windows.

# Uso do Compilador C-
O compilador recebe como argumento um arquivo de entrada contendo o código fonte a ser compilado e, opcionalmente, um segundo argumento indicando o arquivo a ser salvo a saída da compilação. Caso o arquivo de saída não seja fornecido o compilador irá imprimir a saída da compilação na própria linha de comando.

Comando para execução no Windows:
```
./cminus.exe <INPUT_FILE> <OPCIONAL_OUTPUT_FILE>
```
