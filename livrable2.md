# SAé3 Cyber 04
*JOUET Malo & PENCRANE Alexis*


## 1. Présentation

### a. Objet du Pentest

> Un Pentest ou test d'intrusion a pour but d'anticiper les risques d'attaque par intrusion d'une infrastructure, ainsi nous devons identifier les différents leviers d'action d'un attaquant, établir les vulnérabilités de l'infrastructure et leurs potentielles nuisances puis produire un plan d'action pour réduire les risques.

### b. Condition d'execution du Pentest 
<!-- Décrire avec quoi et sur quoi le Pentest s’applique -->
> Nous avons réalisé un pentest de type blackbox, ce genre de pentest est une stratégie simulant une attaque réelle et engage des actions d’intrusion sur le SI via ses accès extérieurs, tout en ne disposant d’aucunes informations sur la cible. La seule information disponible est que le serveur se situer sur le même réseau que notre machine.
## 2. Résultats du Pentest 

### a. Synthèse non technique
<!-- Conclusions du Pentest sur les aspects utilisateurs, qualité de la politique de sécurité et/ou qualité de mise en œuvre -->

> Le SI est très vulnérable, un attaquant peu facilement bloquer l'accès à certains services pour le personnel comme pour le public tel que le site web ou vos accès à distance au SI. Il peut également usurper facilement une identité en se connectant avec les comptes administrateurs sur des services non-protéger. Concernant la politique de sécurité, il faudrait augmenter la complexité des mots de passe pour les accès administrateur, par exemple pour le site web.

### b. Synthèse technique
<!--  Conclusions du Pentest sur la sécurisation des services/protocoles et/ou la qualité sécuritaire de leurs configurations-->
> Les services présents sur le serveur sont tous sur de vieilles versions qui regorgent de failles plus ou moins dangereuses, certains mots de passe sont trop peu complexe (i.e. WordPress). Il faudrait donc mettre en place une meilleure politique de mise à jour ainsi qu'une politique de mot de passe plus complexe et plus particulièrement pour les comptes administrateurs.

### c. Synthèse des Vulnérabilités prioritaires ou les plus critiques
<!-- Mise en avant des vulnérabilités jugées particulièrement critiques et leurs
potentiels de nuisances. Chacune précise un niveau de criticité et une estimation
du niveau de complexité à résoudre/corrige -->
> Une des vulnérabilités la plus critique est la backdoor sur le service ftp, celle-ci est extrêmement simple à mettre en œuvre et donne un accès root aux serveurs ce qui permet a l'attaquant de faire ce qu'il veut sur la machine. Le niveau de criticité est lui extrême quant au niveau de complexité de la correction, elle est très simple.
>
> Une deuxième nuisance importante est le peu de complexité du mot de passe du serveur web, cela peut entraîner une désinformation des utilisateurs voir des redirection sur des sites malveillant.

### d. Actions Correctives recommandées
<!-- Préconisation de changement de politique et de configuration permettant la
suppression ou l’évitement des nuisances relevées dans le chapitre précédent -->
> Pour éviter les nuisances vues précédemment, les correctifs sont relativement simples. Il suffit de mettre les services à jour et d'opter pour une politique de mot de passe plus robuste.

## 3. Surface d’attaque du Pentest

### a. Service FTP
<!-- Description du service, usage normal de ce service, liste ordonnée des vulnérabilités
par criticité décroissante, exploitation possible. Actions correctives. -->
> Ce service a pour but principal de permettre un accès à distance des fichiers présent sur la machine pour les télécharger ou en télécharger vers la machine.


**1. Vulnérabilité 1**


- *Nom*: [CVE-2019-12815](https://nvd.nist.gov/vuln/detail/CVE-2019-12815)
- *Score CVSS*: 7.5
- *Description*: Un attaquant peut envoyer des fichiers arbitraires sans authentification qui peut mené a une rce (remote code execution) et a une divulgation d'information.
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.6 ou ultérieure.

**2. Vulnérabilité 2**

- *Nom*: [CVE-2011-1137](https://nvd.nist.gov/vuln/detail/CVE-2011-1137)
- *Score CVSS*: 5.0
- *Description*: Un attaquant peut provoquer un déni de service sur un serveur FTP ProFTPD antérieur à 1.3.7rc2 en envoyant une commande trop longue au serveur qui provoque une boucle infinie dans l'un des fichiers
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.7rc2 ou ultérieure.

**3. Vulnérabilité 3**

- *Nom*: [CVE-2019-18217](https://nvd.nist.gov/vuln/detail/CVE-2019-18217)
- *Score CVSS*: 5.0
- *Description*: Un attaquant peut provoquer un déni de service sur un serveur FTP ProFTPD 1.3.3d ou antérieur en envoyant une requête malformée. La requête malformée provoque un dépassement d'entier dans le module mod_sftp, ce qui entraîne un OOM Kill.
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.4 ou ultérieure.

### b. Service SSH
<!-- Même chose pour chaque service étudié dans le Pentest d’une cible -->
**1. Vulnérabilité 1**

- *Nom*: [CVE-2016-6515](https://nvd.nist.gov/vuln/detail/CVE-2016-6515)
- *Score CVSS*: 7.8
- *Description*: Un attaquant peut envoyer une requête malformée (mot de passe trop long) pour provoquer un déni de service car la fonction `auth_password` ne limite pas la longueur du mot de passe.
- *Patch*: Mise à jour du serveur SSH vers la version 7.3 ou ultérieure.

**2. Vulnérabilité 2**

- *Nom*: [CVE-2015-8325](https://nvd.nist.gov/vuln/detail/CVE-2015-8325)
- *Score CVSS*: 7.2
- *Description*: Un attaquant peut utiliser une variable d'environnement `LD_PRELOAD` pour exécuter du code arbitraire avec les privilèges de l'utilisateur.
- *Patch*: Mise à jour du serveur SSH vers une version ultérieure à 7.2p2.

**3. Vulnérabilité 3**

- *Nom*: [CVE-2019-6111](https://nvd.nist.gov/vuln/detail/CVE-2019-6111)
- *Score CVSS*: 5.8
- *Description*: Un attaquant peut modifier les fichiers du client en envoyant des fichiers malveillants via scp.
- *Patch*: Mise à jour du serveur SSH vers une version ultérieure à 7.9.


### c. Service WEB
<!-- Même chose² pour chaque service étudié dans le Pentest d’une cible -->
**1. Vulnérabilité 1**

- *Nom*: [CVE-2017-3167](https://nvd.nist.gov/vuln/detail/CVE-2017-3167)
- *Score CVSS*: 7.5
- *Description*: Un attaquant peut contourner les exigences d'authentification en utilisant `ap_get_basic_auth_pw()` dans des modules tiers en dehors de la phase d'authentification.
- *Patch*: Mise à jour du serveur Apache vers la version 2.4.26 ou ultérieure.

**2. Vulnérabilité 2**

- *Nom*: [CVE-2021-40438](https://nvd.nist.gov/vuln/detail/CVE-2021-40438)
- *Score CVSS*: 6.8
- *Description*: Un attaquant peut utiliser une requête malformée pour faire en sorte que le serveur Apache redirige la requête vers un serveur choisi par l'attaquant.
- *Patch*: Mise à jour du serveur Apache vers la version 2.4.50 ou ultérieure.

**3. Vulnérabilité 3**

- *Nom*: [CVE-2019-10098](https://nvd.nist.gov/vuln/detail/CVE-2019-10098)
- *Score CVSS*: 5.8
- *Description*: Un attaquant ayant  accès aux fichiers de configuration du serveur Apache peut modifier le mod_rewrite pour rediriger les requêtes vers un site malveillant.
- *Patch*: Mise à jour du serveur Apache vers la version 2.4.40 ou ultérieure.



