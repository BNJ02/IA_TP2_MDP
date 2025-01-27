**Intelligence Artificielle : Travaux Pratiques sur les Processus de Décision Markoviens**

L'objectif est d'implémenter et d'évaluer les algorithmes d'itération de valeur et d'itération de politique pour les **Processus de Décision Markoviens** (MDP).

Nous étudions un petit exemple tiré du livre *Artificial Intelligence: A Modern Approach* de manière aussi générique que possible.

Nous modélisons l'environnement comme une zone rectangulaire carrelée de longueur **L** et de hauteur **H**. Vous pouvez réutiliser et adapter les structures de données et les fonctions du TP sur la recherche de chemin (*Path-finding lab*). Nous nous concentrons en particulier sur le petit environnement de **6×5** suivant :

![Environnement 6x5](image1.png)

Le nombre dans chaque case représente la récompense immédiate obtenue en s'y déplaçant.  
Les cases noires sont des murs infranchissables. Notez que, comme dans le TP sur la recherche de chemin, nous supposons que l'environnement est entouré de murs.  
Les cases avec des récompenses **+1** et **-1** sont des **nœuds terminaux** : lorsque le robot les atteint, il ne peut plus se déplacer. Par conséquent, l'utilité de ces cases (à partir de l'itération 1) est simplement la récompense immédiate.

Nous supposons qu'à chaque fois que le robot essaie de se déplacer dans une direction, il y a **10 % de chances** qu'il aille à gauche (par rapport à la direction choisie) au lieu d'aller tout droit, et **10 % de chances** qu'il aille à droite (toujours par rapport à la direction choisie). Si cela le fait se heurter à un mur, il reste sur place (ne bouge pas).

---

### **Questions :**

**Q1.** Implémentez l'algorithme d'**itération de valeur** pour le MDP correspondant. Affichez la politique calculée à chaque itération en utilisant, par exemple, les caractères `'v'`, `'<'`, `'>'`, `'^'`. Affichez également le **nombre d'itérations nécessaires pour converger**. Utilisez les valeurs **γ = 0.99** et **ϵ = 0.01**.  

À la fin du calcul, affichez également les utilités calculées.

---

**Q2.** Expérimentez avec d'autres récompenses. Essayez en particulier de faire varier la récompense des cases "normales".  
- Que se passe-t-il lorsqu'elle est **positive** ?  
- Et lorsqu'elle est beaucoup plus négative que **-0.04** (par exemple **-2**) ?  
- Pouvez-vous trouver des situations intermédiaires intéressantes ?

---

**Q3.** Implémentez l'algorithme d'**itération de politique** pour le MDP correspondant. Utilisez une version simplifiée de la fonction écrite pour la question Q1 afin de calculer les utilités des politiques jusqu'à **ϵ**.  

Affichez la politique calculée à chaque itération et le **nombre d'itérations nécessaires pour converger**. Comparez avec l'itération de valeur.

---

**Q4.** Implémentez l'algorithme de **Q-learning** (apprentissage par renforcement), en utilisant une politique d'exploration **ϵ-greedy** (rappelez-vous que **ϵ** n'a pas le même rôle que dans les questions précédentes ici).

---

**Q5.** Supposons que nous commençons dans la case en bas à droite de l'environnement, et calculez la meilleure stratégie selon l'algorithme de la question Q4. Utilisez les paramètres suivants :  
- **ϵ = 0.1**,  
- **α = 0.05**,  
- **γ = 0.99**,  
- et **10 000 exécutions**.
