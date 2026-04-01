Question (Ex1) : Une méthode default dans une interface peut-elle accéder aux champs privés de la classe qui l'implémente ? Justifiez, en vous appuyant sur isDefective() dans Qualifiable et getQualityScore() dans Duck. 

    Non une méthode défault dans une interface ne peut pas accéder au attribut private. Une interface est juste un contrat, elle est aveugle à ce qui se passe dans les classes qui l'implémente.
    C'est ce qu'on voit avec isDefective(), il est obligé de passer par getQualityScore() qui lui même reste abstraite et attend d'etre implémenter par Duck pour pouvoir fonctionner

