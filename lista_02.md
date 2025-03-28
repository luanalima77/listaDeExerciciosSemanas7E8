# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.

<h2>Minha resposta da questão 1: A)</h2>

______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0]; 
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i]; 
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'


<h2>Minha resposta da questão 2: A)</h2>
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

<h2>Minha resposta da questão 3: B)</h2>
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.


<h2>Minha resposta da questão 4: D)</h2>
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

<h2> Minha resposta da questão 5: B)</h2>
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

<h2> Minha resposta da questão 6: A)</h2>
______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

<h2>Minha resposta da questão 7:</h2>
<h4>Como a professora Kizzy mencionou em aula, para solucionar essas questões dissertativas, poderia ser usado o JavaScript em vez de pseudocódigo. Então, decidi fazer em JavaScript. </h4>

```javascript
//Classificando os fretes de pedidos menores que R$ 50,00, entre 50 e 199,99 (incluido os dois) e de R$ 200,00 para cima, respectivamente.
function classificarPedidos(pedido){
    if(pedido < 50){
        return "Frete não disponível!";
    }else if (pedido >= 50 && pedido <= 199.99){
        return "Frete com custo adicional!"
    }else{
        return "Frete grátis!";
    }
}

//Aplicando a função em valores distintos.
console.log(classificarPedidos(49));
console.log(classificarPedidos(55));
console.log(classificarPedidos(200));
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

<h2>Minha resposta da questão 8:</h2>
<h4>Como a professora Kizzy mencionou em aula, para solucionar essas questões dissertativas, poderia ser usado o JavaScript em vez de pseudocódigo. Então, decidi fazer em JavaScript. </h4>

```javascript
//Classe Veiculo.
class Veiculo {
    constructor(modelo, ano) {
        this.modelo = modelo;
        this.ano = ano;
    }

    //Método que vai ser sobrescrito nas classes subsequentes.
    calcularConsumo(){}
}

//Classe Carro.
class Carro extends Veiculo {
    constructor(modelo, ano, categoria, eficienciaKmL, quilometragem) {
        super(modelo, ano);
        this.categoria = categoria;
        this.eficienciaKmL = eficienciaKmL;
        this.quilometragem = quilometragem;
    }
    
    //Cálculo do consumo do carro.
    calcularConsumo() {
        return this.quilometragem / this.eficienciaKmL;
    }
}

//Classe Moto
class Moto extends Veiculo {
    constructor(modelo, ano, eficienciaKmL, quilometragem, tipo) {
        super(modelo, ano);
        this.eficienciaKmL = eficienciaKmL;
        this.quilometragem = quilometragem;
        this.tipo = tipo;
    }

    //Cálculo do consumo da moto (que é mais econômica que o carro).
    calcularConsumo() {
        return (this.quilometragem / this.eficienciaKmL) * 0.9; 
    }
}

//Testes.
let carro = new Carro("Civic", 2020, "Sedan", 12.5, 150);
let moto = new Moto("Yamaha YZF R-3", 2021, 20.0, 100, "Esportiva");

console.log(`Consumo do carro ${carro.modelo}: ${carro.calcularConsumo().toFixed(2)} litros`);
console.log(`Consumo da moto ${moto.modelo}: ${moto.calcularConsumo().toFixed(2)} litros`);
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

<h2>Minha resposta da questão 9:</h2>
<h4>Como a professora Kizzy mencionou em aula, para solucionar essas questões dissertativas, poderia ser usado o JavaScript em vez de pseudocódigo. Então, decidi fazer em JavaScript. </h4>

```javascript
function calcularTempoPouso(velocidadeInicial, velocidadeSegura, desaceleracao, tempoMaximo, desaceleracaoMinima) {
    // 1º if: verificando se a desaceleração informada é menor que a aceleração mínima permitida.
    if (desaceleracao < desaceleracaoMinima) {
        return "A desaceleração está abaixo do limite mínimo de desaceleração permitido.";
    }

    // 2º if: verificando se a velocidade inicial já é menor ou igual à velocidade segura.
    if (velocidadeInicial <= velocidadeSegura) {
        return "A velocidade inicial já está abaixo da velocidade segura para pouso.";
    }
    
    // Cálculo do tempo necessário para pouso usando a fórmula: (velocidadeInicial - velocidadeSegura) / desaceleracao. *O tempo foi isolado.
    let tempoNecessarioPouso = (velocidadeInicial - velocidadeSegura) / desaceleracao;
    
    // 3º if: averiguando se o tempo calculado excede o tempo máximo permitido.
    if (tempoNecessarioPouso > tempoMaximo) {
        return `O tempo de descida (${tempoNecessarioPouso.toFixed(2)}s) excede o máximo permitido (${tempoMaximo}s).`;
    }
    
    // Cálculo da desaceleração mínima necessária para cumprir o tempo máximo em questão.
    let desaceleracaoNecessaria = (velocidadeInicial - velocidadeSegura) / tempoMaximo;
    
    // 4º if: averiguando se a desaceleração informada é aplicável no decorrer do tempo máximo.
    if (desaceleracao < desaceleracaoNecessaria) {
        return `A desaceleração é insuficiente. É necessário que ela seja, pelo menos, ${desaceleracaoNecessaria.toFixed(2)}m/s².`;
    }
    
    // Mostrando o tempo seguro para pouso se, de fato, houver esse tempo.
    return `Haverá um pouso seguro possível em ${tempoNecessarioPouso.toFixed(2)} segundos.`;
}


//Testando o código.
// Teste 1: quando a desaceleração está abaixo do mínimo permitido.
let teste1 = calcularTempoPouso(5000, 10, 4, 300, 5);
console.log(`Teste 1 (desaceleração baixa): ${teste1}`);

// Teste 2: quando o tempo de descida ultrapassa o máximo permitido.
let teste2 = calcularTempoPouso(5000, 10, 15, 100, 5);
console.log(`Teste 2 (tempo excedido): ${teste2}`);

// Teste 3: quando a desaceleração é insuficiente para o tempo máximo.
let teste3 = calcularTempoPouso(5000, 10, 16, 300, 5);
console.log(`Teste 3 (desaceleração insuficiente): ${teste3}`);

// Teste 4: quando a velocidade inicial já está segura.
let teste4 = calcularTempoPouso(8, 10, 25, 300, 5);
console.log(`Teste 4 (velocidade já segura): ${teste4}`);

// Teste 5: quando o pouso é bem-sucedido.
let teste5 = calcularTempoPouso(5000, 10, 25, 300, 5);
console.log(`Teste 5 (pouso bem-sucedido): ${teste5}`);
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

<h2>Minha resposta da questão 10:</h2>
<h4>Como a professora Kizzy mencionou em aula, para solucionar essas questões dissertativas, poderia ser usado o JavaScript em vez de pseudocódigo. Então, decidi fazer em JavaScript. </h4>

```javascript
function MultiplicarMatrizesInvestimento(matrizA, matrizB) {
    //Obtendo os tipos de investimento e o número de períodos de tempo para tal.
    let linhasA = matrizA.length;
    let colunasA = matrizA[0].length;
    let linhasB = matrizB.length;
    let colunasB = matrizB[0].length;
    
    // Com base na matemática, uma multiplicação de matrizes só pode acontecer se colunasA for igual a linhasB.
    if (colunasA !== linhasB) {
        return "As matrizes não podem ser multiplicadas. Isso porque o número de colunas da primeira matriz deve ser igual ao número de linhas da segunda matriz.";
    }
    
    // Criando a matriz que é o produto de A e B.
    let matrizResultado = [];
    for (let i = 0; i < linhasA; i++) {
        matrizResultado[i] = [];
        for (let j = 0; j < colunasB; j++) {
            matrizResultado[i][j] = 0;
        }
    }
    
    //Realizando o cálculo tradicional de multiplicação de matrizes.
    for (let i = 0; i < linhasA; i++) {
        for (let j = 0; j < colunasB; j++) {
            for (let k = 0; k < colunasA; k++) {
                matrizResultado[i][j] += matrizA[i][k] * matrizB[k][j];
            }
        }
    }
    
    //A matriz que foi obtida tem que ser retornada.
    return matrizResultado;
}

//Testes.
let investimentos = [[1000, 2000],[1500, 2500]];
let fatoresCrescimento = [[1.1, 1.2],[0.9, 1.3]];
let resultadoMatrizTeste = MultiplicarMatrizesInvestimento(investimentos, fatoresCrescimento);
console.log("Resultado da multiplicação das matrizes:", resultadoMatrizTeste);
```