🌐 [English](README.md) · [Español](README.es.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Português](README.pt.md) · [日本語](README.ja.md)

# 📺 Outil de Recherche YouTube

Un outil web pour rechercher des vidéos et des lives YouTube en ordre chronologique réel avec votre propre clé API. Sans connexion requise — collez simplement votre clé et recherchez.

## **Outil de Recherche YouTube :** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutoriel clé API :** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Fonctionnalités

* 🔍 Recherchez des vidéos ou des lives triés par les plus récents en premier
* 📅 Filtrer par date — choisissez un seul jour ou une plage personnalisée avec un calendrier interactif
* 🕐 Filtre horaire — limitez les résultats à une fenêtre horaire spécifique (convertit automatiquement votre fuseau horaire en UTC)
* 🚫 Filtrer les Shorts — masque les vidéos contenant des hashtags (`#`) dans leur titre ou description
* ⏱️ Filtre de durée — en mode Vidéos, filtrez par Court (<4 min), Moyen (4–20 min) ou Long (20+ min)
* 🎨 8 thèmes de couleur — Violet, Cyan, Émeraude, Rose, Ambre, Bleu, Pink et Lime
* 💾 Clé API et thème de couleur sauvegardés automatiquement dans votre navigateur
* ✨ Fond de particules animées
* 🕒 Affiche le temps écoulé pour chaque résultat
* 🖱️ Cliquez sur n'importe quel résultat pour ouvrir la vidéo directement
* ⭐ Mettez en favori n'importe quelle vidéo en un clic — les favoris persistent entre les sessions
* 📋 Ajoutez des notes à n'importe quelle vidéo — cliquez sur le bouton Notes d'une carte pour ouvrir une zone de texte, sauvegardée automatiquement
* 📄 Exportez votre session complète en fichier `.md` — inclut tous les résultats de chaque recherche effectuée, avec les URLs, liens de miniatures, favoris et notes, sans quota supplémentaire

> **Note :** Le mode Lives est désactivé lorsque le filtre de date est actif. Le filtre de durée n'est disponible qu'en mode Vidéos.

---

## 🔑 Comment obtenir une clé API YouTube

1. Ouvrez un nouvel onglet, allez sur [Gmail](https://mail.google.com) et connectez-vous à votre compte Google
2. Accédez à [console.cloud.google.com](https://console.cloud.google.com)
3. Acceptez les **Conditions d'utilisation** et cliquez sur **J'accepte et je continue**
4. En haut à gauche, cliquez sur **Sélectionner un projet**, puis sur **Nouveau projet**
5. Donnez un nom à votre projet et cliquez sur **Créer** — attendez la fin
6. Ouvrez le **Menu de navigation** (trois barres en haut à gauche), allez dans **APIs et services → Bibliothèque**
7. Faites défiler jusqu'à **YouTube Data API v3** et cliquez dessus
8. Cliquez sur **Activer** et attendez l'activation complète
9. Sur le côté gauche, cliquez sur **Identifiants**
10. En haut, cliquez sur **Créer des identifiants → Clé API → Créer**
11. Une fois la clé générée, cliquez sur la **Clé API** pour ouvrir ses paramètres
12. Sous **Restrictions d'API**, cliquez sur **Restreindre la clé → Sélectionner les API**
    - Si YouTube Data API v3 n'apparaît pas immédiatement, actualisez la page
    - Sélectionnez **YouTube Data API v3** et cliquez sur **OK**
13. Cliquez sur **Enregistrer**
14. Cliquez sur **Afficher la clé**, puis copiez-la
15. Allez sur l'[Outil de Recherche YouTube](https://slotchy.github.io/YouTube-Search-Tool), collez votre clé et effectuez une recherche pour confirmer que ça fonctionne

> **Quota :** Le niveau gratuit fournit 10 000 unités/jour. Chaque recherche coûte ~100 unités (~100 recherches/jour gratuitement).

---

## 🚀 Utilisation

1. Collez votre clé API YouTube — sauvegardée automatiquement pour les visites futures
2. Choisissez **Vidéos** ou **En direct**
3. Tapez votre sujet de recherche
4. *(Optionnel)* Sélectionnez une **Durée de vidéo** pour filtrer (mode Vidéos uniquement)
5. *(Optionnel)* Cochez **Filtrer les Shorts** pour exclure les vidéos avec hashtags
6. *(Optionnel)* Activez **Filtrer par date** et sélectionnez un jour ou une plage dans le calendrier
7. *(Optionnel)* Si une date est sélectionnée, définissez une heure de **Début** et de **Fin**
8. Cliquez sur **Trouver les plus récents** (ou **Rechercher** avec le filtre de date actif)
9. Cliquez sur n'importe quelle carte de résultat pour ouvrir la vidéo
10. *(Optionnel)* Cliquez sur **☆ Favorite** sur n'importe quelle carte pour la sauvegarder en favori
11. *(Optionnel)* Cliquez sur **📋 Notes** pour ouvrir la zone de notes et taper une note
12. Cliquez sur **Export .MD** pour télécharger votre session complète en fichier Markdown
13. Utilisez les swatches de couleur à droite pour changer le thème — mémorisé entre les visites

---

## 📄 Export

Le bouton d'export apparaît automatiquement après la première recherche et accumule les résultats tout au long de la session.

Le fichier `.md` est organisé ainsi :

* **⭐ Favoris** — toutes les vidéos marquées d'une étoile, listées en premier
* **📝 Notes** — toutes les vidéos avec des notes attachées
* **Tous les résultats** — chaque résultat groupé par terme de recherche

Les favoris et les notes persistent dans votre navigateur entre les rechargements de page via `localStorage`.

---

## 🔒 Confidentialité

* Clé API stockée localement dans votre navigateur (`localStorage`) — jamais envoyée ailleurs que chez Google
* Thème de couleur, favoris et notes stockés localement
* Sans backend — tout le traitement se fait côté client
* Les seules requêtes externes sont vers la YouTube Data API v3 de Google

---

## 🛠️ Détails techniques

| Détail | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript pur — sans frameworks |
| Backend | Aucun — entièrement côté client |
| API | YouTube Data API v3 |
| Résultats | Jusqu'à 50 par recherche, triés par date |
| Filtre de date | Utilise les paramètres `publishedAfter` / `publishedBefore` |
| Filtre de durée | Utilise le paramètre `videoDuration` |
| Filtre Shorts | Côté client — supprime les résultats contenant `#` dans le titre ou la description |
| Thèmes | Propriétés CSS personnalisées échangées via JavaScript |
| Particules | Valeurs négatives d'`animation-delay` pour pré-remplir l'écran au chargement |
| Stockage | `localStorage` pour la clé API, le thème, les favoris et les notes |
| Export | Téléchargement Blob côté client — aucun appel API supplémentaire |
