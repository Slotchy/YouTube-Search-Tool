🌐 [English](README.md) · [Español](README.es.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Português](README.pt.md) · [日本語](README.ja.md)

# 📺 YouTube Search Tool

Un outil web pour rechercher des vidéos et des livestreams YouTube en ordre chronologique réel en utilisant votre propre clé API YouTube. Aucune connexion requise — collez simplement votre clé et recherchez.

## **YouTube Search Tool:** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutoriel Clé API:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Fonctionnalités

* 🔍 Recherchez des vidéos ou des livestreams triés par les plus récents en premier
* 📅 Filtrer par date — choisissez un seul jour ou une plage de dates personnalisée à l'aide d'un calendrier interactif
* 🕐 Filtre horaire — restreignez les résultats à une fenêtre de temps spécifique dans la date sélectionnée (convertit automatiquement votre fuseau horaire local en UTC)
* 🚫 Filtrer les Shorts — masque les vidéos contenant des hashtags (`#`) dans leur titre ou description
* ⏱️ Filtre de durée de vidéo — lorsque Videos est sélectionné, filtrez par Court (<4 min), Moyen (4–20 min) ou Long (20+ min)
* 🎨 8 thèmes de couleurs — Violet, Cyan, Émeraude, Rose, Ambre, Bleu, Pink et Lime via un panneau d'échantillons
* 💾 Clé API et thème de couleur enregistrés automatiquement dans votre navigateur
* ✨ Fond de particules animées, pré-rempli au chargement
* 🕒 Affiche le temps écoulé depuis la publication de chaque résultat
* 🖱️ Cliquez sur n'importe quel résultat pour ouvrir la vidéo directement

> **Remarque:** Le mode Livestreams est désactivé lorsque le filtre de date est actif. Le filtre de durée de vidéo n'est disponible qu'en mode Videos.

---

## 🔑 Comment Obtenir une Clé API YouTube

1. Ouvrez un nouvel onglet, allez sur [Gmail](https://mail.google.com) et connectez-vous à votre compte Google
2. Naviguez vers [console.cloud.google.com](https://console.cloud.google.com)
3. Lorsque vous y êtes invité, acceptez les **Conditions d'utilisation** et cliquez sur **J'accepte et je continue**
4. En haut à gauche de la page, cliquez sur **Sélectionner un projet**, puis en haut à droite de cette fenêtre cliquez sur **Nouveau projet**
5. Donnez un nom à votre projet et cliquez sur **Créer** — attendez la fin de la création
6. Ouvrez le **Menu de navigation** (les trois barres en haut à gauche), faites défiler vers le bas jusqu'à **API et services** et cliquez sur **Bibliothèque**
7. Faites défiler vers le bas jusqu'à trouver **YouTube Data API v3** et cliquez dessus
8. Cliquez sur **Activer** et attendez l'activation complète
9. Sur le côté gauche, cliquez sur **Identifiants**
10. En haut, cliquez sur **Créer des identifiants → Clé API**, puis cliquez sur **Créer**
11. Une fois votre clé générée, cliquez sur la **Clé API** pour ouvrir ses paramètres
12. Sous **Restrictions d'API**, cliquez sur **Restreindre la clé**, puis cliquez sur **Sélectionner les API**
    - Si YouTube Data API v3 n'apparaît pas immédiatement, actualisez la page
    - Faites défiler vers le bas, sélectionnez **YouTube Data API v3** et cliquez sur **OK**
13. Cliquez sur **Enregistrer**
14. Cliquez sur **Afficher la clé**, puis copiez votre clé
15. Rendez-vous sur le [YouTube Search Tool](https://slotchy.github.io/YouTube-Search-Tool), collez votre clé et effectuez une recherche pour confirmer qu'elle fonctionne

> **Quota:** Le niveau gratuit fournit 10 000 unités/jour. Chaque recherche coûte ~100 unités (~100 recherches/jour gratuitement).

---

## 🚀 Utilisation

1. Collez votre clé API YouTube — elle est sauvegardée automatiquement pour les visites futures
2. Choisissez **Videos** ou **Livestreams**
3. Tapez votre sujet de recherche
4. *(Optionnel)* Sélectionnez une **Durée de vidéo** pour filtrer par durée (mode Videos uniquement)
5. *(Optionnel)* Cochez **Filtrer les Shorts** pour exclure les vidéos avec des hashtags dans leur titre ou description
6. *(Optionnel)* Activez **Filtrer par date** et sélectionnez un jour ou une plage de dates sur le calendrier
7. *(Optionnel)* Si une date est sélectionnée, définissez une heure de **Début** et de **Fin** pour filtrer par heure de la journée
8. Cliquez sur **Trouver les plus récents** (ou **Rechercher** lorsque le filtre de date est activé)
9. Cliquez sur n'importe quelle carte de résultat pour ouvrir la vidéo
10. Utilisez les échantillons de couleur à droite pour changer le thème d'accentuation — mémorisé entre les visites

---

## 🔒 Confidentialité

* Clé API stockée localement dans votre navigateur (`localStorage`) — jamais envoyée nulle part sauf à Google
* Préférence de thème de couleur stockée localement dans votre navigateur
* Pas de backend — tout le traitement se fait côté client
* Les seules requêtes externes sont vers l'API Google YouTube Data v3

---

## 🛠️ Détails Techniques

| Détail | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript pur — pas de frameworks |
| Backend | Aucun — entièrement côté client |
| API | YouTube Data API v3 |
| Résultats | Jusqu'à 50, triés par date |
| Filtre de date | Utilise les paramètres `publishedAfter` / `publishedBefore` de l'API |
| Filtre de durée | Utilise le paramètre `videoDuration` de l'API (`short` / `medium` / `long`) |
| Filtre Shorts | Côté client — supprime tout résultat contenant `#` dans le titre ou la description |
| Thèmes | Propriétés CSS personnalisées (`var(--accent)`) échangées via JavaScript |
| Particules | Valeurs négatives d'`animation-delay` pour que les particules se pré-remplissent au chargement |
| Stockage | `localStorage` pour la clé API et la préférence de thème |
