# 📺 Outil de Recherche YouTube

Un outil web pour rechercher des vidéos et des live YouTube en ordre chronologique réel grâce à votre propre clé API YouTube. Aucune connexion requise — collez simplement votre clé et lancez la recherche.

## **Outil de Recherche YouTube :** https://slotchy.github.io/YouTube-Search-Tool

---

## ✨ Fonctionnalités

* 🔍 Recherchez des vidéos ou des lives triés par les plus récents en premier
* 📅 Filtrer par date — choisissez un jour précis ou une plage de dates personnalisée avec un calendrier interactif
* 🕐 Filtre horaire — affinez les résultats à une fenêtre temporelle spécifique dans une date sélectionnée (convertit automatiquement votre fuseau horaire local en UTC)
* 🚫 Filtrer les Shorts — masque les vidéos contenant des hashtags (`#`) dans leur titre ou description
* ⏱️ Filtre de durée — quand Vidéos est sélectionné, filtrez par Court (<4 min), Moyen (4–20 min) ou Long (20+ min)
* 🎨 8 thèmes de couleurs — Violet, Cyan, Émeraude, Rose, Ambre, Bleu, Pink et Citron vert via un panneau de nuances
* 💾 La clé API et le thème de couleur sont enregistrés automatiquement dans votre navigateur
* ✨ Fond de particules animées, pré-rempli au chargement
* 🕒 Affiche le temps écoulé pour chaque résultat
* 🖱️ Cliquez sur n'importe quel résultat pour ouvrir la vidéo directement

> **Remarque :** Le mode Live est désactivé quand le filtre de date est actif. Le filtre de durée n'est disponible qu'en mode Vidéos.

---

## 🔑 Comment obtenir une clé API YouTube

1. Rendez-vous sur [console.cloud.google.com](https://console.cloud.google.com)
2. Créez un nouveau projet ou sélectionnez-en un existant
3. Activez **YouTube Data API v3**
4. Naviguez vers **Identifiants → Créer des identifiants → Clé API**
5. Copiez votre clé API et collez-la dans l'outil

> **Quota :** Le niveau gratuit fournit 10 000 unités/jour. Chaque recherche coûte ~100 unités (~100 recherches/jour gratuitement).

---

## 🚀 Utilisation

1. Collez votre clé API YouTube — elle est sauvegardée automatiquement pour les visites futures
2. Choisissez **Vidéos** ou **Lives**
3. Saisissez votre sujet de recherche
4. *(Optionnel)* Sélectionnez une **Durée de vidéo** pour filtrer par durée (mode Vidéos uniquement)
5. *(Optionnel)* Cochez **Filtrer les Shorts** pour exclure les vidéos avec des hashtags dans leur titre ou description
6. *(Optionnel)* Activez **Filtrer par date** et sélectionnez un jour ou une plage sur le calendrier
7. *(Optionnel)* Si une date est sélectionnée, définissez une heure de **Début** et de **Fin** pour filtrer par heure de la journée
8. Cliquez sur **Trouver les plus récents** (ou **Rechercher** quand le filtre de date est actif)
9. Cliquez sur n'importe quelle carte de résultat pour ouvrir la vidéo
10. Utilisez les nuances de couleur à droite pour changer le thème — mémorisé entre les visites

---

## 🔒 Confidentialité

* La clé API est stockée localement dans votre navigateur (`localStorage`) — jamais envoyée nulle part sauf à Google
* La préférence de thème de couleur est stockée localement dans votre navigateur
* Aucun backend — tout le traitement se fait côté client
* Les seules requêtes externes sont adressées à l'API Google YouTube Data v3

---

## 🛠️ Détails techniques

| Détail | Informations |
|---|---|
| Stack | HTML, CSS, JavaScript pur — sans framework |
| Backend | Aucun — entièrement côté client |
| API | YouTube Data API v3 |
| Résultats | Jusqu'à 50, triés par date |
| Filtre de date | Utilise les paramètres API `publishedAfter` / `publishedBefore` |
| Filtre de durée | Utilise le paramètre API `videoDuration` (`short` / `medium` / `long`) |
| Filtre Shorts | Côté client — supprime tout résultat contenant `#` dans le titre ou la description |
| Thèmes | Propriétés CSS personnalisées (`var(--accent)`) échangées via JavaScript |
| Particules | Valeurs négatives d'`animation-delay` pour que les particules pré-remplissent l'écran au chargement |
| Stockage | `localStorage` pour la clé API et la préférence de thème |
