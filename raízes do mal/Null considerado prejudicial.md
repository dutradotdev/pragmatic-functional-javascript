<h2>Null considerado prejudicial</h2>

<p>E por <code>null</code>, nós também queremos dizer <code>undefined</code>. É difícil ver um programador que nunca teve alguns problemas com referências nulas, null pointers ou qualquer coisa que possa representar ausência de valor. Para programadores JavaScript, <code>undefined is not a function</code>, para os jovens de terno do C#, <code>NullReferenceException</code>, e para falta de sorte de quem precisa usar Java, o clássico <code>java.lang.NullPointerException</code>. Você pensa que nós realmente precisamos de <code>null</code> como uma construção especial da linguagem? Neste ponto, há também um consenso entre programadores de linguagens funcionais e programadores de linguagens orientada a objetos: <code>null</code> foi um erro secular.
</p>

<h4>Aumenta a complexidade</h4>

<p>Quando você tem que comparar com nulo para evitar erros de compilação, a lógica do seu código 
bifurca e cria um novo conjunto de possibilidades. Se você usar muitos valores <code>null</code>, a chance de você ter um código spaghetti que se torna difícil de manter é realmente grande. Linguagens orientadas a objetos recomendam o padrão <code>null object</code>, enquanto linguagens funcionais usam monads para isso. Felizmente, existem inúmeras bibliotecas e implementações monadic para JavaScript para abstrair e evitar este problema. Nós veremos monads em detalhes e como lidar devidamente com <code>null</code> depois - por hora, nós iremos apresentar os problemas e a busca pela solução será uma tarefa para os próximos capítulos.
</p>

<h4>Tipos imprevisíveis</h4>

<p>Por que você retornaria <code>null</code> em uma função que recupera a lista de usuários do banco de dados quando você pode apenas retornar uma <b>representação vazia</b> do tipo esperado? - Um array vazio nesta situação. O fato é que este <code>null</code> pode ser de <b>qualquer</b> tipo, e isso faz a tarefa de debugar ser um pouco mais difícil. Qual é mais pragmática?</p>

<pre><span class="pl-k">const</span> <span class="pl-c1">showUsers</span> <span class="pl-k">=</span> () <span class="pl-k">=&gt;</span> {
    <span class="pl-k">const</span> <span class="pl-c1">users</span> <span class="pl-k">=</span> <span class="pl-en">getUsers</span>()
    <span class="pl-k">if</span> (users <span class="pl-k">!==</span> <span class="pl-c1">null</span>) {
        <span class="pl-smi">users</span>.<span class="pl-c1">forEach</span>(<span class="pl-en">console</span>.<span class="pl-smi">log</span>)
    }
}</pre>

<pre><span class="pl-k">const</span> <span class="pl-c1">showUsers</span> <span class="pl-k">=</span> () <span class="pl-k">=&gt;</span> <span class="pl-en">getUsers</span>().<span class="pl-c1">forEach</span>(<span class="pl-en">console</span>.<span class="pl-smi">log</span>)</pre>

<p>Não torne complexo quando você pode tornar simples.</p>

<h4>True, false... e null!?</h4>

<p>A não ser que você tenha uma <b>boa</b> desculpa, não retorne <code>null</code> quando tudo que você precisa é dar umas simples resposta booleana. Primeira coisa: <code>null</code> não é <code>falso</code>, <code>null</code> é a falta de valor, e neste caso nós não temos representação booleana, mas um modelo de três estados. Booleanos nunca devem ser anuláveis.</p>



