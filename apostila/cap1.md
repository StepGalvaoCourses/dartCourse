# Conhecendo a Linguagem

Muitos alunos chegam na disciplina de programação orientada a objeto com o conhecimento da programação estruturada. Por isso, é interessante
os alunos conhecerem primeiramente a ferramenta de aprendizagem, a linguagem [dart](https://dart.dev/), e resolverem o mesmo problemas que 
resolveram nas lingagues anterior, agora nova linguagem. Após isso, será feita a mudança de paradigma utilizando os problemas como exemplos.

Devido à isso, este capítulo será para a apresentação da linguagem [dart](https://dart.dev/), de modo estruturado. Posteriormente serão 
apresentadas as estruturas de programação orientada a objeto da linguagem.

## Tudo começa com o *Hello Word*

Em dart, todo app tem a função ```main```, Como apresentada na Figura 01.

**Figura 01: Hello Word em dart.**
```dart
void main() {
  print('Hello World!');
}
```
<!-- Falar sobre o que é assinatura da função e corpo da função, mas isso pode ficar para a parte de função -->
Aqui pode-se notar que o comando ```void``` que significa o tipo de retorno da função, nesse caso o tipo **void**; o nome da função,
**main**; os parenteses, **()**, para indicar que a função não recebe parâmetros. 

O corpo da função inicia-se com as chaves **{}**, de abertura e fechamento. Dentro das chaves tem-se o comando [```print```](https://sites.google.com/site/dartlangexamples/api/dart-core/functions/print),
que exibe uma mensagem na tela. Assim, o resultado do código da Figura 1 sera:

>Hello World!

## Variáveis
Em dart, as variáveis armazenam [referências](https://en.wikipedia.org/wiki/Reference_(computer_science) e a maioria das variáveis não precisam colocar 
explicitamente o tipo devido à inferencia de tipo, que é a dedução automática em tempo de compilação do tipo da expressão. Em seguir tem-se 
um exemplo de criação e inicialização de uma variável.

```dart
var nome = "José"
```
No exemplo acima, a variável chamada ```nome``` contém uma referência a um objeto ```String``` com o valor ```"Jose"```. Outra opção seria
colocar explicitamente o tipo da variável, como no código abaixo:

```dart
String nome = "José"
```

### Inicialização de variável

<!--Depois explicar o que é uma variável nullable -->
Em dart todas a variáveis **nullable** devem ser inicializadas antes da sua utilização (exceto se modo **null safety** não estiver ativado). Dessa forma, o código abaixo 
tem uma erro porque a variável ```nome``` não foi inicializada.

```dart
void main() {
  String nome;
  print(nome);
}
```

As variáveis não necessitam se inicializadas no momento da sua criação, basta
ser inicializada antes da sua utilização. Nó código abaixo, o comando ```print(quantidade)``` é permitido, porque a variável ```quantidade``` foi inicializada antes
do comando.

```dart
void main() {
  int quantidade;
  if(condicao){
    quantidade = 10;
  }else{
    quantidade = 9;
  }
  print(quantidade);
}
```

### Constante

Constantes em Dart são criadas pela palavra ```const``` ou ```final```. O Código abaixo mostra o exemplo da utilização
de uma constante:

```dart
void main() {
  const PI = 3.14;
  double raio = 10;
  double area = PI*PI*raio;
  print(area);
}
```
No código anterior, a constante ```PI``` foi criada pela inferência de tipo, mas constantes também podem ser criadas através da tipagem explícita, como no código a seguir

```dart
void main() {
  const double PI = 3.14;
  double raio = 10;
  double area = PI*PI*raio;
  print(area);
}
```

Observe que agora, a declaração da constante, ```const double PI = 3.14;``` , acompanha o seu tipo. Por fim, constantes são variáveis que não podem alterar o seu valor, após
inicializadas. Um exemplo de erro, causado por alteração de valor de uma constante pode ser visto no código a seguir

```dart
void main() {
  const double PI = 3.14;
  double raio = 10;
  PI = 3.1415;
  double area = PI*PI*raio;
  print(area);
}
```

Observe, no código acima, que o comando ```PI = 3.1415;``` está alterando o valor de ```PI```, o que não é permitido, pois ```PI``` é uma constante.

## Tipos de dados

Em dart são permitidos os seguintes tipos de dados:

- **Numeros:**: int, double
- **String:**: String
- **Boolean**: bool
- **Lista**: List
- **Set**: Set
- **Map**: Map

### **Numeros**

Números em Dart são de dois tipos, **int** e **double**. **int** são os número sem casas decimais, numeros inteiros, e **double** são os números com casas decimais (representadas pelo ponto), números de ponto flutuante. Abaixo tem-se a representação do inteiro ```idade``` e do ponto flutuante ```altura``` 

```dart
int idade = 20;
double altura = 1.78;
```
A mesma regra da inferência de tipos usada nos exemplos anteriores pode ser utilizada também para números. As variáveis ```idade``` de ```altura``` pondem ser declaradas como no código abaixo que continuarão com o mesmo tipo do exemplo anterior.


```dart
var idade = 20;
var altura = 1.78
```

A conversão de numeros para String e vice-versa pode ser feita como no exemplo a seguir. Através da função ```parse()```, para transforma de numero para String, e através das funções ```toString()``` e ```toStringAsFixed``` , para transformar de String para **int** e **double**

```dart
void main() {
  // int -> String
  int idade = int.parse('18');

  // String -> double
  double altura = double.parse('1.75');

  // int -> String
  String idadeString = 18.toString();

  // double -> String
  String alturaString = 1.7589.toString();
  String alturaStringFormat = 1.7589.toStringAsFixed(2);
}
```

### **String**

String são representadas por aspas simple ou aspas duplas. No exemplo abaixo, as String são criadas das duas formas.

```dart
void main() {
  String nome = "José";
  String texto = 'Meu texto';
}
```
Valores de expressões podem ser colocados dentro de uma String através de ```${expressao}```. Se a expressão for somente um identificador, como uma variável, o ```{}``` pode ser opcional. No exemplo a seguir, as String estão sendo colocadas diretamente dentro do comando ```print```, mas poderia ser colocado também dentro de uma variável.

```dart
void main() {
  double salario = 1000;
  double imposto = salario * 0.10;
  double salarioFinal = salario - imposto;

  print("Salario = ${salario}");
  print("Imposto = $imposto");
  print("Salario Final = $salarioFinal");
  print("Salario Final = ${salario - imposto}");
}
```

No exemplo, acima o comando:
>```print("Salario = ${salario}");``` 

exibirá a saída, 

>```Salario = 1000.0```,

neste caso os ```{}``` é opcional, pois a expressão é formada por somente um identificador. Já o comando no comando abaixo, as ```{}``` não são opcionais, pois a expressão não é somente um identificador.

> ```print("Salario Final = ${salario - imposto}")```

tem como saída:

>```Salario Final = 900.0```

A concatenação de String é feita através o operador ```+```, como no exemplo a seguir:

```dart
String nome = "José" + "de Nazaré";
```

### **Boolean**

Os valores booleanos têm um tipo chamado ```bool```. Apenas dois objetos têm o tipo bool: os literais booleanos ```true``` e ```false```.

```dart
void main() {
  bool sexoMasculino = true;

  if(sexoMasculino){
    print("Necessário comprovante de reservista");
  }else {
    print("Não é necessário o comprovante de reservista");
  }
}
```

### **Lista**

As listas em Dart são criadas através do objeto ```List```. Estes objetos são identificados por ```[]```, e seus valores são separados por vírgula. No código a seguir, tem-se o exemplo de uma lista de nomes:

```dart
List nomes = ["Jose", "Maria", "Joao"];
```

Os valores de uma lista são acessados através do operador ```[indice]```. O primeiro indice da lista é o valor zero, consequentemente o último indice é o ```tamanho_da_lista - 1```. O tamanho de uma lista pode ser acessado através da propriedade ```length```. 

No código a seguir tem-se o exemplo da criação da lista ```nome``` que possui três valores. O primeiro valor da lista é acessado pelo comando ```nome[0]``` e o tamanho da lista pode ser informado pelo comando ```nomes.length```

```dart
void main() {
  List nomes = ["Jose", "Maria", "Joao"];
  String primeiro = nomes[0];
  int tam = nomes.length;
  
  print("Primeiro nome = $primeiro");
  //Primeiro nome = Jose

  print("Tamanho da lista = $tam");
  //Tamanho da lista = 3
}
```



