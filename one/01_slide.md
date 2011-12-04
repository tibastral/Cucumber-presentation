!SLIDE
# Cucumber / VCR

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
## Given When Then

* état initial
* introduction d'une perturbation au système
* assertion : vérification que le système est dans un état définit

!SLIDE
## exemple : application de gestion de chenil

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

!SLIDE
# Ressources

* Rspec, cucumber book : [http://pragprog.com/book/achbd/the-rspec-book](http://pragprog.com/book/achbd/the-rspec-book)
* le wiki du github de cucumber
* [http://cukes.info](http://cukes.info)



!SLIDE

# Merci !

Pour tout ce que qui n'était pas clair : mailez-moi ([thibaut@milesrock.com](thibaut@milesrock.com))
