## 1. O que é?

+ Também chamado de array, um vetor é uma coleção de elementos do mesmo tipo que podem ser acessados através de um índice que representa a sua posição. Eles são muitos úteis para armazenar dados, pois eles eliminam a necessidade de criar múltiplas variáveis para os armazenamento.

+ Uma forma mais fácil de visualizar a utilidade deles é com o seguinte problema:

***Imagine que você precise criar um sistema que leia, armazene e permita a visualização das seguintes informações de 5 alunos: nota, idade, e nome. Ao invés de criar 5 variáveis para cada informação, o que iria totalizar 15 variáveis diferentes, você pode utilizar apenas 3 vetores para armazenar todas as informações.***

## 2. Declaração e inicialização

+ Para declarar um vetor em C, você precisa especificar o tipo de dado que vai ser armazenado, o nome do vetor, e entre colchetes '[]' o número de elementos que irá ser armazenado nele.

**Ex1:**
```ruby
int numeros[5]; /*Declaração do vetor 'numeros' que é do tipo inteiro, podendo armazenar 5 elementos;*/
```
+ Além disso é possível inicializarmos um vetor logo quando fazemos sua declaração, para isso é preciso colocar um sinal de igual '=' e entre chaves '{}' colocar os elementos com os quais deseja inicializa-lo separados por vírgula ','.

**Ex2:**
```ruby
int numeros[] = {1, 2, 3, 4, 5}; /*Declaração do vetor números do tipo inteiro com os valores 1, 2, 3, 4 e 5*/
```
+ Note que não foi necessário colocar o número de elementos entre os colchetes, isso ocorre porque quando utilizarmos esse método, o número elementos no vetor é determinado pela quantidade de elementos nas chaves.

## 3. Acesso e atribuição de elementos.

+ Para acessar um elemento de um vetor será usado um sistema de índice, que começa do 0 até o números de elementos do vetor menos 1. É um pouco confuso de entender esse sistema de índices no início, por isso vamos usar um exemplo.

+ Vamos reutilizar o vetor 'numeros' do exemplo 2(int numeros[] = {1, 2, 3, 4, 5}), nele temos 5 elementos, sendo o primeiro elemento com o índice 0, o segundo com índice 1, o terceiro com 2, e assim até o quinto elemento com o índice 4. 

+ Agora, digamos que queremos acessar o 4° elemento do vetor e atribuir ele a uma variável chamada num, para fazer isso podemos fazer da seguinte forma:

**Ex3:**
```ruby
int numeros[] = {1, 2, 3, 4, 5};//Declaração e inicialização do vetor. 
int num = numeros[3];/*Declaração da variável 'num', que é inicializada com o elemento de índice 3 do vetor 'numeros'.*/
```
+ Neste exemplo, para inicializar 'num' com o quarto elemento do vetor é colocado, após o sinal de igual, o nome do vetor e entre colchetes o índice do elemento a ser acessado(em que nesse caso, como era o 4° elemento o índice será 3).

+ E da mesma forma que podemos atribuir a uma variável o elemento de um vetor, podemos alterar ou atribuir um valor ao vetor.

**Ex4:**
```ruby
int numeros[5]; //Declaração de um vetor de 5 elementos;
numeros[2] = 7;/*Atribuição do valor 7 ao 3° elemento do vetor 'numeros'*/
```
+ Caso queira preencher o vetor com os dados digitados pelo usuário, pode-se utilizar um laço de repetição 'for' para cada índice do vetor um elemento que foi digitado pelo usuário, veja o exemplo abaixo:

**Ex5:**
```ruby
#include <stdio.h>//Biblioteca para utilizar os comandos printf e scanf.
#include <locale.h>//Biblioteca que permitirá utilizar caracteres da língua portuguesa.

int main(){
	setlocale(LC_ALL, "Portuguese");//Configura a localização para caracteres da língua portuguesa.
	int numeros[5];//Declaração de um vetor de 5 elementos.
  
	for(int i = 0 /*Declaração e inicialização de i como 0*/; i < 5
	/*O laço irá repetir enquanto i for menor que 5*/; i++/*incrementação de i +1*/){
	
		printf("Digite o %d° número: ", i+1);
		scanf("%d", &numeros[i]);
	}
	
	return 1;
}
```
+ Nele se utiliza o laço de repetição for para que ele repita 5 cinco vezes, de forma que cada ciclo do laço represente um index(exemplo: no primeiro ciclo i=0, no segundo i=1, ..., no quinto ciclo i=4);

+ Agora que você viu como um vetor funciona, recomendo tentar desenvolver um código que resolva o problema citado anteriormente no início. Após isso você pode conferir a resolução do problema para comparar os códigos, para saber o que ficou melhor e/ou o que pode melhorar.











**Resolução do problema**
```ruby
#include <stdio.h>//Biblioteca para utilizar o pritnf e scanf para leitura de dados;
#include <stdlib.h>//Biblioteca para utilizar o system para utilizar o comando do prompt 'cls';
#include <locale.h>//Biblioteca para utilizar os caracteres da língua protuguesa;

int main(){
    //Configuração da localizção para utilizar os caracteres da língua portuguese;
    setlocale(LC_ALL, "Portuguese");
    //declaração dos vetores;
    char nome[5][50];
    int idade[5];
    float nota[5];
    //Laço de repetição que será responsável por preencher os vetores com os dados fornecidos pelo ususário;
    for(int i = 0; i < 5; i++){
        
        printf("Digite o nome do %d° aluno: ", i+1);
        scanf(" %49[^\n]", nome[i]);

        printf("Digite a idade desse aluno: ");
        scanf("%d", &idade[i]);

        printf("Digite a nota desse aluno: ");
        scanf("%f", &nota[i]);
        
        system("cls");
    }
    //Laço de repetição que será utilizado para mostrar as informações de cada vetor;
    for(int i = 0; i < 5; i++){

        printf("NOME - %s\n", nome[i]);
        printf("IDADE - %d\n", idade[i]);
        printf("NOTA - %.2f\n", nota[i]);
        printf("%s\n", "-------------------------------------------------------");
    }
    return 1;
}
```
