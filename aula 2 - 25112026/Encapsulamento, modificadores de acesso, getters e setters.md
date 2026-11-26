
Finalizando o estudo sobre classes, veremos mais aprofudadamente sobre os **modificadores de acesso**, os métodos chamados de **getters e setters** e uma introdução sobre pilares de POO começando pelo **encapsulamento**

### Modificadores de acesso

São palavras reservadas que determinam onde pode-se chamar um método ou alterar uma váriavel.
No Java temos 4 modificadores de acesso :

-  **Public**
	---> o público não tem nenhum nível de bloqueio, dá para chamar o método em qualquer lugar do código desde que o escopo permita, assim como se um atributo tiver esse modificador, é possível alterá-lo diretamente no objeto por meio de um `nomedoobjeto.atributo = novovalor` , o public não é recomendado como modificador de acessos de atributos já que em projetos grandes não queremos a possibilidade de que seja possível mexer na parte interna de uma classe, é usado quando precisamos que algo acesse aquela classe/atributo/método;
 ^78a94f
- **Private** 
	---> Enquanto o public permite acesso livre, o private é o exato oposto, ele não permite acesso externo nenhum, normalmente usado nos atributos. Com esse modificador de acesso só é possível dentro da própria classe de origem, é o mais seguro e o responsável por complementar a lógica dos **getters e setters**;
 ^07ada4
- **Package-private** 
	---> Esse em específico funciona como o private, limita a visibilidade, mas o escopo é dentro do mesmo pacote, fora dele não é possível acessar, para declará-lo basta não colocar nada
	`ex : class calculator{}`;

- **Protected** 
	---> Por último, o protected, definido pela palavra reservada "protected", assim como o package-private, permite o uso dentro do próprio pacote, mas esse tem o adicional de que as classes filhas, ou seja, quando temos herança, conseguem acessar.


Exemplo de uso de cada um dos modificadores :
```java
package com.banco.contas;
import java.util.List;

public class exemplo1{
	public static void main (String args[]){
		public class contabancaria{
			private String nome_titular;
			private String cpf;
			private BigDecimal saldo;
			private List<String> logs = new ArrayList<>()
		
			public contabancaria(String nome_titular,String cpf,Double saldo){
				this.nome_titular = nome_titular;
				this.cpf = cpf;
				this.saldo = saldo;
			}
		
			public void depositar(BigDecimal valor){
				if(valor.compareTo(BigDecimal.ZERO) > 0){ 
					this.saldo = this.saldo.add(valor);
					registrarLog("conta bancária recebeu depósito no valor                                          de"+valor+"R$") 
				}
				else{
					throw new illegalArgumentException("O valor do depósito deve                       ser maior que zero");
				}
			}
		
			private void registrarLog(String msg){
				logs.add(msg);
			}
			
			public List<String>: logHistory(){
				return List.copyof(logs);
			}
		}
		
		public BigDecimal getSaldo(){
			return this.saldo;
		}
		
		class CalculadoraJuros{
			///lógica de calculo dos juros
		}
	}
}
```

Considerando o exemplo acima, podemos notar como são usados os modificadores de acesso para manter a segurança e a funcionalidade do código, além disso notamos um tipo de método que tem o prefixo de get.
Quando privamos um atributo, impedimos que possa ser acessado diretamente por notação de ponto (objeto.atributo), mas em muitos casos precisamos ter a informação do que está guardado no atributo, para isso usamos um **getter**, que, resumidamente, é um método que retorna o valor na variável de instância, isso permite que acessemos sem ter o risco de que seja trocado o valor de maneira indevida.
Enquanto o getter serve para puxarmos a informações, o **setter** é para definir de maneira segura, nele que organizamos um bloco dedicado ao tratamento da entrada, como a lógica que impede que um valor especifico seja associado, ou apenas fazer a alteração diretamente.

### Encapsulamento 

Encapsulamento é o primeiro dos pilares que veremos, seu objetivo central é transformar a classe numa caixa preta, você coloca os dados e tem um retorno, não precisa saber e nem ter o acesso à como é a lógica por trás dos métodos, é tipo dirigir um carro, não se sabe como o volante vira os pneus, mas sabe-se que rotacionar pra esquerda faz o carro ir pra esquerda.
Tendo essa ideia, podemos manter o código dessa forma com uso dos já citados anteriormente : getters e setters, eles ficam responsáveis por encapsular os meios de acesso dos atributos.
Mas mais importante é saber quando usar e na verdade é bem simples, se precisa ser visto por alguém, usa o getter; precisa ser alterado ? usa um setter com validação; se nao precisa ser acessado ou alterado, então não coloca.
Desta forma, por meio desse pilar mantemos um código mais seguro e mais limpo para trabalhar, quando, mais encapsulado for, menos problema dá quando for usar os métodos já que a lógica interna estará bem sólida.