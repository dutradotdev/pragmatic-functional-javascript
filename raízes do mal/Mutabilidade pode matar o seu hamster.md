<h2>Mutabilidade pode matar o seu hamster</h2>

<p>Um dos pilares da programação funcional é a imutabilidade e alterar as coisas é algo muito comum nas linguagens com paradigma imperativo e orientado a objetos, mas como se podem modelar computações e problemas sem sequer ter permissão de ter variáveis?</p>

<p>Mutabilidade é sobre mostrar ao computador <b>como</b> resolver seu problema e não apresentar ou declarar <b>qual</b> é o problema que ele tem que resolver.</p>

<p>Antes de apresentar como nós faremos isso, vamos primeiro examinar o porquê da mutabilidade ser do mal e você deve evitar ela quando possível e sensível se você preza pela vida e saúde do seu hamster. Isso definitivamente não é um discurso sobre mutabilidade em geral, mas uma visão geral dos problemas que são inegavelmente comuns em projetos do mundo real. Há situações onde mutabilidade é necessária, mas elas são as exceções e não a regra.</p>

<h2>Dados mutáveis são inerentemente complexos</h2>

<p>E mutabilidade sem controle explícito é o que faz o desenvolvimento de software difícil. O controle do fluxo do seu programa cria mais possibilidades e mais coisas para se preocupar. Ao manter bases de código com muitas variáveis globais ou mutáveis e referências, não há garantias que ao mudar uma função não iremos presenciar efeitos colaterais em outra parte do programa que pode ser completamente não relacionado a alteração. Funções com uma única entrada e saída te dão uma garantia de que elas não afetarão outras partes do programa e são previsíveis. Se preocupar com a segurança do programa é trabalho do compilador e não seu. O programador deve se preocupar somente com a modelagem do problemas e os únicos erros que ele deve se preocupar devem ser os problemas de lógica de negócio, mas a maioria das linguagens convencionais transferem o trabalho delas para o programador depressivo.</p>

<h2>Multithreading é difícil</h2>

<p>Se você acredita que linguagens imperativas e coisas que são mais próximas do Assembly são para sistemas distribuídos, você está errado, muito errado. Código imutável e previsível é inerentemente mais fácil de otimizar para rodar em múltiplos cores e threads porque o compilador sabe que ele pode rodar com segurança diferentes partes do programa independentemente 
sabendo que não há interdependência entre eles. Uma função que tem algumas entradas e sempre tem a mesma saída e não afeta partes do programa ou não deve emitir efeitos secundários é sempre thread-safe e otimizável. </p>

<p>Outro problema com mutabilidade de estado é quando você lida com desenvolvimento server-side com um servidor sem estado. Rodando sua aplicação em clusters (múltiplos cores ou máquinas) com um servidor com estado se torna a principal fonte de dor de cabeça porque a mutabilidade de estados do servidor não é compartilhado através de todas as possíveis instâncias da aplicação. A falta de um estado global mutável é o que permite Haskell ser tão otimizável. Erlang e Elixir armazenam e compartilham este estado usando cálculo de processos (como π-calculus). </p>

<h2>Perda de reversabilidade</h2>

<p>Reversabilidade importa muito. Desde 2015, novas ferramentas para desenvolvimento front-end tem emergido e uma boa parte delas é sobre o estado de controle e reversabilidade, como React e Vue. Reversabilidade é sobre ter controle do seu programa e ser capaz para replicar o ponto do seu programa baseado puramente no estado atual. Isso também torna debugar e encontrar erros muito mais fácil porque não reproduzir erros já não pode ser uma desculpa. Quando você tem reversabilidade e controle de estado, coisas complexas se tornam triviais, como restaurar o estado do programa ao reiniciá-lo ou implementar operações de "desfazer" e "refazer".</p>

<h2>Debugar pode ser cansativo</h2>
<p>E eu não estou brincando. Debugar se torna ainda mais difícil quando você está lidando com múltiplos processos e programação assíncrona. Você já se perguntou como no mundo essa variável teve seu valor alterado? Quando você combina mutabilidade com nulidade, você cria um monstro perigoso. </p>

<h2>Referências podem ser um problema</h2>

<p>E o problema aumenta quando você adiciona referências mutáveis; Elas são, em primeiro lugar, difíceis para otimização do compilador e criam uma bola de neve em qualquer ponto da aplicação que receba uma referência é capaz de mutar o valor esperado pela variável. Referências são muito úteis em algumas situações, mas a não ser que você realmente precise usá-las e saiba o que está fazendo, evite-as. JavaScript tem um problema especial onde alguns métodos trabalham com referências ao invés de valores, e você pode fácilmente perder o controle da situação: </p>

<pre><code class="lang-javascript"><span class="hljs-keyword">const</span> list = [<span class="hljs-number">8</span>, <span class="hljs-number">3</span>, <span class="hljs-number">1</span>, <span class="hljs-number">2</span>, <span class="hljs-number">7</span>, <span class="hljs-number">4</span>]
<span class="hljs-comment">// The sorted list</span>
<span class="hljs-built_in">console</span>.log(list.sort()) <span class="hljs-comment">// [1, 2, 3, 4, 7, 8]</span>

<span class="hljs-comment">// Then original list... oh wait!</span>
<span class="hljs-built_in">console</span>.log(list) <span class="hljs-comment">// [1, 2, 3, 4, 7, 8]</span>
</code></pre>

<p>Então, se em algum ponto da aplicação uma função que foi chamada para trabalhar com a lista decide classificar os valores, isto vai bagunçar com todos os seus dados originais e aumentar a possibilidade de um erro ou computação não esperada. Algumas funções que operam com arrays para manter distância:</p>

<ul>
<li><code>copyWithin</code></li>
<li><code>fill</code></li>
<li><code>pop</code></li>
<li><code>push</code></li>
<li><code>reverse</code></li>
<li><code>shift</code></li>
<li><code>sort</code></li>
<li><code>splice</code></li>
<li><code>unshift</code></li>
</ul>

<p>Elas estão documentadas no Mozilla Developer Network na seção "<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype#Mutator_methods" target="_blank">Mutator methods</a>" do objeto <code>Array</code>.</p>

