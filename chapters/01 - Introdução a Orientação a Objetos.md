# Introdução a Orientação a Objetos

## Introdução á programação orientada a objetos
A Orientação a Objetos é um paradigma de programação baseada no conceito de “objetos”, que contém características, comportamentos e estados. Cada objeto é independente e exerce um papel no software. Você pode criar diversos objetos diferentes. Dessa forma cada objeto “interage” com outros objetos na resolução de um problema.

Assim como o mundo real é constituído de objetos, da mesma forma o é o software orientado a objetos. Em uma linguagem de programação OO pura, tudo é um objeto, desde os tipos mais básicos, como inteiros e lógicos, até instâncias de classe mais complexas; nem todas as linguagens orientadas a objetos chegam a esse ponto. Em algumas como Java, primitivas como int e float, não são tratadas como objetos. 

Orientação a objetos é um paradigma de programação que representa uma evolução natural a outros paradigmas precursores como o Procedural e o Modular. Ela permite que você programe em um nível mais conceitual do domínio do problema o fazendo pensar em seus programas em termos naturais e reais. Em vez de modelar seu programa como um conjunto de procedimentos e dados separados (termos do mundo dos computadores), você modela seu programa em objetos. Os objetos permitem que você modela seus programas no substantivos, verbos e adjetivos do domínio de seu problema.

Quando recua e pensa nos termos do problemas que está se resolvendo, você evita se emaranhar nos detalhes da implementação. É claro que alguns de seus objetos de alto nível precisarão interagir com o computador. Entretanto, o objeto isolará essas interações do restante do sistema. 

### Objeto 
Um objeto é uma construção de software que encapsula estado e comportamento. Os objetos permite que você modele seu software em termos reais e abstrações. 
Rigorosamente falando, um objeto é uma instância de uma classe. 

### Classe
Assim como no mundo real, o mundo da POO grupa os objetos pelos seus comportamentos e atributos comuns. 
A biologia classifica todos os cães, gatos, elefantes e seres humanos como mamíferos. Características  compartilhadas dão a essas criaturas separadas um senso de comunidade. No mundo do software, as classes agrupam objetos relacionados da mesma maneira. 

Uma classe define todas as características comuns a um tipo de objeto. Especificamente, a classe define todos os atributos e comportamentos expostos pelo objeto. A classe define a quais mensagens seus objetos respondem. Quando um objeto quer exercer o comportamento de outro objeto ele não faz isso diretamente, mas pede ao outro objeto que se mude, normalmente baseado em alguma informação adicional. Frequentemente, isso é referido como ‘envio de mensagem’.

#### Definição Formal 

Uma classe define os atributos e comportamentos comuns compartilhados  por um tipo de objeto. Os objetos de certo tipo ou classificação compartilham os mesmo comportamentos e atributos. As classes atuam de forma muito parecida com um cortador de molde de biscoito, no sentido de que você usa uma classe para criar ou instanciar objetos.

### Atributos
São as características de uma classe visíveis externamente. A cor dos olhos e a cor dos cabelos são exemplos de atributos. Um objeto pode expor um atributo fornecendo um link direto a alguma variável interna ou retornando um valor através de um método. 

### Comportamento 
Comportamento é uma ação executada por um objeto quando passada uma mensagem  ou em resposta a uma mudança de estado: é algo que um objeto faz. 
Um objeto pode exercer o comportamento de outro , executando uma operação sobre esse objeto. Você pode ver os termos chamada de método, chamada de função ou passar uma mensagem, usados em vez de executar uma operação. O que é importante é que cada uma dessas ações omite o comportamento de um objeto. 

### Construtores de Classe 
Construtores são “métodos” especiais usados para inicializar objetos durante sua instanciação. Você chama a criação de objetos de instanciação porque ela cria uma instância do objeto da classe. 

### Acessores 
Os acessores dão acesso aos dados internos de um objeto. Entretanto, os acessores ocultam o fato de os dados estarem em uma variável, em uma combinação de variáveis ou serem calculados. Os acessores permitem que você mude ou recupere o valor e têm ‘efeitos colaterais’ sobre o estado interno. 

### Mutantes
Os mutantes permitem que você altere o estado interno de um objeto.
Nota: No mundo Java os acessores são os Getters e os Setters do Padrão Java Bean.

### Relacionamentos de objeto.
O modo como os objetos se relacionam é um componente muito importante da POO. Os objetos podem se relacionar de duas maneiras importantes. 
Primeiro, os objetos podem existir independentemente uns dos outros. Dois objetos de Item podem aparecer no carrinho de compras simultaneamente . Se esses dois objetos separados precisarem interagir, eles interagirão passando mensagens um para o outro.
Os objetos se comunicam uns com os outros através de mensagens. As mensagens fazem com que o objeto realize algo. 
Passar uma mensagem é o mesmo que chamar um método para mudar o estado do objeto ou para exercer um comportamento. 
As mensagens são um importante conceito em OO. Elas permitem que os objetos permaneçam independentes. Quando uma objeto envia uma mensagem para outro, geralmente ele não se preocupa com a maneira como o objeto escolhe transportar o comportamento solicitado. O objeto solicitante se preocupa apenas que o comportamento aconteça.
Segundo, um objeto poderia conter outros objetos. Assim, como os objetos compõem um programa em POO, eles podem compor outros objetos através da agregação.

### Resumo
Hoje, fizemos um passeio pela programação orientada a objetos. Você começou vendo a evolução dos principais paradigmas de programação e aprendeu alguns dos fundamentos da POO. Agora, você deve entender as ideias conceituais por trás da OO, como o que é uma classe e como os objetos se comunicam. 
Definições são importantes, mas nunca devemos perder o rumo do que estamos tentando fazer usando OO, nos atendo ao ‘como’ do que estivermos fazendo. As seis vantagens e objetivos resumem o que a programação orientada a objetos espera cumprir: 

* Natural 
* Confiável 
* Reutilizável  
* Manutenível 
* Extensível 
* Oportuna 

Você nunca deve perder esses objetivos de vista.
