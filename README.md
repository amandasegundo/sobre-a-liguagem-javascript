# Sobre a Liguagem JavaScript

## Paradigmas da linguagem

Javascript é uma linguagem de programação que faz o uso de vários paradigmas.

### Paradigma imperativo

Programação imperativa é um paradigma de programação que descreve a computação como ações, enunciados ou comandos que mudam o estado (variáveis) de um programa. ("Ordenar como o sistema irá funcionar").

### Paradigma procedural
O paradigma procedural se baseia no conceito de chamadas a procedimento (en: procedure call). Os Procedimentos, também conhecidos como rotinas, subrotinas, métodos, ou funções (que não devem ser confundidas com funções matemáticas, mas são similares àquelas usadas na programação funcional) simplesmente contêm um conjunto de passos computacionais a serem executados. Um dado procedimento pode ser chamado a qualquer hora durante a execução de um programa, inclusive por outros procedimentos ou por si mesmo.

### Orientação a Objetos (baseada em protótipos e não em classes):
 Protótipos são, de forma bem simples, objetos que servem de "reserva" para outro objeto. Dessa forma, quando buscamos uma propriedade em um objeto e ela não está presente nele, a máquina virtual vai até o protótipo desse objeto buscar essa propriedade. Caso o resultado seja negativo novamente, busca-se no protótipo do protótipo e assim por diante até que um objeto não tenha prototótipo ou a propriedade seja encontrada.

### Orientada a eventos:
Paradigma no qual é implementada uma rotina que é especializada em monitorar os eventos e avisa o código especializado em responder a um determinado evento que aquele evento que ele esperava ocorreu; e então o código recém avisado responde ao evento. (mouseClick, onClick, beforePost).

## Sistema de tipos da linguagem

### Dinâmica e fraca.

#### Tipos de variáveis

Apesar de ser de tipagem dinâmica e fraca o JavaScript possui tipos de variáveis.

- **String:** Armazena cadeia de caracteres ou seja um texto, utiliza-se aspas simples para texto. exemplo: 'exemplo'
- **Number**: Números sem aspas, exemplo 10
- **Boolean**: possui os valores true e false.
- **Array**: estrutura para armazenar vários valores em uma única referência. Exemplo: var array01= [10, 'bob', true] 
- **Object**: pode se dizer que tudo em javascript é um object e pode ser armazenado em uma variável.
 
#### Operadores

**+** : Adiçao e concatenação

**-** : subtração

*\** : multiplicação

**/** : Divisão

**=** : operador de atribuição

**===** : operador de comparação, retornar um valor booleano

**!==** : Operador de comparação, retorna true para elementos diferentes

**!** : negação

Em expressões envolvendo valores numéricos e strings com o operador +, o JavaScript converte valores numéricos para string. Por exemplo, considere as seguintes declarações:

```js
x = "A resposta é " + 42 // retorna "A resposta é 42"
y = 42 + " é a resposta" // retorna "42 é a resposta"
```

Em declarações envolvendo outros operadores, o JavaScript não converte valores numérico para strings. Por exemplo:

```js
"37" - 7 // retorna 30
```

**++** : incremento

**--** : decremento

**%**  : MOD = resto da divisão

**break**: utilizado na estrutura switch;

**continue**: utilizado nos laços de repetição.

**delete** : deleta uma propriedade do objeto.

**in**: Retorna verdadeiro se uma propriedade existe um objeto

## Principais estruturas

### Estruturas de condicional:

#### if, else

Estrutura condicional verifica uma ou mais condições e executa o bloco da estrutura.

Exemplo:

```js
nome = 'Cristian'
if (nome == 'Cristian'){
    z = ('Sou eu');
} else {
    z = ('Não sou eu');
}
alert(z);
```

#### switch, case


Outra estrutura de condicional que o javascript possui é o switch, case. Ele funciona como uma sequência de ifs e elses com uma estrutura mais "elegante".

Exemplo:
```js
nome = 'Gabriel'
switch(nome){
  case 'Cristian':
    	z = 'Sou eu';
   	 break;
  case 'Gabriel':
    	z ='Não sou eu';
    	break;
  default:
    	z = 'Não sei que é';
}
alert(z);
```

### Estruturas de condicional

#### while, do while, for, for in

Estruturas de laços de repetição, já conhecidos em outras linguagens como Java.

Nos casos de while e do...while, enquanto a condicional for verdadeira o bloco será repetido.

Nos casos do for e for in, o bloco será repetido conforme a quantidade de elementos contidos na condicional.

Exemplos:

#### while

```js
x = 0
while (x < 10){
    x = x+1;
}
alert(x);
```

#### do while

```js
x=0
do {
    x = x+1;
} while (x < 10)
alert(x);
```

#### for

```js
x = 0
for (i = 0; i < 5; i++) {
    x = x+1;
}
alert(x);
```

#### for in

```js
var pessoa = {nome:"Cristian Maicon", sobrenome:"Voltolini", idade:35};
var text = "";
var x;
for (x in pessoa) {
    text += " " + pessoa[x];
}
alert(text);
```

### Estrutura function

#### function

As declarações de funções, como o padrão de javascript os parâmetros não são tipados, e podem ou não retornar valores o que vai determinar isso é a existência do return na função.

Exemplo:

```js
function soma1(x){
    return x+1;
}

var msg = function mensagem(x){
    alert(x);
}

var x = 0;
x = soma1(x);
x = soma1(x);
x = soma1(x);
mensagem(x);
msg("Esse é com atribuição de função "+x);
```

### Estrutura de tratamento de erros

#### try , catch, finally e throw

Estrutura para tratamento de erros, muito igual a Java C#.

Todo o erro que ocorre dentro de um bloco try é passado para o bloco catch, você pode utilizar o throw para apontar um erro, e o bloco finally será executado sempre, independentemente de ocorrer um erro.

Exemplo:

```js
x = 4
try {
    if(x == "") throw "Está vazio";
    if(isNaN(x)) throw "não é um numero";
    if(x > 10) throw "muito alto";
    if(x < 5) throw "muito baixo";
}
catch(err) {
    alert(err);
}
finally{
    alert("Sempre executo mesmo com erro");
}
```

### Estrutura de classes

#### Classes e objetos

Conceito parecido com outras linguagens orientadas a objeto. Contém propriedades, métodos, heranças.

Objetos em javascript podem ser criados sem a declaração da classe para esse objeto.

Exemplos:

##### Class

```js
class Retangulo {
  constructor(altura, largura) {
  this.altura = altura; this.largura = largura;
  }

  get area() {
  return this.calculaArea()
  }

  calculaArea() {
  return this.altura * this.largura;
  }
}

var quadrado = new Retangulo(10,10);

alert(quadrado.area);
```

#### Herança

```js
class Retangulo {
  constructor(altura, largura) {
  this.altura = altura; this.largura = largura;
  }

  get area() {
  return this.calculaArea()
  }

  calculaArea() {
  return this.altura * this.largura;
  }

}

class Quadrado extends Retangulo{
  constructor(lados){
  super(lados, lados);
  }
}

var quad = new Quadrado(10);

alert(quad.area);

Objetos sem ter uma classe com modelo
var pessoa = {nome:"Cristian Maicon", sobrenome:"Voltolini", idade:35};
var text = "";
var x;
for (x in pessoa) {
    text += " " + pessoa[x];
}
alert(text);
```

## Aplicação
O JavaScript (JS) foi criado como uma linguagem de scripting, ou seja, para controlar determinados comportamentos em aplicações já existentes.

O JS começou e se popularizou nos navegadores de internet, mas hoje em dia é possível encontrar interpretadores de JavaScript e grandes e renomadas aplicações como o Adobe Acrobat Reader, o Photoshop, as imagens vetoriais SVG, ambientes de servidores como o Node.js, ambientes desktop como o Gnome, etc...

## Interpretação e Compilação
O JavaScript é uma linguagem essencialmente interpretada, porém, dependendo do ambiente, ela pode utilizar os recursos de interpretação e compilação de maneira mista.

Diferentes navegadores utilizam diferentes engines de JavaScript, feitos em linguagens como Java e C++, que pré-compilam partes do código JavaScript para rodar na máquina cliente.

Os principais exemplos de engines de execução de JavaScript são o V8 desenvolvido pela  Google, o Rhino e o SpiderMonkey ambos desenvolvidos pela Mozilla Foundation.

## Curiosidades
Vários problemas ocorrem no JavaScript pelo fato de ser uma linguagem de tipagem fraca e dinâmica.

Geralmente acontecem quando se depara com um impasse causado pela liberdade dada pela própria linguagem.

### Comparações Estranhas

A linguagem JavaScript permite comparar objetos de tipos diferentes.

O operador == ( igual a ) permite comprar apenas o valor e  === ( igual tipo e valor ) compara primeiro o tipo e depois o valor.

Agora de fato vamos às coisas estranhas que não fazem sentido:

#### Comparando array igual a array retorna falso.

```js
> [] == []
// false
```

#### Comparando array igual a não array retorna verdadeiro.

```js
> [] == ![]
// true
```

#### Comparando objeto array igual a String com 3 vírgulas retorna verdadeiro.

```js
> Array(4) == ",,,"
// true
```

#### O null representa ausência de valor significativo e também é um objeto em Java.

Porém, null não é considerado uma instância de um objeto.

```js
> typeof null
// object
	> null instanceof Object
// false
```

#### O mesmo acontece com as strings, elas também não são instâncias de strings.

```js
> "String bonitona e rebelde" instanceof String
// false
```

#### Outro tipo estranho é o NaN que significa "not a number".
Se verificarmos com typeof qual o tipo de um NaN, ele retorna que é um number.

Um not a number é um number. Mas se compararmos um NaN igual a NaN, retorna false.

```js
> typeof NaN
// number
> NaN == NaN
// false
```

E apesar do NaN ser um number, ele não é uma instância de number.

```js
> typeof NaN
// number
> NaN instanceof Number
// false
```


## Contribuidores

- [Amanda Segundo](https://github.com/amandasegundo)
- [Cristian Voltolini](https://github.com/crmaicon)
- [Gabriel Bartholomeu]()
- [Matheus Avi](https://github.com/matheusavi)
- [Maxwell de Assis](https://github.com/maxwelldeassis)