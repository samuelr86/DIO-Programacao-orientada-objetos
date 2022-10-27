# Programação Orientado a Objetos

## Porque usar?
Antes da POO imperava um outro paradigma, o estruturado, com exemplo principalmente da linguagem C. Algumas diferenças entre os paradigmas facilitam no momento em que decidimos qual ferramenta usar.
### Programação Estruturada vs Programação Orientada Objetos
O Paradigma Estruturado ou PE tem uma representação mais simplista.
O Paradigma Orientado a Objetos, ou POO, tem uma representação mais realista.
POO tem mais mecanismos e mais avançados em relação a PE. 
PE foca em operações e dados, manipulação de dados brutos.
POO foca na modelagens de entidades e nas interações entre eles,  nivel abstr.
PE foca mais no "como fazer".
POO foca mais no "o que fazer".
VANTAGENS DA POO
 -Melhor coesão
 -Melhor acoplamento
 -Diminuição do Gap semântico
 -Tem Coletor de lixo(limpa trechos de código não utilizados, liberando espaço).

## Os Fundamentos
### Definição 
é um paradigma de análise, projeto e programação de sistemas de software baseado em composição e interação entre as diversas unidade de software chamadas objetos.
são divididos em três pilares principais: abstração, reuso e encapsulamento.
### Abstração
processo pelo qual se isolam características de um objeto, considerando os que tenham em comum certos grupos de objetos.
### Reuso
capacidade de criar novas unidades de código a partir de outras já existentes.
### Encapsulamento
capacidade de esconder complexidades e proteger dados.

## A estrutura
### Classe
é uma estrutura que abstrai(serve de molde) um conjunto de objetos com características similares. Define o comportamento de seus objetos através de métodos e os estados possíveis deste objetos através dos atributos. Em outras palavras descreve os serviços providos por seus objetos e quais informações eles podem armazenar.
Dicas de criação:
-substantivos
-nomes significativos

#### *Exerc1. Criar uma classe Carro
```
class Carro {

}
```
### Atributo
é o elemento de uma classe responsável por definir sua estrutura de dados, ou por representar suas características.
Dicas de criação:
-substantivos e adjetivos
-nomes significativos
-contexto deve ser considerado
-tipos adequados

#### *Exerc2. Defina três atributos para a classe Carro
```
class Carro{
    String cor;
    String modelo;
    int capacidadeTanque;
}
```
### Método
é uma porção de código(sub-rotina) que é disponibilizada pela classe. é executado quando é feita uma requisição a ele. Identifica ações, serviços que a classe oferece.
Criação de métodos:
-visibilidade
-retorno
-nome
-parâmetros
Dicas para criação:
-verbos
-nomes significativos
-contexto deve ser considerado
Há dois métodos especiais:
-Construtor
    -constrói objetos a partir das classes.
    -provê valores iniciais caso necessite.
    -não tem retorno.
    -construtor vazio automaticamente fornecido pela classe.
-Destrutor
    -auxilia a destruição de um objeto.
    -retorno void.
    -nome 'finalize'.

Sobrecarga:
-mudar a assinatura de um método de acordo com o a necessidade 

#### *Exerc3. Crie um método para calcular o valor total para encher o tanque.
```
class Carro{
    String cor;
    String modelo;
    int combustivelTanque;
    int capacidadeTanque = 55;

    Carro(){}

    Carro(String cor, String modelo){
        this.cor = cor;
        this.modelo = modelo;
    }

    void setCor(String cor){
        this.cor = cor;
    }
    String getCor(){
        this.cor;
    }
    void setTanque(int combustivel){
        this.capacidadeTanque += combustivel;
    }
    int getTanque(){
        this.capacidadeTanque;
    }
    double encherTanque(int combustivel){
        setTanque(combustivel);
        double valorGasoline = 3.4;
        double total = combustivel * 3.4;
        return "Total pago é de $" + total;
    }

}
```
### Objeto
um objeto é a representação de um conceito do mundo real, que pode ser física ou conceitual e possui um significado bem definido para um determinado software.
Forma de criação em java;

```
Carro carro = new Carro()// com construtor default;
```
### Mensagem
é o processo de ativação de um método de um objeto. Isto ocorre quano uma requisição a esse método é realizada, assim disparando a execução de seu comportamento descrito por sua classe.
é alguma lógica que seja executada, isso é chamada de mensagem.

```
Carro.<método>; // mensagem via classe
carro.<método>; // mensagem via objeto
```
#### *Exerc4. Crie objetos da classe Carro e use metodos get/set. Passe também uma mensagem para o cálculo do total para encher o tanque.

```
class App{
    static void main(String[] args){

        Carro carro = new Carro();

        carro.setModelo("Gol");
        
        System.out.println(carro.getTanque()); // 0

        carro.encherTanque(55); // Total pago é de $187

        System.out.println(carro.getTanque()); // 55
    }
}
```

## As relações

## A Organização