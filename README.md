# documentacão C
Uma documentação prática e simples feita de universitários para universitários com o objetivo de facilitar o aprendizado da linguagem c.


---

## Índice
1. [Um pouco sobre bibliotecas](#adicionando-bibliotecas)
2. [Escopo principal de um programa](#escopo-principal)
3. [Hello world](#hello-world)
4. [Tipos de dados](#tipos-dados)
5. [Especificadores mais comuns](#especificadores-comuns)
6. [Float vs Double](#float-vs-double)
7. [Vetor de caracteres](#vetor-de-caracteres)
8. [Operadores](#operadores)
9. [Mais operações com números](#mais-operacoes)
10. [Comentários](#comentarios)
11. [Constantes](#constantes)
12. [Trabalhando com entradas e saídas](#entradas-saidas)
13. [Condicionais](#condicionais)
14. [Laços de repetiçao](#loops)
15. [Funções](#funcoes)

---

## Um pouco sobre bibliotecas <a name="adicionando-bibliotecas"></a>
As bibliotecas nos auxiliam a executar instruções no nosso programa. para adiciona-las basta utilizar #include + nome da biblioteca:
```c

#include <stdio.h>

// Resto do programa
```
No caso da biblioteca stdio.h, 'std' vem de standard(padrão) e 'io' significa input/output (Entrada/saída), portanto é facil imaginar que
essa biblioteca adiciona instruções de entrada e saída padrões, são o 'printf' e 'scanf'.
Existem varias outras bibliotecas como: 
- math.h 
- stdlib.h 
- string.h
- limits.h
- stdbool.h
- time.h

Dentre varias outras.

## Escopo principal de um programa <a name="escopo-principal"></a>
Em C, é comum ver nosso programa rodar dentro de uma função principal:
```c
//importações

int main() {
  //códigos do programa
  return 0; //retorno indicando que o programa rodou como esperado
}
```

## Hello world <a name="hello-world"></a>
Com o que vimos até aqui, já podemos construir o clássico programa hello world:
```c
#include <stdio.h> //biblioteca que adiciona entradas e saídas

int main() { // função principal
    printf(“hello world”); // saída da string hello world
    return 0; // retorno de sucesso do programa
}
```

## Tipos de dados <a name="tipos-dados"></a>
Como em toda linguagem temos vários tipos de dados. Em C podemos utilizar algumas “expressões”, os Especificadores de formato, para tipar as variaveis na entrada e saída. A seguir veja os tipos de dados, seus devidos tamanhos e especificadores de formato:

Tipo de dados   | Memoria(bytes) | Intervalo | especificador de formato
--------- | ------ | -----------| ----------|
short int | 2 | -32, 768 a 32, 767 | %hd
unsigned short int | 2 | 0 a 65, 535 | %hu
unsigned int | 4 | 0 a 4, 294, 297, 295 | %u
int | 4 | -2,147,483,648 to 2,147,483,647 | %d
long int | 4 | -2,147,483,648 a 2,147,483,647 | %ld
unsigned long int | 4 | 0 a 4,294,967,295 | %lu
long long int | 8 | -(2^63) a (2^63)-1 | %lld
unsigned long long int | 8 | 0 a 18,446,744,073,709,551,615 | %llu
signed char | 1 | -128 a 127 | %c
unsigned char | 1 | 0 a 255 | %c
float | 4 | | %f
double | 8 | | %lf
long double | 16 | | %Lf

## Especificadores mais comuns <a name="especificadores-comuns"></a>
De forma mais simplificada, aqui estão os especificadores mais comuns e que serão mais utilizados:

especificador de formato | descrição
-------------------------| ----------|
%d or %i | É usado para imprimir o valor inteiro com sinal, onde inteiro com sinal significa que a variável pode conter valores positivos e negativos.
%u | É usado para imprimir o valor inteiro sem sinal, onde o inteiro sem sinal significa que a variável pode conter apenas valor positivo.
%o | É usado para imprimir o inteiro octal sem sinal, onde o valor inteiro octal sempre começa com um valor 0.
%x | É usado para imprimir o inteiro hexadecimal sem sinal, onde o valor inteiro hexadecimal sempre começa com um valor 0x. Neste, os caracteres alfabéticos são impressos em letras minúsculas, como a, b, c, etc.
%X | É usado para imprimir o inteiro hexadecimal sem sinal, mas% X imprime os caracteres alfabéticos em maiúsculas, como A, B, C, etc.
%f | É usado para imprimir os valores de ponto flutuante decimal. Por padrão, ele imprime os 6 valores após '.'.
%e/%E | É usado para notação científica. Também é conhecido como Mantissa ou Expoente.
%g | É usado para imprimir os valores de ponto flutuante decimal e usa a precisão fixa, ou seja, o valor após o decimal na entrada seria exatamente o mesmo que o valor na saída.
%p | É usado para imprimir o endereço em formato hexadecimal.
%c | É usado para imprimir o caractere sem sinal.
%s | É usado para imprimir as strings.
%ld | É usado para imprimir o valor inteiro com sinal longo.


## Float vs Double <a name="float-vs-double"></a>
A primeria vista eles podem parecer iguais, mas há uma enorme diferença. Como o nome indica, a double tem 2x a precisão de Float.

double possui 52 bits de mantissa + 1 bit oculto: log (2 53 ) ÷ log (10) = 15,95 dígitos

float possui 23 bits mantissa + 1 bit oculto: log (2 24 ) ÷ log (10) = 7,22 dígitos

Essa perda de precisão pode levar ao aumento de erros de truncamento quando cálculos repetidos são feitos.

## Vetor de caracteres <a name="vetor-de-caracteres"></a>
Em linguagem C, ao contrário de outras linguagens, não existe um tipo de dados string nativo.

Para representar uma string em C, devemos criar um vetor de caracteres, ou seja um vetor do tipo char:

```c
char name[] = "john smith"
// ou
char name[20] = "john smith" // ao passar 20 entre os colchetes, definimos que
														// a string terá no máximo 20 caracteres.
```

## Operadores <a name="operadores"></a>
Um operador é um símbolo que indica a realização de uma operação sobre uma ou mais variáveis ou valores.

- Relacionais
    - '<'  menor que
    - '>'  maior que
    - '<='  menor ou igual
    - '>='  maior ou igual
    - '=='  igual
    - '!='  diferente
- Aritméticos
    - '/'  divisão
    - '*'  multiplicação
    - '-'  subtração
    - '+'  adição
    - '%'  módulo
- Lógicos
    - '&&'  operador binario E (and)
    - '||' operador binario OU (or)
    - '!' operador de negação (not)
- Incremento
    - '++' incremento
    - '--' decremento

## mais operações com números <a name="mais-operacoes"></a>
podemos utilizar a biblioteca <math.h> para trabalhar operações mais complexas com os números através de funções aritméticas:

- ceil( ) - arredonda o número fornecido. Ele retorna o valor inteiro que é maior ou igual ao número fornecido.

- floor( ) - arredonda o número fornecido para baixo. Ele retorna o valor inteiro que é menor ou igual ao número fornecido.

- sqrt( ) - retorna a raiz quadrada de um determinado número.

- pow( ) - retorna a potência de um determinado número. recebe 2 parâmetros, base, expoente 

  ex: pow(2, 4), retorna 16

- abs( ) - retorna o valor absoluto de um determinado número.

## Comentários <a name="comentarios"></a>
Como toda linguagem, o c tem um bloco especial que não é compilado para o executável e pode ser usado para comentar, documentar, ignorar códigos e etc...

podemos usar comentários de multiplas linhas:
```c
/* Comments can contain keywords such as
   for and while without generating errors. */
ou
/* MATHERR.C illustrates writing an error routine
* for math functions.
*/
```
comentários  de linha única dependendo do compilador:
```c
// This is a valid comment
```

## Constantes <a name="constantes"></a>
Para utilizar uma constante, apenas colocamos const  antes da declaração da "variável"(a partir desse momento deixa de ser uma varável rsrs):
```c
const int number = 4;
```

## Trabalhando com entradas e saídas <a name="entradas-saidas"></a>
Como vimos, ao adicionar a biblioteca <stdio.h>, podemos utilizar inputs e outputs padrões do c:

- printf - saída de dados
- scanf - entrada de dados

```c
int num;
printf("essa é uma saída");
scanf("%d", &num); // Essa é uma entrada
```
Como podemos ver, o scanf recebe como primeiro parâmetro um especificador de tipo referente ao tipo de dado que esperamos receber e recebe como segundo parâmetro
uma variável onde será guardado o valor recebido.

Note que antes da váriavel vai um & comercial, esse & é o operador "endereço de". Então o resultado dele sempre será o endereço de memória do objeto em questão.

Em C essa passagem sempre tem que ser explícita, já que todas passagens se dão por valor. Neste caso está passando o valor que é o endereço de memória, que será interpretado em algum lugar pegando o valor que está sendo apontado por este endereço, criando assim uma indireção. No caso específico o scanf() espera justamente um endereço onde ele deve armazenar o que for digitado pelo usuário.

O operador oposto é o * que é pegar o valor apontado pelo endereço.

#### Peculiaridade do scanf
O scanf tem uma peculiaridade no mínimo interessante, perceba:
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char name[20];
	printf("informe o seu nome:");
	scanf("%s", name);
	printf("seu nome é %s", name);
	return 0;
}
```
A resposta desse programa vai ser algo do tipo:
```c
informe seu nome: john
seu nome é john
```
porém, o problema surge caso seja passado um nome e sobrenome:
```c
informe seu nome: john smith
seu nome é john
```
Ele continua retornando apenas o primeiro nome.

Uma solução para isso é usarmos o fgets no lugar de scanf:
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	char name[20];
	printf("informe o seu nome:");
	fgets(name, 20, stdin);
	printf("seu nome é %s", name);
	return 0;
}
```
dessa vez, ao executar o programa, tudo segue normalmente:
```c
informe seu nome: john smith
seu nome é john smith
```
o fgets é usado para se ler uma string num arquivo. A função recebe 3 argumentos: a string a ser lida, o limite máximo de caracteres a serem lidos e o ponteiro para FILE, que está associado ao arquivo de onde a string será lida. 

no exemplo acima, passamos como referencia de arquivo o **stdin** que significa standard input, ou seja, pegamos a referência da entrada padrão, assim como fazemos no scanf.

## Condicionais <a name="condicionais"></a>

## Laços de repetiçao <a name="loops"></a>

## Funções <a name="funcoes"></a>

