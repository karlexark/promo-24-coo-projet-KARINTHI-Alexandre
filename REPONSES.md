Question (Ex1) : Une méthode default dans une interface peut-elle accéder aux champs privés de la classe qui l'implémente ? Justifiez, en vous appuyant sur isDefective() dans Qualifiable et getQualityScore() dans Duck. 

    Non une méthode défault dans une interface ne peut pas accéder au attribut private. Une interface est juste un contrat, elle est aveugle à ce qui se passe dans les classes qui l'implémente.
    C'est ce qu'on voit avec isDefective(), il est obligé de passer par getQualityScore() qui lui même reste abstraite et attend d'etre implémenter par Duck pour pouvoir fonctionner

Question (Ex2) : Dans ce projet, Maintainable est une interface et Machine est une classe abstraite. Quelle règle Java vous aurait empêché de faire l'inverse (rendre Maintainable abstraite et Machine une interface) ? Plus généralement, quand choisit-on une interface plutôt qu'une classe abstraite ?

    On mettant machine en Interface nous n'aurions pas pu déclarer des attributs. En mettant Maintenable en classe abstraite il aurait fallu lui déclarer un constructeur.

Question (Ex4) : Expliquez pourquoi canBeFulfilled(Stock<Duck> stock) serait une signature plus restrictive que canBeFulfilled(Stock<? extends Duck> stock). Donnez un exemple de code Java qui compilerait avec la seconde mais pas avec la première.

    En java les types génériques sont invariant, cela veut dire que même si StandardDuck hérite de Duck et bien Stock<StandardDuck> n'hérite pas de Stock<Duck>

    Son avait ultiliser Stock<Duck> on aurait pu uniquement mettre uniquement une liste exactement Stock<Duck> dans la méthode

    En utilisant un joker on rend le paramètre covariant, en rajoutant extend Duck on accepte tout les types d'objets à condition qu'il soit Duck ou sous classe du Duck

    Exemple : 
    Stock<StandardDuck> stockExclusifStandard = new Stock<>();
    Order commande = new Order(DuckType.STANDARD, 10, 25.0, 3);

    avec Stock<Duck>
    boolean possible1 = commande.canBeFulfilled(stockExclusifStandard); // ne compilera pas car pas Stock<Duck> mais Stock<StandardDuck>

    avec Stock<? extends Duck>
    boolean possible2 = commande.canBeFulfilled(stockExclusifStandard); // ça compiler car StandardDuck est une sous classe de Duck
