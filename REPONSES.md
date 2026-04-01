Question (Ex1) : Une méthode default dans une interface peut-elle accéder aux champs privés de la classe qui l'implémente ? Justifiez, en vous appuyant sur isDefective() dans Qualifiable et getQualityScore() dans Duck. 

    Non une méthode défault dans une interface ne peut pas accéder au attribut private. Une interface est juste un contrat, elle est aveugle à ce qui se passe dans les classes qui l'implémente.
    C'est ce qu'on voit avec isDefective(), il est obligé de passer par getQualityScore() qui lui même reste abstraite et attend d'etre implémenter par Duck pour pouvoir fonctionner

Question (Ex2) : Dans ce projet, Maintainable est une interface et Machine est une classe abstraite. Quelle règle Java vous aurait empêché de faire l'inverse (rendre Maintainable abstraite et Machine une interface) ? Plus généralement, quand choisit-on une interface plutôt qu'une classe abstraite ?

    On mettant machine en Interface nous n'aurions pas pu déclarer des attributs. En mettant Maintenable en classe abstraite il aurait fallu lui déclarer un constructeur.
    