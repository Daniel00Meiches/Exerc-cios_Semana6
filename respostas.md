1.

<ins>**a) A saída será undefined seguido de erro**</ins>
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

<ins>**b) Substituir if (a || b === 0) por if (a === 0 && b === 0)**</ins>
<br>
Essa opção solucionaria o problema, porque primeiro, 2 + 0 = 2, e não teria motivo para essa conta dar um erro no programa. A condicional (a === 0 && b === 0) vai garantir que o erro só ocorrerá se ambos os parâmetros a e b forem iguais a 0. (a && b === 0) vai apenas checar se o parâmetro b é igual a 0, por isso que é incorreto. As outras opções usam o condicional or (||), que permitem que o erro ocorra se apenas um dos parâmetros for igual a 0, o que levaria a um cenário indesejável.

3.

<ins>**b) O código imprime 200**</ins>
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

<ins>**d) 24**</ins>

5.

<ins>**c) ["banana", "abacaxi", "manga", "laranja"]**</ins>
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

<ins>**a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.**</ins>
<br>
A primeira afirmação apenas define o que é uma herança em programação, enquanto a segunda afirmação mostra a maneira pelo qual a herança é implementada no código. Com isso, você poderia dizer que a segunda afirmação justifica a primeira, pois está comprovando como é possível compartilhar métodos e propriedades entre classes sem ter que repetir código.

7.

<ins>**a) I e II são verdadeiras.**</ins>
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

<ins>**d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.**</ins>
<br>
A asserção e a razão são verdadeiras. O modo que o enunciado aplica o conceito do polimorfismo é correto, onde objetos diferentes conseguem responder à mesma mensagem de maneiras diferentes (poli = muitas, morfo = forma. Polimorfismo = muitas formas). A razão proposta pelo enunciado corretamente explica como isso ocorre em Javascript, através da sobrecarga de métodos em uma classe, veja o exemplo abaixo:

```javascript

```

9.

```javascript
var soma = [];                            // Array que vai guardar os dobros dos valores do array nums[]

function somaArray(num1, num2, num3, num4) {

    var nums = [num1, num2, num3, num4];  // O array nums vai guardar os valores dos parâmetros da função somaArray, para que o cálculo dos dobros possa ser feito no loop for usando os valores de index da lista

    for (i = 0; i < nums.length; i++) {
        soma.push(2 * nums[i]);           // No VSCode, .push vai append (adicionar no final da lista) a multiplicação (2 * nums[i])
    }
    return soma;                          // O valor do array soma[] (nesse exemplo [2, 4, 6, 8]) será retornado para a função somaArray (somaArray será igual a [2, 4, 6, 8])
}

console.log(somaArray(1, 2, 3, 4));       // Saída: [ 2, 4, 6, 8 ]
```

10.

Como funciona a herança: a classe Livro vai herdar os membros (atributos e métodos) da classe Produto. Serão herdados os atributos nome, preco, dezPorcento e vintePorcento. No construtor da classe Livro, o super(nome, preco) é usado para chamar o construtor da classe pai (isso garante que os atributos sejam inicializados corretamente. E a classe Livro sobrescreve o método calcularDesconto() para alterar a lógica de cálculo.

Como eu implementaria a modificação do método na classe Livro: o método de calcularDesconto() na classe Livro tem uma lógica diferente do método presente na classe Produto. Para garantir que os descontos de 20% sejam corretamente aplicados a livros, eu faço uso de um switch para ver se o parâmetro nome é "livro" ou não. Se o nome for "livro", o desconto de 20% será aplicado e caso o nome for de qualquer outro produto, o desconto de 10% será aplicado. E o motivo que eu usei um switch e não um if-else é porque se eu quiser checar outros livros ou outros tipos de produtos futuramente, é mais fácil de adicionar casos do que verificar um if-else.

```javascript
// Classe produto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;   // Atributo: nome do produto
        this.preco = preco; // Atributo: preço do produto
        
        this.dezPorcento = this.preco - (this.preco * 0.1);   // cálculo de 10% será um atributo que será usado nos métodos
        this.vintePorcento = this.preco - (this.preco * 0.2); // cálculo de 20% será um atributo que será usado nos métodos
    }

    calcularDesconto() {
        console.log(`O preço descontado do produto ${this.nome}, que custava R$ ${this.preco.toFixed(2)}, é R$ ${this.dezPorcento.toFixed(2)}`);
        return this.dezPorcento;
    }

}

// Cenário criado
let info = new Produto('Baralho', 10);

info.calcularDesconto(); // Saída: O preço descontado do produto Baralho, que custava R$ 10.00, é de R$ 9.00

// -------------------------------------------------------------------------------------------------------------------

// Classe livro que pode herdar aspectos da classe produto. Isso inclui as variáveis que farão os cálculos dos descontos
class Livro extends Produto {
    constructor(nome, preco) {
        super(nome, preco); // Chama o construtor da classe pai, que nesse caso é Produto
    }

    calcularDesconto() {
        
        let discount;

        switch(this.nome.toLowerCase()) {
            case "livro":
                discount = this.vintePorcento; // Cálculo do disconto de 20% de desconto se o parâmetro nome = "livro"
                break;
            default:
                discount = this.dezPorcento;   // Cálculo do disconto de 10% de desconto para qualquer outro produto que for inserido
                break;
        }
        
        console.log(`O preço descontado do produto ${this.nome}, que custava R$ ${this.preco.toFixed(2)}, é R$ ${discount.toFixed(2)} `)
        return discount;
    
    }

}

// Criando dois cenários para testar o meu switch
let info2 = new Livro("Livro", 35);
let info3 = new Livro("Pelúcia", 60);

info2.calcularDesconto(); // Saída: O preço descontado do produto Livro, que custava R$ 35.00, é de R$ 28.00

info3.calcularDesconto(); // Saída: O preço descontado do produto Pelúcia, que custava R$ 60.00, é de R$ 54.00
```
