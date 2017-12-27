<h2>Coerção de tipos é um bad boy</h2>

<p>Enquanto tipos estáticos ajudam a evitar erros e comportamentos inesperados, coerção de tipos ajuda a perder o controle sobre seus dados e tipos. Coerção de tipos significa que quando o operando e o operador tem tipos diferentes, então eles são convertidos a um equivalente e aceitável valor pelo operador.</p>

<p>Por exemplo, quando você faz:</p>
<pre><code class="lang-js"><span class="hljs-number">1</span> == <span class="hljs-literal">true</span>
</code></pre>

<p>Isso é <code>true</code> apenas porque não havendo comparação para diferentes tipos, <code>true</code> do lado direito é convertido para um número (baseado no <code>1</code> do lado esquerdo), nesse caso, <code>true</code> vira <code>1</code>. O operador <code>===</code> evita que esta conversão aconteça, e isso é o que será usado à partir deste ponto. </p>

<p>O sistema de tipos de uma linguagem de programação define quais tipos de dados podem existir na linguagem e como as operações podem ser aplicadas a ela, e esse tipo de coisa existe para eviar que o programador atire no próprio pé. Coerção de tipos é sobre <b>implicitamente</b> converter valores incompatíveis quando não há nenhum operador válido para aquele tipo de valor.</p>

<p>Em linguagens como Python, mesmo com tipagem dinâmica, operações como <code>"foo" + 1</code> transmitirão um runtime error:</p>

<pre><code class="lang-python"><span class="hljs-meta">&gt;&gt;&gt; </span><span class="hljs-string">"foo"</span> + <span class="hljs-number">1</span>
Traceback (most recent call last):
  File <span class="hljs-string">"&lt;stdin&gt;"</span>, line <span class="hljs-number">1</span>, <span class="hljs-keyword">in</span> &lt;module&gt;
TypeError: cannot concatenate <span class="hljs-string">'str'</span> <span class="hljs-keyword">and</span> <span class="hljs-string">'int'</span> objects
</code></pre>

<p>E isso ajuda a evitar muitos bugs que seriam apanhados apenas em um ponto distante do programa. Coerção de tipos é um nome incorreto, enquanto valores não tenham tipos no senso de linguagens tipadas estáticamente, mas isso é uma definição de como diferentes valores interagem. A especificação do ECMAScript sobre coerção de tipos é realmente grande. Há muitas regras e exceções e confiar nessas conversões é um erro fatal.</p>
