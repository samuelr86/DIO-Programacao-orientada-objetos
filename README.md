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

## A Estrutura
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

## As Relações (Herança, Associação e Interface)

### Herança
é um relacionamento entre classes em que uma classe chamada de subclasse é uma extensão, um subtipo, de outra classe chamada superclasse.
Devido a isto, a subclasse consegue reaprovietar os atributos e métodos dela. Além dos que venha  aser herdados, a subclase pode definir seus próprios membros (atributos e métodos).
a herança é usada para criar subtipos mais especializados.

```
class A extends B {

}
```
#### Exerc 1 - Crie a classe "Veículo", Carro e Moto. Faça a relação de herança que julgar necessária.

```
class Veiculo{

}
class Carro extends Veiculo{

}
class Moto extends Veiculo{

}
```

### Polimorfismo e Sobrescrita
 - Polimorfismo:  a mesma ação, se comportando diferente.

quando uma subclasse faz uso de um método e se comportando de acordo como o objeto em questão.
 - Sobrescrita: a mesma ação, podendo se comportar diferente.

quando uma subclasse pode fazer uso de um método da superclasse rescrevendo ou não.

### Associação
possibilita um relacionamento entre classes/objetos no qual estes possam pedir ajuda a outras classes e representar de forma completa o conceito ao qual se destinam. Neste tipo de relacionamento, as classes e os objetos interagem entre si para atingir seus objetivos.

#### Tipos
 - Estrutura:
    - Composição: "Com parte todo"
        - Uma parte(endereço) só existe se tiver o todo(Pessoa), se Pessoa deixar de existir, Endereco também deixa de existir.
        
        ```
        class Pessoa{
            Endereco endereco;
        }
        ```

    - Agregação: "Sem parte todo"
        - Uma parte(Aluno) pode existir sem o todo(Disciplina).

        ```
        class Disciplina{
            Aluno aluno;
        }
        ```

 - Comportamental:
    - Dependência: "Depende de" 
        - Uma parte(Compra) depende de outra(Cupom)

        ```
        class Compra {
            Cliente cliente;

            finalizar(Cupom cupom){}
            finalizar(){}
        }

        class Cupom{

        }
        ```
### Interface
define um contrato que deve ser seguido pela classe que a implementa. Quando uma classe implementa uma interface, ela se compromete a realizar todos os comportamentos que a interface disponibiliza.

```
interface A{
    ...
}

class B implements A{
    ...
}
```

#### Exerc 2 - Crie uma interface chamada OperacaoMatematica, também crie 4 métodos das operações básicas.

```
interface OperacaoMatematica{
    void soma(double operando1, double operando2);
    void subtracao(double operando1, double operando2);
    void multiplicacao(double operando1, double operando2);
    void divisao(double operando1, double operando2);
}
```

## A Organização

### Pacotes
são uma organização física ou lógica criada para separar classes com responsabilidades distintas. Com isso, espera-se que a aplicação fique mais organizada e seja possível separar classes de finalidades e representatividades diferentes.

```
//criar pacotes
package <nome do pacote>;

//usar uma classe que está em outro pacote
import <nome da classe>;

```

### Visibilidade
também chamadas de modificadores de acesso, tem como finalidade determinar até que ponto uma classe, atributo ou método pode ser usado. A utilização de modificadores de acesso é fundamental para o uso efetivo da Orientação a Objetos. Algumas boas práticas e conceitos só são atingidos como o uso corretos deles.

#### Tipos

    - public
        - visível em qualquer lugar


    ```
        public int i;
        public void do ();
    ```

    - protected
        - visível dentro da classe, mesmo pacote e subclasses

    ```
        protected int i;
        protected void do();
    ```

    - private
        - visível só dentro da classe

```
        private int i;
        private void do();
```


