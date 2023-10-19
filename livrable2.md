# SAé3 Cyber04
*JOUET Malo & PENCRANE Alexis*


## 1. Présentation

### a. Objet du Pentest

> Un Pentest ou test d'intrusion a pour but de d'antisiper les risque d'ataque par intrusion d'une infrastructure, ainsi nous devons identifier les different levier d'action d'un attaquantetablir les vulnerabiliter de l'infrastructur et leur potentiel nuisance puis produire un plan d'action pour reduire c'est risque.

### b. Condition d'execution du Pentest 
<!-- Décrire avec quoi et sur quoi le Pentest s’applique -->
> Nous avons realiser un pentest de type blackbox, ce genre de pentest est une stratégie simulant une attaque réelle et engage des actions d’intrusion sur le SI via ses accès extérieurs, Tout en ne disposant d’aucune informations sur la cible.
```javascript
console.log("cc il faudrais finir la partie juste en haut stp")
```

## 2. Résultats du Pentest 

### a. Synthèse non technique
<!-- Conclusions du Pentest sur les aspects utilisateurs, qualité de la politique de sécurité et/ou qualité de mise en œuvre -->

> Le SI est tres vulnerable, un attaquant peu facilement bloquer l'accees à certains service pour le personnel comme pour le public tel que le site web ou vos accees a distance au SI. Il peut également usurper facilement une identité en se connectant avec les comptes administrateurs sur des services non-protéger. Concernant la potlitique de sécurité, il faudrait augmenter la compléxité des mots de passes pour les accèes administrateur, par exemple pour le site web.

### b. Synthèse technique
<!--  Conclusions du Pentest sur la sécurisation des services/protocoles et/ou la
qualité sécuritaire de leurs configurations-->
> Les services presents sur le serveur sont tous sur de vieilles versions qui regorgent de failles plus ou moins dangeureuse, certains mot de passes sont trop peu complexe (i.e: WordPress)
```javascript
console.log("cc il faudrais finir la partie juste en haut stp")
```

### c. Synthèse des Vulnérabilités prioritaires ou les plus critiques
<!-- Mise en avant des vulnérabilités jugées particulièrement critiques et leurs
potentiels de nuisances. Chacune précise un niveau de criticité et une estimation
du niveau de complexité à résoudre/corrige -->
> Une des vulnérabilités la plus critique est la backdoor sur le service ftp, celle ci est extremement simple a mettre en oeuvre et donne un accèes root aux serveurs ce qui permet a l'attaquant de faire ce qu'il veut sur la machine.
```javascript
console.log("cc il faudrais finir la partie juste en haut stp")
```

### d. Actions Correctives recommandées
<!-- Préconisation de changement de politique et de configuration permettant la
suppression ou l’évitement des nuisances relevées dans le chapitre précédent -->
> Pour éviter les nuissances vu précedement, les correctif sont relativement simple. Il suffit de mettre les services a jour et opter pour une politiques de mot de passe plus robuste.
```javascript
console.log("cc il faudrais finir la partie juste en haut stp")
```

## 3. Surface d’attaque du Pentes

### a. Service FTP
<!-- Description du service, usage normal de ce service, liste ordonnée des vulnérabilités
par criticité décroissante, exploitation possible. Actions correctives. -->
> Ce service a pour but principal de permettre un accès a distance des fichiers présent sur la machine pour les télécharger ou en télécharger vers la machine.


**1. Vulnérabilité 1**


- *Nom*: [CVE-2019-12815](https://nvd.nist.gov/vuln/detail/CVE-2019-12815)
- *Score CVSS*: 7.5
- *Description*: Un attaquant peut envoyer des fichier arbitraires sans authentification qui peut mené a une rce (remote code execution) et a une divulgation d'information.
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.6 ou ultérieure.

**2. Vulnérabilité 2**

- *Nom*: [CVE-2011-1137](https://nvd.nist.gov/vuln/detail/CVE-2011-1137)
- *Score CVSS*: 5.0
- *Description*: Un attaquant peut provoquer un déni de service sur un serveur FTP ProFTPD 1.3.3d ou antérieur en envoyant une requête malformée. La requête malformée provoque un dépassement d'entier dans le module mod_sftp, ce qui entraîne un OOM Kill.
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.4 ou ultérieure.

**3. Vulnérabilité 3**

- *Nom*: [CVE-2011-1137](https://nvd.nist.gov/vuln/detail/CVE-2011-1137)
- *Score CVSS*: 5.0
- *Description*: Un attaquant envoi une requête malformée au serveur FTP, ce qui provoque un OOM Kill qui aboutit donc a un déni de service.
- *Patch*: Mise à jour du serveur FTP vers la version 1.3.4 ou ultérieure.

### b. Service SSH
<!-- Même chose pour chaque service étudié dans le Pentest d’une cible -->

### c. Service WEB
<!-- Même chose² pour chaque service étudié dans le Pentest d’une cible -->

