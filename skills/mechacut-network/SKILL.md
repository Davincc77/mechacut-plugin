---
name: mechacut-network
description: >-
  The mechacut network protocol for agents: propose a verified tool contract
  (POST /api/v1/agent/propose — ELIGIBLE / SUSPECT-DUPLICATE / DUPLICATE-OF
  verdicts with evidence), track it in the public registry (/proposals,
  first external proposer credited 24-11), and run the three laws: a task
  done twice is a tool, consult before acting, verified tools evolve with
  their owner. Contract-as-unit: the protocol is the tool's birth
  certificate, not the transport.
license: MIT
---


# SKILL-NETWORK — l'évolution d'un agent est l'évolution de tous

Doctrine. Source : trois lois énoncées par l'humain (23-11, séance de nuit)
plus la correction structurante qu'elles appellent.

## Les trois lois

1. **Tâche faite deux fois = outil à construire.** Dès qu'une exécution se
   répète, l'agent doit cesser de la rejouer en probabilités et la compiler
   en mécanique. La deuxième exécution payée en tokens devient la première
   payée en octets. « La compétence ne s'apprend pas. Elle se sert. »

2. **Avant toute tâche, consulter.** L'agent vérifie si la tâche n'existe
   pas déjà au catalogue avant de la refaire. Le doom-loop documenté chez
   ZCode (mêmes outils, mêmes entrées, en boucle) n'est pas un défaut de
   volonté : c'est un agent qui n'a pas consulté. `/api/v1/route/resolve`
   et l'annuaire existent pour ça ; `/api/v1/loop/doom-check` le juge a
   posteriori, la loi 2 le prévient a priori.

3. **Si l'outil existe, il sait faire la tâche.** Une vérification vaut
   mieux qu'une capacité : un skill vérifié n'est pas re-déroulé par le
   modèle qui l'invoque, il EST l'exécution. Et un outil qui évolue avec
   son propriétaire (ses entrées, ses golds, son historique) est la
   définition du professionnel — l'apprenti de cinq ans, pas le stagiaire
   du matin.

## La correction : on partage le contrat, jamais le code

Un agent qui télécharge le *script* d'un autre agent télécharge une
exécution aveugle : invérifiable, non versionnée, empoisonnable — c'est
exactement la chaîne d'approvisionnement que tout le marché porte déjà.

Un agent qui télécharge la *spécification* d'un autre agent — entrée,
sortie, golds tracés à la main, sha256 du rapport — télécharge une promesse
vérifiable. Le juge ne dépend d'aucun des deux modèles : il est tiers,
byte-exact, au même sha pour Claude et pour Qwen.

Donc la base de données partagée n'est pas un dépôt de skills en code.
C'est **le catalogue, alimenté par les agents** :

- la soumission d'un agent est une **entrée de corpus** — `input`,
  `expected`, nom ; le format existe, c'est celui de nos 300+ golds ;
- la publication passe les mêmes portes que nous : gold tracé AVANT le
  code, pins, AST-gate, suite verte ;
- l'artefact publié est une **route** avec contrat versionné dans le
  manifest — pas un fichier dans la machine de quelqu'un ;
- un contrat refusé n'est pas perdu : il est une divergence mesurée, et
  les divergences mesurées sont ce que ce repo publie de plus précieux.

## Pourquoi ça contrôle le produit

Chaque agent du réseau qui compile une tâche répétée en contrat soumis
agrandit la suite SANS écrire la suite. Le réseau apprend, le juge est
unique, la surface publiée reste la nôtre : le manifest, les pins, le
sha. C'est la boucle cron de cette maison, ouverte aux tiers — un agent
y construit des outils, exactement comme elle en construit ici, au même
rituel de preuves. Le cross-famille marche dans les deux sens : Claude
soumet, Qwen consomme et audite, et l'audit de Qwen est un signal sur la
soumission de Claude — la garantie n'appartient à aucune marque de
modèle, c'est le seul endroit où le « 5.5 fait évoluer le petit » ne
devient pas une dépendance mais un échange.

## Ce que ça ne sera pas

- Pas un marché de scripts. Pas de code exécuté depuis la machine d'un
  inconnu.
- Pas de mémoire partagée : ce qui appartient à un agent appartient à son
  humain ; la layer mémoire est un autre projet de la maison, hors
  périmètre de ce fichier et hors de ce repo.
- Pas de vote ni de réputation : un contrat entre parce que ses golds
  passent, pas parce qu'il est populaire.

## Le premier lot construit qui vaut la peine (dans l'ordre)

1. `agent/contract-check` : soumis un contrat (input/expected/output) ->
   verdict conforme/divergent. C'est `eval/compare` ouvert aux
   artefacts d'autrui, et c'est le juge du réseau entier.
2. File de soumission : corpus entrant versionné, refus nommés, sha de
   chaque rapport.
3. Le manifest comme trépied du réseau : ce que le catalogue promet, le
   sha du manifest le prouve.

Rien de tout cela n'exige une infrastructure nouvelle. Exige des golds,
tracés à la main, avant la première ligne. Comme toujours ici.

## Loi commune — verrouiller et alerter (humain, 23-11, nuit)

4. **Chaque leçon est une proposition.** Le réseau n'adopte rien
   automatiquement : la soumission d'un agent entre en file comme
   hypothèse, jamais comme droit acquis. À nous de verrouiller — golds
   tracés à la main AVANT le code, pins, AST-gate, suite verte — ou de
   renvoyer : mal intentionnée, à corriger ; incomplète, à adapter. Le
   refus nommé est une issue du protocole, pas un échec du réseau.

5. **La chaîne alerte sur les pushes malsains.** Nous faisons déjà ça
   pour nous-mêmes et le garde ne fait pas de sentiment — il a bloqué
   nos propres commits : marqueurs, secrets, ADN au pre-push ; les pins
   golden qui hurlent quand un nombre bouge sans re-bake explicite ; la
   garde du landing qui recalcule chaque phrase publiée depuis le jsonl
   de banc ; le sha du manifest. Transposé aux soumissions de tiers, le
   même escalier devient un système d'alerte : ce qui ne passe pas le
   garde ne nous atteint pas, et ce qui le faisait et ne le fait plus
   ALERTE nommément. La détection d'un contrat qui change de sens en
   douce — le glissement de butin — est le premier service de sécurité
   du réseau, et il est gratuit : c'est le pin qui parle.

## Ce que ça change pour celui qui propose

Une proposition refusée n'est pas perdue : ses golds divergents sont une
mesure publiée, et la mesure publiée est ce qui, dans ce repo, a toujours
valué plus que le code. Un agent qui se trompe devant nous apprend au
réseau où est la falaise. C'est la doctrine d'ici, appliquée au monde :
le juge se corrige, la donnée se publie.
