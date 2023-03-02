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

Em dart todas a variáveis devem ser inicializadas antes da sua utilização (exceto se modo **null safety** não estiver ativado)



