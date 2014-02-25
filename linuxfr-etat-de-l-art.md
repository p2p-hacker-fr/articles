Étant un amoureux des protocoles et services pair-à-pair et/ou fortement décentralisés, et constatant l'engouement de la _moulosphère_ à ce sujet, je prend aujourd'hui l'initiative de rédiger un état de l'art (qui j'espère donnera suite à des revues d'activité), en me basant sur les ressources de la communauté « p2p-hackers ». 



 **Toute collaboration à la rédaction de cette dépêche est, même sous forme de remarques acerbes venant de nazis de l'orthographe, la bienvenue.**


Seuls les projets libres accompagnés d'une implémentation de référence libre sont répertoriés ici. Plus que par conviction, cette sélection permet de limiter le nombres de citation (les projets non-libres sont très nombreux) et de fournir les informations sur le code source, telle que la licence choisie ou encore le langage de programmation principal.


# Décentralisation de quoi ?



Dans ce premier chapitre, je vais essayer de clarifier certains concepts clés (en expliquant comment je les comprends), comme la « décentralisation » et le domaine « pair-à-pair ».



## Internet, Web et les différentes « centralisations »



Tout d'abord, c'est beau de parler de décentralisation, mais constatons d'abord ce que l'on appelle « centralisation ». Ce terme peut soulever plusieurs interprétations, dont voici une liste incomplète :



* La centralisation des infrastructures de l'Internet autour du modèle « datacenter ».
* La centralisation des services Web autour d'un petit nombre de services non-libres (services Google, Facebook, Twitter, etc).
* La présence de points de centralisation dans certains protocoles (serveurs DNS primaires, serveurs d'authentification, serveurs HTTP, etc)



## Qu'est-ce que le pair-à-pair ?



On entend beaucoup parler de « protocoles pair-à-pair », « services pair-à-pair » ou encore « partage pair-à-pair », sans forcément avoir une image claire de ce à quoi cet adjectif « pair-à-pair » se rapporte. Je vous propose, ici, la définition que je préfère, compilée à partir de plusieurs cours de référence dans le domaine :



_L'adjectif « pair-à-pair » qualifie un modèle d'architecture de système distribué. Il est né en opposition au modèle traditionnel « client/serveur », traduisant l'idée qu'un système distribué peut être constitué de « pairs », dont aucun n'a de rôle particulier. Chaque machine, généralement appelée « pair » ou « nœud », joue à la fois les rôles de client et de serveur._



D’après [la synthèse proposée par Rodrigues et Druschel en 2010](http://cacm.acm.org/magazines/2010/10/99498-peer-to-peer-systems/fulltext) les systèmes pair-à-pair sont des systèmes distribués qui présentent les propriétés suivantes :



* **Haut degré de décentralisation** : Les pairs prennent le rôle de client et de serveur,
et la majeure partie de l’état du système et des tâches sont dynamiquement distribués
parmi les pairs. Il existe peu de nœuds, voire aucun, possédant un état centralisé.
L’ensemble des besoins de calcul, de stockage et de communication liés à l’exécution du
système est alors fourni de façon collaborative par les membres du système pair-à-pair.



* **Organisation automatique** :
Une fois qu’un nœud est introduit au sein du système
(typiquement en lui fournissant l’adresse IP d’un des membres), aucune configuration
manuelle n’est nécessaire pour maintenir l’exécution du système pair-à-pair.



* **Entités administratives multiples** :
Les nœuds participant au système pair-à-pair
dépendent rarement d’une seule entité administrative. Dans la plupart des cas, chaque
nœud appartient à un contributeur particulier souhaitant participer à la vie du système.



* **Faible coût de déploiement** :
N’utilisant pas, ou peu, d’infrastructure dédiée, le coût
de déploiement initial d’un service pair-à-pair est généralement faible en comparaison
du coût de déploiement des services utilisant une architecture de type client/serveur.



* **Croissance organique** :
Étant donné que la majeure partie des ressources exécutant
le système sont fournies par les pairs, c’est-à-dire les clients du service, la croissance
d’un système pair-à-pair ne nécessite pas de mises à jour franches de l’infrastructure
hôte, par exemple le remplacement d’un serveur par un matériel plus puissant.



* **Robustesse aux pannes et aux attaques** :
Les systèmes pair-à-pair sont généralement résistants aux pannes, car il existe peu, ou pas, de nœud dont la présence est
critique pour l’exécution du service associé. Pour attaquer ou rendre inaccessible un
système pair-à-pair, un tiers malveillant doit prendre pour cible une grande partie des
nœuds du système simultanément.



* **Abondance et hétérogénéité des ressources** :
Les systèmes pair-à-pair les plus
populaires rassemblent une quantité de ressources informatiques que peu d’entreprises
peuvent prétendre acquérir individuellement. Les ressources sont hétérogènes en terme
d’architecture matérielle et logicielle, de méthode d’accès à Internet, ou encore de situation géographique. Cette diversité contribue à réduire les pannes, les attaques et même
la censure rencontrée dans ce type de système distribué.



Pour conclure, le « modèle pair-à-pair » est un outil qui permet d'architecturer un système, un service distribué, avec une optique de décentralisation. Cette décentralisation peut être partielle (présence d'un serveur centralisé), importante (présence de nœuds particuliers, par exemple des « trackers ») ou totale (absence de tout point de centralisation).

## Vers la décentralisation



* Répartition de la charge (de bande passante (Bittorent), de calcul (), de stockage ).
* Distribution de l'autorité (défaut de Napster, succès de Bitcoin ?).



Note : les protocoles p2p non totalement décentralisés (ex : Bitorrent, BOINC...) ne sont pas présentés ici.



**TODO** : faire un glossaire, ou parler de **churn**



# Systèmes basés sur Bitcoin 1.0



Les systèmes basés sur la crypto-monnaie [Bitcoin](https://bitcoin.org) ont la côte (notez la touche d'humour). Plus sérieusement, la base solide du code de Bitcoin a permis le développement de plusieurs projets sérieux et populaires. À noter qu'il existe de très nombreux projets autours des crypto-devises, qui ne seront pas cités ici par soucis de concision.

## Bitcoin
* _Site web du projet_ : [bitcoin.org/](https://bitcoin.org/)
* _Année de déploiement_ : (2009)
* _Implémentation de référence_ : [github.com/bitcoin/bitcoin](https://github.com/bitcoin/bitcoin) (C++) (MIT)



Il est difficile de faire mieux que le [journal de Gof](http://linuxfr.org/users/gof/journaux/comment-fonctionne-bitcoin) pour décrire Bitcoin :



> Le but de Bitcoin est d'être une monnaie et un moyen de paiement sur Internet décentralisé hors du contrôle des gouvernements, des banques ou d'une seule société.



> Le mot « Bitcoin » fait référence au protocole décrivant cette monnaie virtuelle ainsi qu'à son implantation de référence. C'est aussi le nom de l'unité de cette monnaie.



> Bitcoin est décentralisé. Quiconque le souhaite peut devenir un nœud du réseau, en installant le logiciel.



## BitMessage ##
* _Site web du projet_ : [https://bitmessage.org/wiki/Main_Page](https://bitmessage.org/wiki/Main_Page)
* _Année de déploiement_ : (2012)
* _Implémentation de référence_ : [github.com/Bitmessage/PyBitmessage](https://github.com/Bitmessage/PyBitmessage) (Python) (MIT)



Bitmessage est un protocole pair-à-pair de communication, basé sur la crypto-devise « Bitcoin », et utilisé pour envoyer des messages encryptés à une personnes ciblée ou à un groupe d'abonnés. Ce protocole est décentralisé et ne demande aucune confiance dans une entité centralisée particulière, telle qu'une autorité de certification. Il utilise une authentification forte, ce qui signifie que l'identité de l'auteur d'un message ne peut théoriquement pas être usurpée. Bitmessage a pour objectif de cacher toutes les méta-données, telles que l'identité de l'auteur et du (ou des) destinataire(s), d'un espionnage potentiel de type « écoute téléphonique ».



Pour les détails techniques, il y a le [journal de julmx](https://linuxfr.org/users/julmx/journaux/bitmessage-envoi-de-messages-chiffres-en-p2p) (et les commentaires associés), ainsi que [l'article de Stéphane Bortzmeyer](http://www.bortzmeyer.org/bitmessage.html), qui étudie notamment le protocole d'un point de vue écologique :)

Source supplémentaire, ce [comparatif](https://bitmessage.org/wiki/FAQ#How_does_Bitmessage_compare_to_other_messaging_methods) positionne de façon intéressante BitMessage par rapport aux autres logiciels de messagerie.

A noter l'existence d'un projet dérivé : « [BitGroup](http://www.bitgroup.org/), qui a pour objectif de construire un réseau social au dessus de BitMessage.


## Namecoin
* _Site web du projet_ : [namecoin.info/](http://namecoin.info/)
* _Année de déploiement_ : (2011)
* _Implémentation de référence_ : [https://github.com/namecoin/namecoin/tree/vQ.3.72](https://github.com/namecoin/namecoin/tree/vQ.3.72) (C++/QT) (MIT)

Namecoin est un service décentralisé et libre de transfert et d'enregistrement de type clef/valeur, basé sur la technologie Bitcoin. Il permet notamment d'enregistrer et de transférer des noms arbitraires (clefs), et d'associer des données (valeurs) à ces noms (520 Octets pour le moment), le tout à l'abri de la censure. Les actions (enregistrement, transferts) se font grâce à une monnaie internationale propre au système : le « NMC ».

Pour approfondir Namecoin, il y a le [journal de Khalahan](https://linuxfr.org/users/khalahan/journaux/namecoin-dns-decentralise-ou-bdd-cle-valeur-en-p2p) et l'[article de Stéphane Bortzmeyer](http://www.bortzmeyer.org/namecoin.html), qui sont de bonnes ressources.

## Twister
* _Site web du projet_ : [twister.net.co/](http://twister.net.co/)
* _Année de déploiement_ : (2013)
* _Implémentation_ : [github.com/miguelfreitas/twister-core](https://github.com/miguelfreitas/twister-core) (C++) (MIT/BSD)


Twister est un service totalement décentralisé de « microblogging », qui met en avant les trois points suivants :


* **Liberté d'expression** : la nature décentralisée de Twister empêche la censure. De fait, il est impossible d'effacer un billet, de censurer son contenu, ou encore de désactiver le compte d'un utilisateur.


* **Pas d'espionnage** : les données et méta-données (identifiants auteur/destinataire) des communications privées sont protégées par le protocole, notamment en utilisant des méthodes de cryptographie.


* **Préservation de l'anonymat** : l'adresse IP utilisée pour communiquer via Twister n'est enregistrée par aucun serveur. Dans son utilisation normale (si vous n'êtes pas espionné), votre présence sur le réseau n'est pas surveillée.

Pour approfondir sur Twister il y a le [journal de fredix](http://linuxfr.org/users/fredix/journaux/twister-un-microblog-opensource-p2p) ([promu en dépêche](http://linuxfr.org/news/twister-un-microblog-opensource-p2p)), et aussi [un billet de 
Stéphane Bortzmeyer](http://www.bortzmeyer.org/twister.html).

# Partage/Stockage distribué
## Freenet



* _Site web du projet_ : [freenetproject.org/](https://freenetproject.org/index.html)
* _Année de déploiement_ : (2000)
* _Implémentation de référence_ : [github.com/freenet/](https://github.com/freenet/) (Java) (GPL)



_Résumé :_ Freenet est un réseau pair-à-pair qui a vu le jour dans le cours de l'année 2000 et qui a été suivi par de (très) nombreuses [entrées sur DLFP](http://linuxfr.org/recherche?utf8=%E2%9C%93&q=freenet). Le service proposé est un _« Internet dans l'Internet »,_ qui fournit principalement du partage de contenu (fichiers et/ou sites web appelés « freesites ») et de la messagerie (type mail). L'hébergement des contenus est anonymisé, chiffré et distribué entre les pairs. Il en résulte une quasi impossibilité de censurer les contenus, caractéristique du réseau Freenet. Son réseau est de type « Darknet » ou encore « smallworld », c'est-à-dire que la connexion entre les pairs est établie au cas par cas, selon un réseau de pairs de confiance, ou « amis » pour reprendre le terme des réseaux sociaux. La topologie résultante est donc « non structurée ».



## Tahoe-LAFS
* _Site web du projet_ : [tahoe-lafs.org](https://tahoe-lafs.org/trac/tahoe-lafs)
* _Année de déploiement_ : (2008)
* _Code source_ : [github.com/tahoe-lafs/tahoe-lafs](https://github.com/tahoe-lafs/tahoe-lafs) (Python) (GPL/[TGPPL](https://tahoe-lafs.org/trac/tahoe-lafs/browser/COPYING.TGPPL.rst))


_Tahoe-Least-Authority Filesystem_ (Tahoe-lafs) est un système de fichiers distribué « dans le Cloud ». Il sait distribuer les fichiers sur diverses topologies composées de serveurs potentiellement hétérogènes. Si un ou plusieurs de ces serveurs tombe en panne ou est compromis par une attaque, le système de fichiers continue de fonctionner correctement, tout en préservant l'intégrité, la sécurité et la confidentialité des fichiers de l'utilisateur.



Tahoe-LAFS est la première technologie de stockage basée sur des logiciels libres à proposer un stockage distribué dont la sécurité est indépendante des hébergeurs de données. Une sécurité indépendante des hébergeurs signifie que l'intégrité et la confidentialité de vos fichiers est garantie grâce à des opérations mathématiques (cryptographie, code de correction, etc.), qui sont calculées côté client et donc indépendamment des serveurs d'hébergement, lesquels sont potentiellement fournis par des tiers.



Pour avoir une idée de l'utilisation de Tahoe-LAFS, les cas d'usage suivant sont [répertoriés](https://tahoe-lafs.org/trac/tahoe-lafs/wiki/UseCases) :
![use case table](http://vlamy.fr/img/tahoe-uc.png)



## Bitcloud
* _Site web du projet_ : [http://bitcloudproject.org](http://bitcloudproject.org/wiki/index.php/Main_Page)
* _Année de déploiement_ : (2014)
* _Implémentation de référence_ : [github.com/wetube/bitcloud](https://github.com/wetube/bitcloud) (C) (MIT)

Bitcloud est un service de stockage décentralisé et de « tenu de compte séquestre », qui permet à des clients appelés « éditeurs » de payer des nœuds volontaires pour y stocker et partager des données cryptées. La nature décentralisée de Bitcloud permet à n'importe quel utilisateur de publier du contenu en tirant profit des infrastructures populaires (machines des utilisateurs et bénévoles) et sans utiliser de logiciel « propriétaire », le tout en étant protégé de la censure. L'idée du projet Bitcloud est de fournir les fondations technologiques pour des applications décentralisées basées sur les crypto-devises, et qui mettent en place des mécanismes de « motivations économiques » (« _economic incentives_ » étant un terme que je n'ai jamais réussi à traduire), notamment avec des transactions via des comptes séquestres et des services contractuels.

Un scénario pour illustrer le principe de Bitcloud ([source](http://bitcloudproject.org/w/Bitcloud_as_an_Escrow_Agent)) : Le scénario commence avec un éditeur qui choisi le nœud ou groupe de nœuds, qui propose le service de stockage qui lui paraît le mieux adapté à ses besoins. En utilisant un client Bitcloud, cet éditeur pourra consulter toutes les offres proposées par les nœuds du réseau Bitcloud, ainsi que leur prix et la réputation des nœuds en question. Disons que notre éditeur a trouvé un groupe de nœuds proposant l'hébergement de 500Go de données pour une somme de 10mBTC (la crypto-devise du système Bitcloud) par mois. L'éditeur va envoyer un paiement de 10 mBTC à ce groupe de nœuds par l'intermédiaire du réseau Bitcloud. Le paiement sera alors placé sur un « compte séquestre » et lié à un contrat de service, en utilisant le réseau Bitcloud comme médiateur. Ce médiateur décentralisé va notamment s'assurer que le groupe de nœuds fournit bien le service stipulé par le contrat. Une fois le mois écoulé, le réseau Bitcloud valide le paiement pour le groupe de nœuds.

À noter qu'il existe le concept de grille de nœuds, qui regroupe plusieurs nœuds par affinité sociale ou économique et organise ce groupe pour fournir un service collaboratif, lequel se matérialise par une offre commune sur le marché Bitcloud. La grille organise aussi la répartition des gains, le tout en utilisant des mécanismes de consensus distribués.


Pour finir, l'application de référence construite au dessus de Bitcloud est [WeTube](http://bitcloudproject.org/w/WeTube). Cette application vise à concurrencer YouTube, mais son développement ne semble pas encore avoir commencé (Bitcloud semble être un projet très jeune, démarré début 2014).

## Cryptosphere
* _Site web du projet_ : [cryptosphere.org](http://cryptosphere.org/)
* _Année de déploiement_ : (?)
* _Implémentation de référence_ : [github.com/cryptosphere/cryptosphere](https://github.com/cryptosphere/cryptosphere) (Ruby) (MIT)



## SyncNet
* _Site web du projet_ : [jack.minardi.org/software/syncnet-a-decentralized-web-browser/](http://jack.minardi.org/software/syncnet-a-decentralized-web-browser/)
* _Année de déploiement_ : (2013/2014)
* _Implémentation de référence_ : [github.com/jminardi/syncnet](https://github.com/jminardi/syncnet) (Python)(MIT)


## Trackerless Bittorent

# Protocoles de routage
## Babel
* _Site web du projet_ : [www.pps.univ-paris-diderot.fr/~jch/software/babel/](http://www.pps.univ-paris-diderot.fr/~jch/software/babel/)
* _Année de déploiement_ : (2007)
* _Code source_ : [git.wifi.pps.univ-paris-diderot.fr/babeld ](git://git.wifi.pps.univ-paris-diderot.fr/babeld ) (C) (MIT)


## CJDNS
* _Site web du projet_ : [cjdns.info](http://cjdns.info/)
* _Année de déploiement_ : (2011/2012)
* _Implémentation de référence_ : [github.com/cjdelisle/cjdns/](https://github.com/cjdelisle/cjdns/) (C) (GPL)



## IPOP
* _Site web du projet_ : [ipop-project.org/](http://ipop-project.org/)
* _Année de déploiement_ : (2013)
* _Implémentation de référence_ : [github.com/ipop-project](https://github.com/ipop-project) (C++/Python) (MIT)

