---


---

<h1 id="tp-4">TP 4</h1>
<h2 id="exercice-1">Exercice 1</h2>
<ol>
<li><code>alias maj="sudo apt-get install &amp;&amp; sudo apt-get upgrade -y"</code>.  On ajoute cette commande dans le fichier <strong>sudo nano .bashrc</strong> et on fait <code>source ~/.bashrc</code> pour que ce sois persistant</li>
<li>Car c’est simplement une commande bash</li>
<li>Compter le nombre de paquets dispo sur les dépôts Ubuntu <code>apt-cache pkgnames | wc -l</code> ou <code>apt-list | wc -l</code>. Il y en a 73965.</li>
<li><code>dpkg --list | wc -l</code> ou <code>apt list --installed | wc -l</code>. Il y en a 614 avec dpkg et 610 avec apt car apt rajoute une ligne pour dire qu’il est en train de lister les paquets. On ne peut pas utiliser dpkg.log car ce fichier supprime les journaux lorsqu’ils sont trop vieux ou trop anciens</li>
<li>Les 5 derniers paquets installés d’après <strong>/var/log/dpkg.log</strong> : <em>rsyslog:amd64 8.2112.0-2ubuntu2.2<br>
man-db:amd64 2.10.2-1<br>
plymouth-theme-ubuntu-<br>
status installed dbus:amd64 1.12.20-<br>
installed initramfs-tools:all 0.140ubuntu13.4</em></li>
<li>Afficher les derniers paquets installés avec <strong>apt</strong> avec <code>cat /var/log/apt/history.log</code> :<br>
<em>fwupd:amd64 (1.7.5-3, 1.7.9-1~22.04.3), ubuntu-minimal:amd64 (1.481, 1.481.1), update-notifier-common:amd64 (3.192.54, 3.192.54.6), python3-debian:amd64 (0.1.43ubuntu1, 0.1.43ubuntu1.1), nftables:amd64 (1.0.2-1ubuntu2, 1.0.2-1ubuntu3)</em></li>
<li></li>
</ol>
<p><strong>Glances :</strong> afficher l’état des principales ressources d’un système, de sa charge et du fonctionnement des applications.<br>
<strong>tldr :</strong> permet de montrer chacun des commandes d’un manuel résumées par des exemples<br>
<strong>hollywood</strong> : Cet utilitaire divise votre console en plusieurs volets de véritable bavardage techno, parfaitement adapté à tout mélodrame geek hollywoodien.</p>
<h2 id="exercice-2">Exercice 2</h2>
<p>Avec <code>which -a ls</code> qui donne <em>/usr/bin/ls /bin/ls</em> puis <code>dpkg -S /bin/ls</code>, on retrouve le paquet d’origine de ls qui est<strong>coreutils</strong></p>
<p>On prend en argument le résultat de la première cmd avec <strong>xargs</strong> et on utilise <strong>2&gt;/dev/null</strong> pour ne pas afficher l’avertissement, en une seule commande :</p>
<pre><code>which -a ls | xargs dpkg -S 2&gt; /dev/null 
</code></pre>
<h2 id="exercice-3">Exercice 3</h2>
<pre><code> #!/bin/bash
 paquet=$1
 if dpkg -l | grep -q "$1"; then
         echo "INSTALLE"
 else
         echo "NON INSTALLE"
 fi
</code></pre>
<h2 id="exercice-4">Exercice 4</h2>
<pre><code> dpkg -L coreutils | grep "/bin/"
</code></pre>
<h2 id="exercice-5">Exercice 5</h2>
<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>

