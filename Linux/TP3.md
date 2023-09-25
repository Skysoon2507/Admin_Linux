
# TP 3
## Exercice 1
 4. Afficher les membres de infra : 
> `cat /etc/group ou alors getent group groupe`
 5. Appliquez le Sticky bite sur un dossier : 
> `sudo chmod +t infra/ && sudo chmod +t dev/`
 6. On ne peut pas car on a pas défini de mot de passe pour le compte d'alice
 7. Activer un compte utilisateur : 
> `sudo passwd alice`
 8. Afficher les ID d'un utilisateur : 
> `id alice`
 12. Retrouver utilisateur par son UID : 
> `getent passwd 1000...`
 13. Afficher le GID d'un groupe : 
> `getent group test`
 14. Retrouver un groupe avec le GID : 
> `getent group 1000...`
 15. L'utilisateur charlie ne se supprime pas du groupe car le groupe infra est son groupe primaire, impossible pour un utilisateur d'appartenir à aucun groupe.
 16.  Changer expiration mdp / Changer mdp sous 90j / Attendre 5j pour modifier son mdp / User averti 14j avant expiration mdp / Desactivation User après 30j  : 
>     sudo chage -E 2024-06-01 dave
>     sudo chage -M 90 dave
>     sudo chage -m 5 dave
>     sudo chage -W 14 dave
>     sudo chage -E 30 dave
 17. Shell de root : /bin/bash
 18. L'utilisateur **nobody** est celui qui a le moins de permissions possible et était utilisé pour exécuter des serveurs en arrière-plan. Une protection contre les escalades de privilèges
 19. Il le conserve pendant 15min. 
 20. Effacer le cache de conservation du mdp sudo : 
> `sudo -k`
 
 
## Exercice 2



    

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMwNDU5MzM1M119
-->