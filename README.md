8. Analyse critique
Limites et biais

Biais de survie : les cinq titres sont des gagnantes actuelles, choisies après coup. Cela gonfle l'alpha (0,76 % par mois) : un investisseur de 2015 n'aurait pas pu les connaître à l'avance.
Concentration : cinq grandes valeurs technologiques, donc un risque propre au portefeuille important (erreurs de 3 à 5 % certains mois, section 7.3) et des conclusions non généralisables au marché.
Peu de données de test : 33 mois. Le R² hors échantillon est bruité, et les intervalles bootstrap du CAPM et de Fama-French se chevauchent. Le gain des trois facteurs repose surtout sur le test F, calculé sur les 132 mois.
Modèle explicatif, pas prédictif : les facteurs du mois sont connus après coup. Le modèle explique le rendement d'un mois, il ne le prévoit pas. De plus, Mkt-RF contient en partie les cinq titres.
Coefficients non constants : le bêta SMB passe de −0,53 (2015-2019) à −0,28 (2020-2025). Trois facteurs seulement : momentum, rentabilité et investissement sont absents. Frais de transaction ignorés ; données Yahoo non officielles et sujettes à révision.
Pistes d'amélioration concrètes

Élargir le portefeuille à 20 à 30 titres, en incluant des entreprises disparues ou en déclin (base CRSP), pour réduire le biais de survie et le risque spécifique.
Ajouter le facteur momentum (F-F_Momentum_Factor) ou passer au modèle à 5 facteurs (F-F_Research_Data_5_Factors_2x3) et comparer les R² ajustés.
Estimer des bêtas variables dans le temps (fenêtre glissante de 36 mois) et calculer des erreurs-types par sous-période pour tester la stabilité.
Remplacer le découpage unique par une validation à fenêtre croissante et un bootstrap par blocs, plus adapté à des séries temporelles autocorrélées.
9. Conclusion
Oui : pour ce portefeuille, le modèle à trois facteurs explique mieux les rendements que le CAPM seul. Son R² hors échantillon est de 0,73 contre 0,57, et le test F de SMB et HML donne p < 0,0001. L'objectif mesurable de la section 1 est atteint. Le portefeuille est exposé au marché (bêta 1,15), aux grandes capitalisations (SMB −0,36) et à la croissance (HML −0,56), et son alpha de 0,76 % par mois, intervalle [0,29 ; 1,24], est significatif. Ce résultat reste à nuancer : seuls 33 mois servent au test, et l'alpha est probablement gonflé par le biais de survie, donc il ne prouve pas une compétence.

10. Références et reproduction
Sources de données

Kenneth R. French, Data Library (fichier F-F_Research_Data_Factors), Tuck School of Business, Dartmouth : https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html. Extraction : 17 novembre 2026.
Yahoo Finance, cours mensuels ajustés, via la bibliothèque yfinance : https://finance.yahoo.com et https://github.com/ranaroussi/yfinance. Extraction : 17 novembre 2026.
Références scientifiques et logicielles

Fama, E. F., French, K. R. (1993). Common risk factors in the returns on stocks and bonds. Journal of Financial Economics, 33(1), 3-56.
Sharpe, W. F. (1964). Capital asset prices: a theory of market equilibrium under conditions of risk. The Journal of Finance, 19(3), 425-442.
Newey, W. K., West, K. D. (1987). A simple, positive semi-definite, heteroskedasticity and autocorrelation consistent covariance matrix. Econometrica, 55(3), 703-708.
Pedregosa, F. et al. (2011). Scikit-learn: machine learning in Python. Journal of Machine Learning Research, 12, 2825-2830.
Seabold, S., Perktold, J. (2010). Statsmodels: econometric and statistical modeling with Python. Proceedings of the 9th Python in Science Conference.
Support du cours : notebook « 29 exemples Python, principaux algorithmes de Machine Learning » (annexe A), algorithme n° 1 (régression linéaire).
Déclaration des ressources externes et des outils d'IA
Date de la déclaration : 17 novembre 2026

Outil ou ressource	Version ou date	Usage précis	Parties concernées	Vérification effectuée
Claude (Anthropic)	Conversation du 17/11/2026	Assistance à l'écriture du code relatif aux modèles MCO et Ridge, à l'optimisation des hyperparamètres avec GridSearchCV et TimeSeriesSplit, au bootstrap, à l'importance par permutation et à l'analyse par sous-périodes. Assistance également à la rédaction de la présentation de l'algorithme et du protocole méthodologique.	Sections 5 à 7	Code exécuté dans Colab, sorties relues, chaque ligne expliquée ; paramètres modifiés pour tester l'effet.
Claude (Anthropic)	17/11/2026	Assistance à la rédaction de l'analyse critique, de la conclusion et de la liste des références bibliographiques.	Sections 8 à 10	Correction testée, sorties comparées avant et après.
Support du cours : notebook « TP : facteurs de risque d'un portefeuille »	Fourni par l'enseignant	Source de la démarche méthodologique et de certaines cellules de code, notamment le chargement des données Fama-French, la construction du portefeuille avec yfinance, les modèles MCO et les diagnostics, reprises ou adaptées dans le cadre du projet.	Sections 2 à 7	(À compléter selon les adaptations et vérifications effectuées.)
Support du cours : notebook « 29 exemples Python, principaux algorithmes » (annexe A)	Fourni par l'enseignant	Référence pour le choix des algorithmes n° 1 (régression linéaire) et n° 2 et 3 (Ridge et Lasso).	Sections 1 et 5	(À compléter selon les vérifications effectuées.)
Données : Kenneth R. French Data Library et Yahoo Finance (yfinance)	Extraites le 17/11/2026	Sources des données financières utilisées dans le projet, notamment pour la constitution de la base de données et la réalisation des analyses empiriques.	Sections 2 à 7	Dimensions, période d'observation et valeurs manquantes contrôlées (sections 2 et 3.2).
Précision sur l'utilisation des outils d'intelligence artificielle
L'utilisation de Claude (Anthropic) a été limitée à une assistance technique et rédactionnelle portant sur les sections 5 à 10 du projet.

Les propositions de code ont été destinées à être intégrées et exécutées dans Google Colab, tandis que les éléments rédactionnels ont été relus et adaptés au contenu du travail.

Les supports pédagogiques fournis par l'enseignant ainsi que les sources de données financières utilisées sont également mentionnés afin d'assurer la transparence sur les ressources mobilisées dans la réalisation du projet.

