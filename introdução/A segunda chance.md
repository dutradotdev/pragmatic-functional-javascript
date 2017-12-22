<h2> A segunda chance </h2>

<blockquote> E deus disse, "deixe que haja funções", e houveram funções. </blockquote>

<p>No começo, computadores eram muito lentos, mais lento que executar o Android Studio na sua máquina com 2GB de RAM! Quando o primeiro computador físico apareceu e as linguagens de programação começaram a ser projetadas e implementadas, haviam principalmente 2 mindsets:</p>
<ol>
    <li>Começar da arquitetura Von Neumann e <b>adicionar abstração</b>;</li>
    <li>Começar da matemática e <b>remover abstração</b>.</li>
</ol>

<p>Quando tudo começou, lidar com altos níveis de abstração era muito difícil e custoso, memória e armazenamento tinham realmente pouco poder, então linguagens de programação com o paradigma imperativo tiveram maiior visibilidade que o paradigma funcional porque linguagens imperativas tinham um menor nível de abstração então era uma forma mais fácil de implementar e maperar direto no hardware. Pode não ser a melhor maneira de projetas programas e expressar ideias, mas, pelo menos, era fácil de rodar.</p>

<p>Mas computadores melhoraram muito e o paradigma funcional finalmente teve sua merecida chance. Programação funcional não é um conceito novo. Sério. É velho e vem diretamente dos matemáticos. Os conceitos principais e o modelo funcional computacional veio antes de computadores físicos existirem. Teve origem no cálculo lamba e foi iniciamente apenas um sistema forma desenvolvido em 1930 para investigar computabilidade.</p>

<p>Um monte de linguagens de programação modernas suportam bem programação funcional. Até Java se rendeu a isto e implementou expressões lambda e streams. A maioria de vocês programam em linguagens que foram criadas; Eu quero te mostrar o que foi descoberto.</p>

<h2>Por que programação funcional?</h2>
<p>Se programação imperativa e outros paradigmas, como orientação a objetos, fossem boas o suficiente, por que teríamos que aprender uma nova forma de codificar? A resposta é: sobrevivência. Orientação a objetos não pode nos salvar do mostro da nuvem mais. Problemas mais complexos surgiram e a programação funcional soluciona eles muito bem. Programação funcional não é "apenas outra sintaxe" como algumas pessoas pensam. É outra mentalidade e um modo declarativo de resolver problemas. Enquanto na programação imperativa você especifica passos e como as coisas devem acontecer, na declarativa (funcional e lógica) programação você especifica o que deve ser feito e o computador decide a melhor forma de fazê-lo. Nós evoluímos muito para fazer o trabalho que um computador consiga fazer milhares de vezes melhor do que nós.</p>

<h4>Testabilidade e manutenção</h4>
<p>Bases de códigos modulares e funcionais são a forma mais fácil de testar e ter uma alta cobertura nos testes unitários. As coisas são muito bem isoladas e independentes, e por seguirem todos os principais princípios você obtém programas que trabalham bem em conjunto e tem menos bugs.</p>

<h4>Paralelismo</h4>
<p>Isso é realmente variável com a implementação, mas em linguagensque podem rastrear todos os tipo s de efeitos, você consegue paralelismo e a possibilidade de clusterizar seu programa de graça.</p>

<h4>Otimização</h4>
<p>Linguagens funcionais tendem a ser mais fáceis de otimizar e mais previsíveis para compiladores. Conhecendo todo tipo de coisas que podem acontecer em um programa dá a possibilidade ao compilador conhecer a semântica do seu código antes mesmo de executá-lo.
Haskell pode ser mais rápido que C se você um código idiomático. O principal engine JavaScript, V8, investiu extensivamente em otimizar o paradigma funcional.</p>



