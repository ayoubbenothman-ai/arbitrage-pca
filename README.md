## Données
 
25 actions US (5 secteurs, 5 actions chacun), prix journaliers de 2010 à 2019 avec yfinance. Ça fait 2264 jours de rendements.
 
## Où on en est
 
Ce qui est dans le notebook pour l'instant :
- récup des données + rendements
- un peu d'exploration (graphes, autocorrélations, histos)
- matrice de corrélation + valeurs/vecteurs propres
- Marchenko-Pastur : 3 valeurs propres au-dessus du seuil (~1,22), donc on part sur k = 3
Ce qu'il reste à faire :
1. débruiter la matrice (Ledoit-Wolf et clipping)
2. construire les eigenportfolios
3. refaire la PCA sur fenêtre glissante
4. estimer les beta (OLS glissant, puis Kalman si on a le temps) et récupérer les résidus
5. résidus cumulés -> Ornstein-Uhlenbeck -> s-scores
6. backtest (d'abord sans frais, puis avec)
Attention : à partir de l'étape 3, tout doit être calculé avec les données passées uniquement, sinon le backtest triche. Plus de détails à la fin du notebook.
 
## Si vous lancez le notebook dans google colabn ajouter ce bloc au début pour installer les librairies
 
```bash
pip install yfinance numpy pandas matplotlib seaborn statsmodels
```
 
Puis Run All.

 
