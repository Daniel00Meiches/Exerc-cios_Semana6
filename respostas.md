1.

**a) A saída será undefined seguido de erro**
<br>
O programa tenta fazer um console.log de uma variável sendo que ela ainda não foi definida no programa. Assim, a saída no console será primeiro de um valor undefined e depois mostrará um ReferenceError, que acontece justamente quando o programa tenta referenciar uma variável que não foi declarada.

```javascript
// Versão que concerta o erro

var x = 5;
console.log(x); // Saída: 5
let y = 10;
console.log(y); // Saída: 10
```

2.

**b) Substituir if (a || b === 0) por if (a === 0 && b === 0)**
<br>
Essa opção solucionaria o problema, porque primeiro, 2 + 0 = 2, e não teria motivo para essa conta dar um erro no programa. A condicional (a === 0 && b === 0) vai garantir que o erro só ocorrerá se ambos os parâmetros a e b forem iguais a 0. (a && b === 0) vai apenas checar se o parâmetro b é igual a 0, por isso que é incorreto. As outras opções usam o condicional or (||), que permitem que o erro ocorra se apenas um dos parâmetros for igual a 0, o que levaria a um cenário indesejável.

3.

**b) O código imprime 200**
<br>
Já que o código do programa não inclui um 'break' no comando switch na linha da case("eletrônico):, o programa continuará a executar as expressões case seguintes até achar o próximo valor que inclui um 'break'.

```javascript
// Essa versão daria a saída esperada

function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
            break; // <-- adicionando o break
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico")); // Saída: 1000
```

4.

**d) 24**

5.

**c) ["banana", "abacaxi", "manga", "laranja"]**
<br>
.splice em um array consegue remover itens de um array e adicionar novos itens ao mesmo array. Nesse código, temos a linha "lista.splice(1, 2, "abacaxi", "manga")". O código está dizendo que o index 1 e o index 2 do array lista serão substituídos pelas strings "abacaxi" e "manga", respectivamente. Então, "maçã", que está no index 1, será substitúido por "abacaxi", enquanto "uva", que está no index 2, será substituído por "manga".

```javascript
// Testes que eu fiz para ver como funciona o .splice

// Substituindo index 1 e index 0
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista); // Saída: [ 'banana', 'abacaxi', 'manga', 'laranja' ]

// Substituindo index 0 e index 1
let lista2 = ["banana", "maçã", "uva", "laranja"];
lista.splice(0, 1, "abacaxi", "manga");
console.log(lista); // Saída: [ 'abacaxi', 'manga', 'uva', 'laranja' ]
```


6.

**a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.**
<br>
A primeira afirmação apenas define o que é uma herança em programação, enquanto a segunda afirmação mostra a maneira pelo qual a herança é implementada no código. Com isso, você poderia dizer que a segunda afirmação justifica a primeira, pois está comprovando como é possível compartilhar métodos e propriedades entre classes sem ter que repetir código.

7.

**a) I e II são verdadeiras.**
<br>
A primeira afirmação é verdadeira porque o código corretamente faz a herança de classes, usando a palavra-chave 'extends'. A terceira afirmação diretamente contradiz isso, o que quer dizer que ela é falsa. A segunda afirmação é verdadeira, pois quando fui testar o código, quando eu entrei info.apresentar no programa (para executar o método apresentar), a saída foi do método da class Funcionario e não da class Pessoa:

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}

//----------------------------------------------------------------------------------

let info = new Funcionario("André", 20, 2000);
info.apresentar();

// Saída:
// Olá, meu nome é André e tenho 20 anos.
// Meu salário é R$ 2000.
```

por isso que a segunda afirmação é verdadeira.

8.

**d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.**
<br>
A asserção e a razão são verdadeiras. O modo que o enunciado aplica o conceito do polimorfismo é correto, onde objetos diferentes conseguem responder à mesma mensagem de maneiras diferentes (poli = muitas, morfo = forma. Polimorfismo = muitas formas). A razão proposta pelo enunciado corretamente explica como isso ocorre em Javascript, através da sobrecarga de métodos em uma classe, veja o exemplo abaixo:

```javascript

```

