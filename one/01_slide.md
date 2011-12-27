!SLIDE
# utilisation de Cucumber avec Pivotal Tracker

!SLIDE bullets incremental
## Sondage

* combien de personnes ne connaissent pas cucumber ?
* combien de personnes écrivent des tests ?
* combien de personnes écrivent des tests avant de coder ?
* combien de personnes écrivent des tests avant de coder tous les jours ?
* combien de personnes écrivent des tests avant de coder à chaque fois qu'ils ont quelque chose à coder ?


!SLIDE
## Cucumber

* Créé par Aslak Hellesøy en 2008
* But : avoir un outil permettant d'écrire des user stories en texte pur.
* Aslak pensait merger son outil à Rspec, et n'imaginait pas l'essor que celui-ci a pris

!SLIDE transition=uncover
## Installation

1. ajouter cucumber-rails et database-cleaner dans le Gemfile

        @@@ ruby
        group :test do
          gem 'turn', '0.8.2', :require => false
          gem 'cucumber-rails'
          gem 'database_cleaner'
        end

2. installer cucumber dans le projet

        @@@ sh
        rails g cucumber:install



!SLIDE
## Première étape : savoir de quoi on parle

* Le "In order to" est la valeur ajoutée de ce qu'on va coder
* C'est là qu'on va savoir si ce qu'on fait a vraiment de la valeur pour nos utilisateurs
* C'est la partie essentielle du travail, elle nous permet de voir s'il y a bien du business derrière une fonctionnalité

!SLIDE bullets incremental

## Loi des 5 pourquoi

* Poser la question pourquoi récursivement 5 fois (au maximum) jusqu'à avoir une des réponses suivantes :

* Protéger les recettes
* Augmenter les recettes
* Diminuer les coûts
* Augmenter la valeur de la marque
* Faire du produit un produit remarquable
* Apporter plus de valeur aux clients

!SLIDE
## Ensuite, on commence à réfléchir à un scénario avec les Given When Then

* état initial
* introduction d'une perturbation au système
* assertion : vérification que le système est dans un état définit

!SLIDE
## Exemple 1 : On se propose de gérer un chenil (des chiens, des naissances, etc.)

        @@@ cucumber
        Feature: handle a kenel
          In order to handle our kenel
          As a dog trainer
          I want to be able to relate born dogs

!SLIDE
## Application de gestion de chenil

* état initial : soit un chenil habité par 2 chiens 1 mâle et 1 femelle
* perturbation du système : les 2 chiens copulent et ont un petit
* assertion : le chenil devrait avoir 3 habitants



!SLIDE
## En cucumber on va écrire ça de la façon suivante :

        @@@ cucumber
        Given 1 dog and 1 bitch in a kennel
        When the 2 dogs have a child
        Then the kennel should have 3 inhabitants

!SLIDE
# Ces scénarios n'ayant pas grand chose à voir avec quelque chose de monétisables, nous n'allons donc pas les coder.
En effet, nous ne sommes pas une communauté de dresseurs, et nous gagnerions plus à travailler sur un projet qui pourrait
nous être utile...

!SLIDE
# Passons donc à un VRAI problème que nous avons dans cette communauté
Un espace permettant de proposer des conférences pour les prochains évènements !

!SLIDE

# Soit 2 personnes (dont une morale)

1. product owner => Thibaut Assus
2. developer => Milesrock

!SLIDE

# méthode de travail avec cucumber et pivotal (1/2)

1. le product owner propose une user story au développeur
2. le développeur lui demande quelle est la valeur ajoutée de cette fonctionnalité
3. ils se mettent d'accord sur la valeur ajoutée
4. le product owner poste la user story dans pivotal tracker (ou sur un vrai tableau)
5. le développeur estime (0, 1, 2 ou 3 points)
6. il débute le développement (et clique sur start)
7. il finit le développement (et clique sur stop)
8. il livre la story sur internet (et clique sur deliver)

!SLIDE

# méthode de travail avec cucumber et pivotal (2/2)

9. le product owner refuse tant de fois qu'il veut la story (tant qu'elle ne satisfait pas ses requirements)
10. il doit donner une raison à chaque fois
11. le développeur peut alors cliquer sur restart, finish, deliver pour refaire un cycle de travail
12. Quand tout est ok, le product owner clique sur accept
13. La story est finie.


!SLIDE

## la méthode de travail de cucumber passe par 3 étapes de développement : Red, Green et Refactor

* Quand on lance notre premier test, on commence par avoir du jaune.
* Le jaune correspond à des steps non définis
* On va coder ce à quoi correspondent ces steps
* On relance notre test
* On code juste assez pour faire passer les tests
* On factorise le code pour supprimer la duplication

## On peut passer à la feature suivante !

!SLIDE

# Demo

!SLIDE
# Ressources

* Rspec, cucumber book : [http://pragprog.com/book/achbd/the-rspec-book](http://pragprog.com/book/achbd/the-rspec-book)
* le wiki du github de cucumber
* [http://cukes.info](http://cukes.info)

!SLIDE

# Merci !

Pour tout ce que qui n'était pas clair : mailez-moi ([thibaut@milesrock.com](thibaut@milesrock.com))
