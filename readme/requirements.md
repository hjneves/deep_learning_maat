---


---

<h1 id="requisitos">Requisitos</h1>
<p>Não é necessário ter conhecimentos de programação para participar neste workshop, mas vai ser necessário instalar algmas peças de software.</p>
<ul>
<li>FloydHub Account</li>
<li>Git</li>
<li>Python 2 (e PIP)</li>
<li>VirtualEnv</li>
</ul>
<p>Para executar os comandos indicados nestas instruções devera usar um terminal</p>
<ul>
<li>Em macOS usar o ‘terminal’</li>
<li>Em Windows usar o ‘cmd’</li>
</ul>
<h2 id="floydhub-account">FloydHub account</h2>
<p>Para a execução dos modelos de deep learning vamos usar a plataforma <a href="https://www.floydhub.com">Floydhub</a>. A plataforma <em>FloydHub</em> disponibiliza um acesso a hardware e software pré-configurado para a execução de modelos de deep learning.<br>
Deverão criar uma conta <a href="https://www.floydhub.com/signup">aqui</a></p>
<h2 id="git">Git</h2>
<p>Git é uma ferramenta de gestão de versões de projectos que vai ser utilizada para garantir a sincronização dos ficheiros de imagens que vamos usar e produzir.</p>
<p>Verifique se já tem o <em>git</em> instalado através do seguinte comando <code>git --version</code>:</p>
<p><img src="https://github.com/hjneves/deep_learning_maat/blob/master/readme/Screen%20Shot%202019-12-04%20at%2010.50.32.png" alt=""></p>
<p>Se ainda não tem o <em>git</em> intalado pode efectar a sua instalação:</p>
<ul>
<li>Em <a href="https://git-scm.com/download/win">Windows</a></li>
<li>Em <a href="https://git-scm.com/download/mac">macOS</a></li>
</ul>
<h2 id="python-2-e-pip">Python 2 e PIP</h2>
<p>O python é a ferramenta que dá suporte ao treino e aplicação dos modelos de redes neuronais que vão ser a base da criação artistica sobre as fotografias utilizadas.</p>
<p>Verifique que já tem o <em>python</em> intalado através do seguinte comando <code>python -V</code><br>
O PIP é uma ferramenta de gestão de pacotes do python. Se o python já estiver instalado o PIP também já deverá estar. Pode verificar a versão corrente do pip através do comando <code>pip -V</code></p>
<p><img src="https://github.com/hjneves/deep_learning_maat/blob/master/readme/Screen%20Shot%202019-12-05%20at%2018.07.17.png" alt=""></p>
<p>Caso não tenha <em>python</em> instalado, pode efectuar a sua instalação <a href="https://www.python.org/downloads/release/python-2717/">aqui</a></p>
<h2 id="virtualenv">VirtualEnv</h2>
<p>O virtualenv é um ambiente sandbox que permite a utilização de um conjunto de pacotes python sem interferir com a configuração actual do sistema. Os passos seguintes permitem criar o ambiente que vamos utilizar no workshop:</p>
<ul>
<li>Instalação do virtualenv: <code>sudo pip install virtualenv</code></li>
<li>Criar directoria de trabalho: <code>virtualenv ./floyd</code></li>
<li>Activação do ambiente: <code>source ./floyd/bin/activate</code></li>
<li>No final deveráo ter prefixado na linha de comando do terminal a palavra <code>(floyd)</code>.</li>
</ul>
<p><img src="https://github.com/hjneves/deep_learning_maat/blob/master/readme/Screen%20Shot%202019-12-05%20at%2018.59.04.png" alt=""></p>
<ul>
<li>Instalar o floyd-cli: <code>pip install -U floyd-cli</code></li>
</ul>
<h2 id="floydhub-commands">FloydHub commands</h2>
<p>floyd run --env tensorflow-0.12:py2 \<br>
–data narenst/datasets/neural-style-transfer-pre-trained-models/1:models “python <a href="http://evaluate.py">evaluate.py</a> \<br>
–allow-different-dimensions  \<br>
–checkpoint /models/wave.ckpt \<br>
–in-path ./images/ \<br>
–out-path ./output/”</p>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

