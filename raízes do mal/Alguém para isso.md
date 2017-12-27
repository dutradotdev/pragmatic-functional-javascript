<h2>Alguém para isso!</h2>

<p>Existem inúmeros artigos sobre o comando <code>this</code> no JavaScript, e <b>this</b> foi um dos piores problemas de modelagem da linguagem. Algumas pessoas argumentam que existem nomes que expressam melhor o conceito de <code>this</code>, como <code>batatas</code>. Até programadores JavaScript com anos de experiência ficam confusos sobre isso e isso é uma fonte comum de problemas entre eles. Há diferentes maneiras de setar o valor de <code>this</code> dentro de uma função, como chamar um método de um objeto, chamando uma função anônima, usando <code>call</code>, <code>apply</code> ou até usando <code>new</code> para criar uma nova instância. É realmente uma "handyman keyword". Falar do comportamento de um pedaço do programa apenas olhando ele quando contém <code>this</code> não é tão fácil quanto é com funções puras porque você precisa se preocupar com o <b>contexto</b> de chamada da função. Ele também possui diferentes comportamentos ao usar a palavra-chave <code>function</code> e <code>() =></code>, a seta gorda</p>, que captura o contexto do topo ao invés de criar outra, fazendo o uso das duas formas de declarações de funções anônimas nãointercambiáveis.

<h2>Comportamentos do this</h2>

<h4>Método de chamada</h4>

<pre><code class="lang-js"><span class="hljs-keyword">const</span> person = {
    fullName: <span class="hljs-string">'Mr. Pickles'</span>,
    sayName: <span class="hljs-function"><span class="hljs-keyword">function</span> (<span class="hljs-params"></span>) </span>{
        <span class="hljs-built_in">console</span>.log(<span class="hljs-string">`Hello, my name is <span class="hljs-subst">${this.fullName}</span>!`</span>)
    }
}

person.sayName() <span class="hljs-comment">// Hello, my name is Mr. Pickles!</span>
</code></pre>

<p>Note que usando <code>() =></code> ao invés de <code>function</code> irá capturar o topo <code>this</code>, fazendo <code>this.fullName</code> ser <code>undefined</code> nesta situação.</p>

