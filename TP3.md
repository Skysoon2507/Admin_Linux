---


---

<h1 id="tp-3">TP 3</h1>
<h2 id="exercice-1">Exercice 1</h2>
<ol start="4">
<li>Afficher les membres de infra :</li>
</ol>
<blockquote>
<p><code>cat /etc/group ou alors getent group groupe</code></p>
</blockquote>
<ol start="5">
<li>Appliquez le Sticky bite sur un dossier :</li>
</ol>
<blockquote>
<p><code>sudo chmod +t infra/ &amp;&amp; sudo chmod +t dev/</code></p>
</blockquote>
<ol start="6">
<li>On ne peut pas car on a pas défini de mot de passe pour le compte d’alice</li>
<li>Activer un compte utilisateur :</li>
</ol>
<blockquote>
<p><code>sudo passwd alice</code></p>
</blockquote>
<ol start="8">
<li>Afficher les ID d’un utilisateur :</li>
</ol>
<blockquote>
<p><code>id alice</code></p>
</blockquote>
<ol start="12">
<li>Retrouver utilisateur par son UID :</li>
</ol>
<blockquote>
<p><code>getent passwd 1000...</code></p>
</blockquote>
<ol start="13">
<li>Afficher le GID d’un groupe :</li>
</ol>
<blockquote>
<p><code>getent group test</code></p>
</blockquote>
<ol start="14">
<li>Retrouver un groupe avec le GID :</li>
</ol>
<blockquote>
<p><code>getent group 1000...</code></p>
</blockquote>
<ol start="15">
<li>L’utilisateur charlie ne se supprime pas du groupe car le groupe infra est son groupe primaire, impossible pour un utilisateur d’appartenir à aucun groupe.</li>
<li>Changer expiration mdp / Changer mdp sous 90j / Attendre 5j pour modifier son mdp / User averti 14j avant expiration mdp / Desactivation User après 30j  :</li>
</ol>
<blockquote>
<pre><code>sudo chage -E 2024-06-01 dave
sudo chage -M 90 dave
sudo chage -m 5 dave
sudo chage -W 14 dave
sudo chage -E 30 dave
</code></pre>
</blockquote>
<ol start="17">
<li>Shell de root : /bin/bash</li>
<li>L’utilisateur <strong>nobody</strong> est celui qui a le moins de permissions possible et était utilisé pour exécuter des serveurs en arrière-plan. Une protection contre les escalades de privilèges</li>
<li>Il le conserve pendant 15min.</li>
<li>Effacer le cache de conservation du mdp sudo :</li>
</ol>
<blockquote>
<p><code>sudo -k</code></p>
</blockquote>
<h2 id="exercice-2">Exercice 2</h2>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

