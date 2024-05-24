## 1.Aviso
+ Antes de ver sobre matrizes, é recomendado que veja o [A respeito de vetor](https://github.com/TauaRibeiro/A-respeito-de-C/blob/main/A%20respeito%20de%20vetor.md) antes, pois irá facilitar o entendimento de matrizes.

## 2. O que é?
+ Uma matriz em C é báicamente uma coleção de vetores, essencialmente um vetor de vetores, permitindo um maior armazenamento de dados, quando comparado com os vetores, em uma grade bidimensional.
+ Para entender melhor sua utilidade, vamos reformular um problema utilizado no [A respeito de vetor](https://github.com/TauaRibeiro/A-respeito-de-C/blob/main/A%20respeito%20de%20vetor.md):
***Vamos imaginar que precisamos desenvolver um sistema que permita armazenar e mostrar os seguintes dados de 5 alunos: nome, notas, e média. Porém, será nescessário
  armazenar as notas das 3 unidades para cada aluno.***
+ Para que seja possível a armazenar as notas dos alunos, será nescessário a utilização de uma matriz.

## 3. Declaração
+ A declaração de uma matriz é similar a declaração de um vetor, contudo a matriz irá precisar informar o número de linhas e número de colunas, veja o exemplo a seguir.
Ex1:
```C
int numeros[3][5];//Declaração da matriz de inteiros nomeada 'numeros' com 3 linhas e 5 colunas;
```
+ Também é possível inicializar uma matriz na declaração.
```C
int numeros[2][2] = {{1, 2}, {3, 4}};//Declaração e inicialização da matriz 'numeros' com a primeira linha contendo os valores 1 e 2, e a segunda linha com 3 e 4;
```
+ Para que seja feita a inicialização da matriz matriz 'numeros', dentro das chaves '{}' é utilizado 2 series de chaves aonde cada chave representa uma linha, e dentro dessas chaves fica os dados separedados por vírgula.

## 4.Acesso e atribuição de elementos
+ Para acessar e modificar um elemento de uma matriz é utilizado os índices para acessar a linha e a coluna desse elemento.
Ex2:
```C
int numeros[3][3], num;//Declaração da matriz 'numeros' com 3 linhas e 3 colunas, e da variável 'num';
numeros[0][2] = 7;//Atribuição do valor 7 à 1° linha da 3° coluna da matriz 'números';
num = numeros[0][2];//Atribuição à variável 'num' o elemento da 1° linha da 3° coluna da matriz 'numeros';
```

+ Uma das formas de preencher uma matriz com elementos digitados pelo usuário é utilizado 2 laços de repetição 'for' onde um laço será para as linhas e outro para as colunas;
```C
#include <stdio.h>//Biblioteca para utilizar as funções scanf e printf;
#include <locale.h>//Biblioteca para

int main(){
    setlocale(LC_ALL, "PORTUGUESE");
    
	int numeros[3][3];
	
	for(int l = 0;  l < 3; l++){
		for(int c = 0; c < 3; c++){
			printf("Digite um número para %d° linha e %d° coluna: ", l+1, c+1);
			scanf("%d", &numeros[l][c]);
		}
	}   
    return 0;
}
```
