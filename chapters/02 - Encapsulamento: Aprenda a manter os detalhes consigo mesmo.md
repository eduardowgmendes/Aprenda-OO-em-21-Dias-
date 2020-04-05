# Encapsulamento: aprenda a guardar consigo os detalhes
Em vez de ver um programa como uma única entidade grande e monolítica, o encapsulamento permite que você o divida em várias partes menores e independentes. Cada parte possui implementação e realiza seu trabalho independentemente das outras partes. O encapsulamento mantém essa independência , ocultando os detalhes internos ou seja, a implementação de cada parte através de uma interface externa. 

### Definição Formal
Encapsulamento é a característica da OO de ocultar partes independentes da implementação. O encapsulamento permite que você construa partes ocultas da implementação do software, que atinjam uma funcionalidade e ocultam os detalhes de implementação do mundo exterior. 
Uma vez encapsulado, você pode ver uma entidade de software como uma caixa preta. Você sabe o que a caixa preta faz, pois conhece sua interface externa. Conforme a figura ilustra, você simplesmente envia mensagens para a caixa preta. Você não se preocupa com o que acontece dentro da caixa; você só se preocupa com o fato de que isso aconteça. 

## Interface 
Apesar do termo sobrecarregado usado em diversos contextos, uma interface em OO é uma lista de serviços fornecidos por um componente. A interface é um contrato com o mundo exterior, que define exatamente o que uma entidade externa pode fazer com o objeto. Uma interface é o painel de controle do objeto.
Não confunda o termo com o componente Interface em Java ou Interface Gráfica de Usuário.
Uma interface é importante, pois ela diz o que você pode fazer com o componente. O mais interessante é o que uma interface não informa: como o componente fará seu trabalho. Em vez disso, a interface oculta a implementação do mundo exterior. Isso libera o componente para alterações em sua implementação a qualquer momento. As mudanças na implementação não mudam o código que usa a classe, desde que a interface permaneça inalterada. As alterações na interface necessitarão de mudanças no código que exerce essa interface.

## Implementação 
A implementação define como um componente realmente fornece um serviço. É a maneira de como é feito ou melhor dizendo como funciona. A implementação define os detalhes internos do componente.
Pense num carro. Você não precisa saber como exatamente o motor do seu carro funciona para ligá-lo e andar com ele por aí. Você apenas gira a chave ao contato e dá a partida. Você apenas exerce à sua interface e faz uso de seu serviço. O mesmo vale para outras partes do veículo como o volante, o câmbio, a embreagem.  

## TADS – Tipos Abstratos de Dados
O Tipo Abstrato de Dados (TAD) não é um conceito novo. Os TADs, junto com a própria OO, cresceu a partir da linguagem de programação Simula, introduzida em 1966. Na verdade, os TADs são decididamente não OO; em vez disso, eles são um subconjunto da OO. Entretanto, os TADs apresentam duas características interessantes: abstração e tipo. É essa ideia de tipo que é importante, pois sem ela, você não pode ter um verdadeiro encapsulamento.
O verdadeiro encapsulamento é imposto em nível de linguagem, através de construções internas da linguagem. Qualquer outra forma de encapsulamento é simplesmente um acordo de cavalheiros, que é facilmente malogrado. Os programadores o contornarão porque podem fazer isso!

### Definição Formal 
Um TAD é um conjunto de dados e um conjunto de operações sobre esses dados. Os TADs permite que você defina novos tipos na linguagem, ocultando dados internos e o estado, atrás de uma interface bem definida. Essa interface apresenta o TAD como uma única unidade atômica.  
Modificadores de Acesso
São controles de restrição a membros e métodos de uma classe. Quase todas as linguagens fornecem  mecanismos de controle de acesso que em geral em um modo mais básico são divididos em três níveis: 
    - Privado
    - Protegido
    - Público
O nível de acesso que você escolhe é muito importante para seu projeto. Todo comportamento que você queira tornar visível para o mundo, precisa ter acesso público. Tudo que você quiser ocultar do mundo exterior precisa ter acesso protegido ou privado. O Java ainda define mais um modificador chamado de Protegido pelo Pacote. 

## Porque você deve encapsular? 
Quando usado cuidadosamente, o encapsulamento transforma seus objetos em componentes plugáveis. Para que outro objeto use seu componente, ele só precisa saber como usar a interface pública do componente. Tal independência trás três vantagens importantes: 
Independência significa que você pode reutilizar o objeto em qualquer parte. Quando você encapsular corretamente seus objetos, eles não estarão vinculados a nenhum programa em particular. Em vez disso, você pode utilizá-los sempre que seu uso fizer sentido. Para usar o objeto em qualquer lugar, você simplesmente exerce sua interface.
O encapsulamento permite que você tome transparentes as alterações em seu objeto. Desde que você não altere sua interface, todas as alterações permanecerão transparentes para aqueles que estiverem usando o objeto. O encapsulamento permite que você atualize seu componente, forneça uma implementação mais eficiente ou corrija erros - tudo isso sem ter de tocar nos outros objetos de seu programa. Os usuários de seu objeto se beneficiarão automaticamente de todas as alterações que você fizer.
Usar um objeto encapsulado não causará efeitos colaterais inesperados entre o objeto e o restante do programa . Como o objeto tem implementação independente, ele não tera nenhuma outra interação com o restante do programa. além de sua interface.
Agora, você está em um ponto onde podemos falar sobre algumas generalidades a respeito do encapsulamento. Você viu que o encapsulamento permite escrever componentes de software com implementações independentes. As três características do encapsulamento eficaz são:
    - Abstração 
    - Ocultação da implementação 
    - Divisão de responsabilidade
Vamos ver mais profundamente cada característica, para aprender a melhor maneira de obter o encapsulamento.

## Abstração: aprendendo a pensar e programar de forma abstrata
Embora as linguagens OO estimulem o encapsulamento, elas não o garantem. E fácil construir código dependente e frágil. O encapsulamento eficaz vem apenas com um projeto cuidadoso. abstração e experiência. Um dos primeiros passos para o encapsulamento eficaz é aprender como abstrair software e os conceitos subjacentes eficientemente.

## O que é Abstração? 
Abstração é o processo de simplificar um problema difícil. Quando começa a resolver um problema, você não se preocupa com cada detalhe. Em vez disso, você o simplifica, tratando apenas dos detalhes pertinentes a uma solução.
Imagine que você tenha de escrever um simulador de fluxo de tráfego. E possível que você mo- dele classes para sinais de trânsito, veículos, condições da pista, auto estradas, ruas de mão dupla, ruas de mão única, condições climáticas etc. Cada um desses elementos afetaria o fluxo do tráfego. Entretanto, você não modelaria insetos e pássaros no sistema, mesmo que eles possam aparecer em uma via real. Além disso, você omitiria tipos específicos de carros. Você simplifica o mundo real e inclui apenas as partes que realmente afetam a simulação. Um carro é muito importante para a simulação, mas o fato de ser um Cadillac ou fazer com que o carro controle seu nível de combustível é supérfluo para a simulação de tráfego.
A abstração tem duas vantagens. Primeiro, ela permite que você resolva um problema facilmente. Mais importante, a abstração o ajuda a obter reutilização. Muitas vezes, os componentes de software são demasiadamente especializados. Essa especialização, combinada com uma inter dependência desnecessária entre os componentes, torna difícil reutilizar um código existente em outra parte. Quando possível, você deve se esforçar por criar objetos que possam resolver um domínio inteiro de problemas. A abstração permite que você resolva um problema uma vez e depois use essa solução por todo o domínio desse problema.
Embora seja desejável escrever código abstrato e evitar uma especialização demasiada, é duro escrever código abstrato, especial mente quando você começa a praticar a POO.
Existe um a linha tênue entre muita e pouca especialização. A linha pode ser discernida apenas com a experiência. Entretanto, você precisa saber desse poderoso conceito.

## Abstração eficaz
Neste ponto, você pode formular algumas regras para a abstração eficaz:
Trate do caso geral e não do caso específico. 
Ao confrontar vários problemas diferentes, procure o que for comum a todos. Tente ver um conceito e não um caso específico.
Não se esqueça de que você tem um problema a resolver. A abstração é valiosa, mas não descuide do problema na esperança de escrever código abstrato.
A abstração pode não estar prontamente aparente. A abstração pode não saltar à sua frente na primeira, segunda ou terceira vez que você resolver um problema que está sujeito a ser abstraído.
Prepare-se para a falha. É quase impossível escrever uma abstração que funcione em todas as situações. Você verá por que, posteriormente ainda hoje.
Não caia na paralisia da abstração. Resolva os problemas que você encontrar primeiro. Veja a abstração com o um bônus e não com o o objetivo final. Caso contrário, você vai se deparar com a possibilidade de prazos finais perdidos e abstração incorreta. Existem ocasiões para abstrair e ocasiões em que a abstração não é apropriada.
Uma boa regra geral é abstrair algo que você tiver implementado três vezes de maneira análoga. A medida que você ganhar experiência, aprenderá a escolher a abstração mais rapidamente.
Nem sempre você pode reconhecer oportunidades para uma abstração. Talvez você tenha de resolver um problema várias vezes, antes que uma abstração se torne aparente. Às vezes, diferentes situações ajudam a encontrar uma abstração eficaz e, mesmo então, a abstração pode precisar de alguma conversão. A abstração pode demorar a amadurecer.
A abstração pode tomar um componente encapsulado mais reutilizável, pois ele está personalizado para um domínio de problemas e não para um uso específico. Entretanto, há ma is coisas importantes quanto ao encapsulamento do que a simples reutilização de componentes. O encapsulamento também é importante por ocultar os detalhes internos. O tipo abstrato de dados é um bom lugar para ver em seguida, na busca do encapsulamento eficaz.
Guardando seus segredos através da ocultação da implementação
A abstração é apenas uma característica do encapsulamento eficaz. Você pode escrever código abstrato que não é encapsulado. Em vez disso, você também precisa ocultar as implementações internas de seus objetos.
A ocultação da implementação tem duas vantagens:
    - Ela protege seu objeto de seus usuários.
    - Ela protege os usuários de seu objeto do próprio objeto.

## Acoplamento 
Acoplamento é o termo que descreve a dependência demasiada de uma classe à implementação da outra. Em geral isso representa uma falha no encapsulamento e não é bom para um projeto. Todas as entidades devem ser independentes uma das outras. 
A ocultação da implementação leva a um projeto mais flexível , pois ela impede que os usuários de seus objetos se tomem fortemente acoplados à implementação subjacente dos objetos. Então, não apenas a ocultação da implementação protege seus objetos, como também protege aqueles que usam seus objetos, estimulando um código fracamente acoplado.
Quando um recurso aparece na interface pública de um objeto, todo mundo que usa o recurso se toma dependente do fato de ele existir. Se o recurso desaparecer repentinamente, você precisará alterar o código que tiver se desenvolvido de forma dependente a esse comportamento ou atributo.
Código dependente é dependente da existência de determinado tipo. O código dependente é inevitável. Entretanto, existem graus para a dependência aceitável e para a super dependência. 
Existem graus para a dependência. Você não pode eliminar a dependência totalmente. Entretanto, você deve se esforçar para minimizar a dependência entre objetos. Normalmente, você limita tal dependência programando uma interface bem definida. Os usuários só podem se tomar dependentes quanto ao que você decide colocar na interface. Entretanto, se alguma implementação do objeto se tornar parte da interface, os usuários do objeto poderão se tornar dependentes dessa implementação. Tal código fortemente acoplado elimina sua liberdade de alterar a implementação de seu objeto. Uma pequena alteração na implementação de seu objeto poderia necessitar de uma cascata de alterações por todos os usuários do objeto.
O encapsulamento e a ocultação da implementação não são mágica. Se você precisar alterar uma interface, precisará atualizar o código que é dependente da interface antiga. Ocultando os detalhes e escrevendo software para uma interface, você cria software que é fracamente acoplado.
O código fortemente acoplado anula o objetivo do encapsulamento: criar objetos independentes e reutilizáveis.

## Divisão de Responsabilidade 
A ocultação da implementação evolui naturalmente para uma discussão sobre a divisão da responsabilidade. Na seção anterior, você viu como poderia desacoplar código ocultando detalhes da implementação. A ocultação da implementação é apenas um passo na direção da escrita de código fracamente acoplado.
Para ter realmente código fracamente acoplado, você também deve ter uma divisão da responsabilidade correta. Divisão da responsabilidade correta significa que cada objeto deve executar uma função – sua responsabilidade - e executá-la bem. A divisão da responsabilidade correta também significa que o objeto é coesivo. Em outras palavras, não faz sentido encapsular muitas funções aleatórias e variáveis. Elas precisam ter um forte vinculo conceitual entre si. Todas as funções devem trabalhar no senti do de uma responsabilidade comum.
A ocultação da implementação e a responsabilidade andam lado a lado. Sem ocultação da implementação, a responsabilidade pode faltar em um objeto. É de responsabilidade do objeto saber como fazer seu trabalho. Se você deixar a implementação aberta para o mundo exterior. um usuário poderá começar a atuar diretamente na implementação - duplicando assim a responsabilidade.
Assim que dois objetos começam a fazer a mesma tarefa, você sabe que não tem uma divisão da responsabilidade correta. Quando você observar a existência de lógica redundante, precisará refazer seu código. Mas não se sinta mal; refazer o trabalho é um a parte esperada do ciclo de desenvolvimento OO. A medida que seus projetos amadurecerem, você encontrará muitas oportunidades para melhorá-los.

## O Gerente e o Programador
Vamos considerar um exemplo real de divisão da responsabilidades: o relacionamento entre gerente e programador.
Imagine que seu gerente venha até você, forneça as especificações de sua parle em um projeto e, em seguida, o deixe trabalhar. Ele sabe que você tem um trabalho a fazer e que sabe como fazer o melhor trabalho possível.
Agora, imagine que seu chefe não é tão esperto. Ele explica o projeto e pelo que você será responsável. Ele lhe garante que está lá para facilitar seu trabalho. Mas, quando você começa, ele puxa uma cadeira! Pelo resto do dia, seu chefe fica em cima de você e fornece instruções passo a passo, enquanto você codifica.
Embora o exemplo seja um tanto extremo, os programadores programam dessa maneira em seu código, o tempo todo. O encapsulamento é como o gerente eficiente. Como no mundo real, conhecimento e responsabilidade precisam ser delegados para aqueles que sabem como fazer o trabalho da melhor torna possível. Muitos programadores estruturam seu código como um chefe autoritário trata seus funcionários.
Código sem divisão de responsabilidade se aplica a essa metáfora como uma luva. Quando não há divisão de responsabilidade em seu código os clientes que fazem uso dele têm que trabalhar mais por algo que você deveria ter fornecido. Fica para eles o trabalho de extrair os serviços de alguma maneira. Isso não lhe dá o controle de como o serviço deve ser utilizado e impede que você restrinja certas condições de uso.

## Resumo 
Usando encapsulamento, você pode tirar proveito das vantagens da abstração, da ocultação da implementação e da responsabilidade em seu código diário. 
Com a abstração, você pode escrever objetos que são úteis em várias situações. Se você ocultar corretamente a implementação de seu objeto, estará livre para fazer quaisquer melhorias que queria em seu código – a qualquer momento. Finalmente, se você dividir corretamente a responsabilidade entre seus objetos, evitará lógica duplicada e código procedural. 
