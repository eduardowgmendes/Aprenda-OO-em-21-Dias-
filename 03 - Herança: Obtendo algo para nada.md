# Herança: Obtendo algo para nada 

## Herança 
A herança permite que você baseie a definição de uma nova classe em uma classe previamente existente. Quando você baseia uma classe em outra, a definição da nova classe herda automaticamente todos os atributos, comportamentos e implementações presentes na classe previamente existente.
Herança é um mecanismo que permite a você basear uma nova classe na definição de uma classe previamente existente. Usando herança, sua nova classe herda todos os atributos e comportamentos presentes na classe previamente existente. Quando uma classe herda de outra, todos os métodos e atributos que aparecem na interface da classe previamente existente aparecerão automaticamente na interface da nova classe.

## “É um” versus “tem um”
Para apresentar os mecanismos de herança, a primeira seção abordou o que é conhecido como herança de implementação. Conforme você viu, a herança de implementação permite que suas classes herdem a implementação de outras classes. Entretanto, somente porque uma classe pode herdar de outra não significa que isso deve ser feito! 
Então, como você sabe quando deve usar herança? Felizmente, existe uma regra geral a ser seguida, para evitar uma herança incorreta.
Quando você está considerando a herança para reutilização ou por qualquer outro motivo, precisa primeiro perguntar-se se a classe que está herdando é do mesmo tipo que a classe que está sendo herdada. O fato de pensar em termos de tipo enquanto se herda é frequentemente referido como teste ‘é um’.

## O Teste ‘É UM’
É um descreve o relacionamento em que uma classe é considerada do mesmo tipo de outra.
Para usar ‘é um’, você diz a si mesmo, ‘um determinado objeto é um objeto’. Substitua objeto por qualquer objeto que considere usar em seu projeto. Se essa declaração for verdadeira você saberia imediatamente que a herança é válida nessa situação. 
Existirão muitas situações onde o teste é um falhará, quando você quiser reutilizar alguma implementação. Felizmente, existem outras maneiras de reutilizar implementação. Você sempre pode usar composição e delegação. 

## O Teste ‘TEM UM’
Tem um descreve o relacionamento em que uma classe contém uma instância de outra classe. 
Composição
Composição significa que uma classe é implementada usando-se variáveis internas (chamadas de variáveis de membro), que contém instâncias de outras classes. 

## Sobreposição
Os métodos e atributos protegidos são aqueles aos quais você deseja que apenas as subclasses tenham acesso. Não deixe tais métodos públicos. Apenas aqueles com amplo conhecimento da classe devem usar métodos e atributos protegidos. Isso significa não expor funcionalidades internas como métodos da classe em sua interface pública mas sim as suas filhas para que elas herdem a implementação. Não é de utilidade alguma expor esses métodos aos outros objetos já que eles são de composição intrínseca de sua própria classe. 	
Pense: para que eu iria expor a maneira como eu pago as minhas contas ou até mesmo o modo como eu me alimento às outras pessoas? Isso é parte do como eu faço algo ou seja a minha implementação. Nem TODOS os comportamentos devem ser expostos as subclasses ou são interessantes para elas.

## Formas de Sobreposição 
###Novos métodos e atributos 
Um novo método ou atributo é um método ou atributo que aparece na filha, mas não aparece na progenitora. A filha acrescenta o novo método ou atributo em sua interface. Você viu novos métodos no exemplo ThreeDimensionalPoint. ThreeDimensionalPoint acrescenta os novos métodos getZCoordinate() e setZCoordinate(). Você pode adicionar nova funcionalidade na interface de sua filha, adicionando novos métodos e atributos.
Métodos e atributos recursivos
Um método ou atributo recursivo é definido na progenitora ou em alguma outra ancestral, mas não na filha. Quando você acessa o método ou atributo, a mensagem é enviada para cima na hierarquia, até que uma definição do método seja encontrada. O mecanismo é igual àquele apresentado na seção sobre métodos e atributos sobrepostos.
Você viu métodos recursivos no código-fonte de TwoDimensionalPoint e ThreeDimensionalPoint. getXCoordinate() é um exemplo de método recursivo, pois ele é definido por TwoDimensionalPoint e não por ThreeDimensionalPoint.
Os métodos sobrepostos também podem se comportar de forma recursiva. Embora um método sobreposto apareça na filha, a maioria das linguagens orientadas a objetos fornece um mecanismo que permite a um método sobreposto chamar a versão da progenitora (ou de algum outro ancestral) do método. Essa capacidade permite que você enfatize a versão da superclasse, enquanto define novo comportamento na subclasse. Na linguagem Java, a palavra-chave super dá acesso à implementação de uma progenitora.

## Tipos de Herança
Ao todo, existem três maneiras principais de usar herança:
    1. Para reutilização de implementação 
    2. Para diferença 
    3. Para substituição de tipo 
Esteja avisado de que alguns tipos de reutilização são mais desejáveis que outros! Vamos explorar cada uso em detalhes. 

## Herança para implementação
Você já viu que a herança possibilita que uma nova classe reutilize implementação de outra classe. Em vez de recortar e colar código ou instanciar e usar um componente através de composição, herança torna o código automaticamente disponível, coo parte da nova classe. Como mágica, sua nova classe nasce com funcionalidade.
Lembre-se de que, quando programa com herança de implementação, você está preso à implementação que herda. Escolha as classes que herdará com cuidado. Você precisará ponderar as vantagens da reutilização em relação a todos os fatos negativos de reutilizar algumas implementações. 
Entretanto, uma classe corretamente definida para herança fará bastante uso de métodos protegidos refinados. Uma classe que herda pode sobrepor esses métodos protegidos para alterar a implementação. A sobreposição pode diminuir o impacto da herança de uma implementação mal feita ou inadequada.

### Problemas da herança da implementação 
Até aqui, a herança de implementação parece excelente. Cuidado, contudo – o que parece uma técnica útil na superfície se mostra uma prática perigosa no uso. Na verdade, a herança de implementação é a forma mais deficiente de herança e normalmente você deve evitá-la. A reutilização pode ser fácil, mas, conforme você verá, ela tem um alto preço. 
Para entender as falhas, você precisa considerar os tipos. Quando uma classe herda de outra, ela assume automaticamente o tipo da classe herdada. A herança de tipo correto sempre deve ter precedência, ao se projetar hierarquias de classe, ou seja, somente escolha herdar um tipo quando fizer sentido. Você verá os motivos posteriormente, por enquanto, assuma isso como verdade.
Dê uma olhada no exemplo Queue/Iterator novamente. Quando Iterator herda de Queue, ela se torna um a Queue. Isso significa que você pode tratar Iterator com o se fosse do tipo Queue. Como Iterator também é uma Queue, ela tem toda a funcionalidade que estava presente na Queue. Isso significa que os métodos como enqueue()e dequeue() também fazem parte da interface pública de Iterator. 
Superficialmente, isso não parece ser um problema, mas dê uma olhada melhor na definição de Iterator. Uma interface Iterator simplesmente define dois métodos, um para recuperar um elemento e outro para testar se restam quaisquer elementos no Iterador. Por definição, você não pode adicionar itens em um Iterador; entretanto, Queue define o método enqueue() justamente para um caso assim. Em vez disso, você só pode remover elementos. Você não pode pegar um elemento e, ao mesmo tempo, deixá-lo dentro da interface Iterator. Novamente, Queue define o método peek(), justamente para esse caso. E simples ver que usar Queue como uma base herdada para Iterator não é uma boa escol ha; isso fornece comportamentos que simplesmente não pertencem a uma interface Iterator.
Uma herança pobre é o monstro de Frankenstein da programação. Quando você usa herança unicamente para reutilização de implementação, sem quaisquer outras considerações, frequentemente pode acabar com um monstro construído a partir de partes que não se encaixam.

## Herança para diferença
Você viu a herança para diferença no exemplo de TwoDimensionalPoint e ThreeDimensiona1Point. Você também a viu no exemplo Employee. 
A programação pela diferença permite que você programe especificando apenas como uma classe filha difere de sua classe progenitora. 
Programação por diferença significa herdar uma classe e adicionar apenas o código que torne a nova classe diferente da classe herdada.
No caso de ThreeDimensiona1Point, você vê que ela difere de sua classe progenitora pelo acréscimo de uma coordenada Z. Para suportar a coordenada Z, ThreeDimensiona1Point adiciona dois novos métodos para configurar e recuperar o atributo. Você também vê que ThreeDimensiona1Point redefine o método toString();
A programação por diferença é um conceito poderoso. Ela permite que você adicione apenas o código necessário o suficiente para descrever a diferença entre a classe progenitora e a classe filha. Isso permite que você programe através de incrementos. 
Um código menor e mais fácil de gerenciar torna seus projetos mais simples. E como você programa menos linhas de código, teoricamente deve introduzir menos erros. Assim, quando programa pela diferença, você escreve código mais correto em um espaço de tempo mais curto. Assim como a herança de implementação, você pode fazer essas alterações incrementais sem alterar o código existente. 
Através da herança, existem duas maneiras de programar pela diferença: adicionando novos comportamentos e atributos, e redefinindo comportamentos e atributos antigos. Cada caso é conhecido como especialização. Vamos ver detalhadamente a especialização. 

## Especialização 
Especialização é o processo de uma classe filha ser projetada em termos de como ela é diferente de sua progenitora. Quando tudo estiver dito e feito, a definição de classe da filha incluirá apenas os elementos que a tornam diferente de sua progenitora. 
Uma classe filha se especializa em relação à sua progenitora, adicionando novos atributos e métodos em sua interface, assim como redefinindo atributos e métodos previamente existentes. A adição de novos métodos ou a redefinição de métodos já existentes permite que a filha expresse comportamentos que são diferentes de sua progenitora. 
Não se confunda com o termo especialização. A especialização permite apenas que você adicione ou redefina os comportamentos e atributos que a filha herda de sua progenitora. A especialização, ao contrario do que o nome possa sugerir, não permite que você remova da filha comportamentos e atributos herdados. Uma classe não obtém herança seletiva. 
O que a especialização faz é restringir o que pode e o que não pode ser um ponto tridimensional. Um ThreeDimensionalPoint sempre pode ser um TwoDimensionalPoint. Entretanto, é incorreto dizer que um TwoDimensionalPoint sempre pode ser um ThreeDimensiona1Point.
Em vez disso, um ThreeDimensiona1Point é uma especialização de um TwoDimensionalPoint e um TwoDimensionalPoint é uma generalização de um ThreeDimensiona1Point.
A figura ilustra a diferença entre generalização e especialização. Quando você percorre uma hierarquia para baixo, você se especializa. Quando você percorre uma hierarquia para cima, você generaliza. À medida que você generaliza mais classes podem cair sob esse agrupamento. À medida que você especializa, menos classes podem satisfazer todos os critérios para serem classificadas nesse nível. 
Quando percorre uma hierarquia para cima, você generaliza. Quando percorre uma hierarquia para baixo, você especializa. 

Como você vê, especialização não significa uma restrição de funcionalidade, ela significa restrição de categorização de tipo. A especialização não precisa acabar com ThreeDimensiona1Point. Na verdade, ela não precisa necessariamente nem mesmo começar com TwoDimensionalPoint. A herança vai ter a profundidade que você quiser. Você pode usar herança para formar estruturas de hierarquia de classes complexas. A noção de hierarquia introduzida anteriormente leva a mais dois termos novos: ancestral e descendente.
Apenas porque você pode ter hierarquias complicadas não significa que deva tê-las. Você deve se esforçar por ter hierarquias pouco profundas e não hierarquias demasiadamente profundas. À medida que uma hierarquia se aprofunda, ela se torna mais difícil de manter.

## Ancestral
Dada alguma filha, um ancestral é uma classe que aparece na hierarquia de classes antes da progenitora. Também é possível usar outra definição para classes ancestrais: Classe Raiz.

## Descendente
Dada uma classe, toda classe que aparece depois dela na hierarquia de classes é uma descendente da classe dada. Outra definição para classes descendentes: Classe Folha.

## Herança para Substituição de Tipo
O Tipo final de herança é a herança para substituição de tipo. A substituição de tipo permite que você descreva relacionamentos com capacidade de substituição. Oque é um relacionamento com capacidade de substituição?
Um relacionamento com capacidade de substituição significa que você pode passar um objeto como se fosse outro objeto na hierarquia de classes. Por exemplo, dado um construtor que recebe como argumento objetos TwoDimensionalPoint. Você pode passar ou um TwoDimensionalPoint ou qualquer objeto que herde de TwoDimensionalPoint para esse construtor, ou seja, um ThreeDimensionalPoint.
Lembre-se que quando uma filha herda de sua progenitora, você diz que a filha é uma progenitora. Assim, como um objeto ThreeDimensionalPoint é um objeto TwoDimensionalPoint, você pode passar um objeto ThreeDimensionalPoint para o construtor.
Capacidade de conexão é um conceito poderoso. Como você pode enviar a uma filha qualquer mensagem que pode ser enviada para sua progenitora, é possível tratá-la como se ela pudesse ser substituída pela progenitora. Esse é o motivo pelo qual você não deve remover comportamentos ao criar uma filha. Se você fizer isso, a capacidade de conexão será invalidada.
Usando a capacidade de conexão, você pode adicionar novos subtipos em seu programa, a qualquer momento. Se seu programa for feito para usar uma ancestral, ele saberá como usar os novos objetos. O programa não precisará se preocupar com o tipo exato do objeto. Desde que tenha um relacionamento com capacidade de substituição com o tipo que espera que possa usar.
### Cuidados
Relacionamentos com capacidade de substituição só podem ir até UM nível acima na hierarquia de herança. Se você programar seu objeto para aceitar determinado tipo de objeto, não poderá passar para ele a progenitora do objeto esperado. Entretanto, você pode passar para ele qualquer descendente.

## Dicas para a Herança Eficaz
A herança vem com seu próprio conjunto de problemas de projeto. Embora seja poderosa, na verdade a herança fornece a corda para você se enforcar, quando usada incorretamente. As dicas a seguir o ajudarão a usar a herança eficazmente: 
Em geral, use herança para reutilização de interface e para definir relacionamentos de substituição. Você também pode usar herança para estender uma implementação, mas somente se a classe resultando passar no teste ‘é um’.
Em geral, prefira a composição em vez da herança para reutilização de implementação simples. Use herança apenas de você puder aplicar o teste ‘é um’ na hierarquia resultante. Não use herança para reutilização de implementação ambiciosa.

## Sempre use a regra ‘é um’.
As hierarquias de herança corretas não acontecem sozinhas. Frequentemente, você descobrirá hierarquias á medida que prosseguir. Quando isso acontecer, refaça seu código. Em outras ocasiões, você precisará projetar deliberadamente suas hierarquias. De qualquer modo, existem alguns princípios de projeto a seguir:
    - Como regra geral, mantenha suas hierarquias de classe relativamente rasas. 
    - Projete cuidadosamente a hierarquia de heranças e remova as características comuns de classes base abstratas. As classes base abstratas permitem que você defina um método sem fornecer uma implementação. Como a classe base não especifica uma implementação, você não pode instanciá-la. Entretanto, o mecanismo abstrato obriga uma classe que esteja herdando a fornecer uma implementação. As classes abstratas são valiosas para herança planejada. Elas ajudam o desenvolvedor a ver o que elas precisam implementar.
Se sua linguagem não fornece um mecanismo abstrato, crie métodos vazios e documente o fato de que subclasses devem implementar completamente esses métodos. 
    - As classes frequentemente compartilham código comum. Não há sentido em ter várias cópias de código. Você deve remover o código comum e isolá-lo em uma única classe progenitora. Entretanto, não o coloque muito acima. Coloque-o apenas no primeiro nível acima de onde ele é necessário.
    - Simplesmente não é possível planejar sempre suas hierarquias completamente. As características comuns não aparecerão até que você escreva o mesmo código algumas vezes. Quando você ver características comuns, não tenha medo de refazer suas classes. Esse trabalho é frequentemente referido como refazer.
O encapsulamento é tão importante entre progenitora e filho quando entre classes não relacionadas. Não relaxe quanto ao encapsulamento, quando você estiver herdando. A prática de usa uma interface bem definida é tão válida entre progenitora e filha quanto entre classes completamente não relacionadas. Aqui estão algumas dicas que o ajudarão a evitar a quebra do encapsulamento, quando você herdar: 
    - Use interfaces bem definidas entre progenitora e a filha, exatamente como as usaria entre classes. 
    - Se você adicionar métodos especificamente para uso por subclasses, certifique-se de torná-los protegidos, para que apenas a subclasse possa vê-los. Os métodos protegidos permitem que você ofereça às suas subclasses um pouco mais de controle, sem abrir esse controle para toda classe. 
    - Em geral, evite abrir a implementação interna de seu objeto para subclasses. Uma subclasse pode se tornar dependente da implementação, se você fizer isso. Tal acoplamento tem todos os problemas delineados no capítulo sobre encapsulamento. 
Aqui estão alguns segredos finais para herança eficaz:
    - Nunca se esqueça de que a substituição é o objetivo número um. Mesmo que um objeto deva ‘intuitivamente’ aparecer uma hierarquia, isso não quer dizer que ele deve aparecer. Apenas porque é possível ou porque sua intuição clama, não significa que você deve fazer isso.
    - Programe pela diferença para manter o código fácil de gerenciar. 
    - Sempre prefira a composição à herança para reutilização de implementação. Geralmente é mais fácil alterar as classes envolvidas na composição.

## Resumo
Existem dois tipos de relacionamentos fornecidos pela POO: um relacionamento de uso entre objetos e um relacionamento de herança entre classes. Cada relacionamento fornece uma forma de reutilização. Entretanto, cada um vem com suas próprias vantagens e problemas. 
A simples instanciação e uso frequentemente limitam a flexibilidade de uma classe. Através da reutilização simples, não há meios de reutilizar ou estender uma classe. Em vez disso, você fica com uma instanciação simples ou recorte e colagem. A herança supera essas deficiências, fornecendo um mecanismo interno para a reutilização segura e eficiente do código. 
A reutilização de implementação proporciona a você um modo rápido e grosseiro de usar código previamente existente em suas novas classes. Ao contrário da operação de recorte e colagem simples, existe apenas uma cópia do código para manter. Entretanto, simplesmente herdar para reutilizar é imprevidente e limita seus projetos. 
