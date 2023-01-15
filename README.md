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

Cabe notar que o esse projeto foi desenvolvido no Windows e foi necessário a definição de uma macro ``` #define yywrap() 1``` a fim de compilar no Windows sem a necessiadade de colocar a flag ```-lfl``` no comando de compilação do GCC.
