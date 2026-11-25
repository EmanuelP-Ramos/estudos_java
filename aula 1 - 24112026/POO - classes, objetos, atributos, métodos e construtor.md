
O JAVA é uma linguagem baseada em orientação a objetos, ou seja, tudo é uma instância de um objeto ou uma classe com métodos estáticos.
Essa funcionalidade permite atalhos conhecidos como pilares de POO : herança, polimorfismo, encapsulamento e abstração.

Mas afinal, *lo que porras es una classe ?*, nada mais é que uma forma, um molde, uma blueprint, após ser criada, basta encaixar as peças e ter uma instância dela, ou seja, um objeto. No JAVA, temos a mínima classe de acordo com o exemplo:

```java
public class Exemplo{
	public static void main (String args[ ]){
		Desktop meu_pc = new Desktop("R5 5500","B550M",16,"DDR4",RX7600)
		System.out.orint.ln(meu_pc.overView())
	}
	public class Desktop{
		private String CPU;
		private String motherboard;
		private int ram;
		private String ram_type;
		private GPU_list gpu;
		
		public Desktop(String CPU,String motherboard,int ram, String ram_type,                            GPU_list gpu){
		this.CPU = CPU;
		this.motherboard = motherboard;
		this.ram = ram;
		this.ram_type = ram;
		this.gpu = gpu;
		}
		
		public String overView(){
			return "this pc have the following specs :"+this.cpu+
			" "+this.motherboard+" "+this.ram+"GB "+this.gpu;
		}
	
	}
}
```

### A classe
Observando acima temos todos os elementos que compõem uma classe : atributos, métodos, o construtor e a própria classe. Note a linha da *"public class Desktop"*, ela composta pelos seguintes elementos :

**public** --> limitador de acesso que permite que a classe seja chamada em qualquer lugar;
**class** --> palavra reservada que define a criação de uma classe;
**desktop** --> nome que demos para a classe

### Os atributos
Abaixo dela o próximo bloco são os atributos da classe, funcionam como variaveis que irão guardar as informações do objeto quando instanciado, a sintaxe básica é :

**private** --> limitador de acesso para somente dentro da própria classe;
**string/int**--> são os tipos dos dados que serão guardados, podem ser vários outros, também podem ser estruturas de dados, enums e outro objeto
**CPU/motherboard**--> é apenas o nome que demos pr'aquele atributo em questão

### O construtor
Em seguida um método especial, o construtor é responsável por pegar as entradas que usuário define, guardar as informações nos atributos e realizar a inicialização.
Seguindo a sintaxe de um método, ele tem dois pontos especiais :
o nome deve ser o mesmo da classe e ele não tem definição de retorno

**public** --> limitador de acesso, deve ser publico;
**Desktop** --> o mesmo nome da classe;
**(String CPU,String motherboard...)**--> esses são os parâmetros, são os requisitos mínimos para que o objeto seja instanciado.

Dentro do corpo da função que é entre os colchetes, definimos o que citei antes, a alocação dos valores para os atributos.

### Os métodos
Para finalizar o exemplo, vemos um exemplo básico de método.
Métodos são ações que um objeto ou uma classe conseguem fazer, nesse caso do exemplo, ele emite uma mensagem que diz as configurações do desktop. 

**public** --> modificador de acesso, mesma coisa dos anteriores, apenas define em qual escopo posso chamar o método;
**String/void/int** --> é o tipo que é retornado pelo método, se declarado algum que nao seja void, o emprego do return é obrigatorio
**overView** --> nome do método, deve resumir o que método faz
**()** --> os parenteses representam os parametros que são usados no método, em uma analogia é como se fosse a árvore que entra numa maquina de fazer tábuas, no caso do exemplo ele está vazio porque usa os atributos da própria classe

Dentro dos colchetes temos o bloco de código do método, ele é responsável por ser a lógica por trás dessa função, recebe dos parâmetros as informações e as utiliza para realizar as operações internas, no caso do exemplo, ele junta tudo em uma string para retornar as specs do desktop.


