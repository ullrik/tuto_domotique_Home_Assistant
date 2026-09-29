# Guide d'utilisation de l'alarme Alarmo

Cette installation utilise Alarmo comme système d'alarme.

---

# 1. Principe général

L'alarme surveille :

- Les portes équipées de capteurs
- Les futurs détecteurs éventuellement ajoutés

Si une ouverture est détectée alors que l'alarme est active :

- Une alerte est déclenchée
- Une notification est envoyée

---

# 2. États de l'alarme

L'alarme peut être dans plusieurs états.

## Désarmée

Aucune surveillance.

Les ouvertures de porte sont simplement affichées.

## Armement total

Protection complète de l'habitation.

Toutes les zones configurées sont surveillées.

Utiliser ce mode lorsque la maison est vide.

## Armement partiel (si configuré)

Certaines zones sont surveillées.

Exemple :

- Rez-de-chaussée surveillé
- Étage libre d'accès

Utiliser ce mode la nuit.

---

# 3. Armer l'alarme

Depuis Home Assistant :

1. Ouvrir le tableau de bord
2. Cliquer sur l'alarme
3. Choisir le mode souhaité
4. Saisir le code si demandé

Un délai de sortie peut être appliqué.

Pendant ce délai :

- Quitter le logement
- Fermer les portes

---

# 4. Désarmer l'alarme

1. Ouvrir Home Assistant
2. Accéder à la carte Alarme
3. Saisir le code
4. Désarmer

---

# 5. Déclenchement de l'alarme

Un déclenchement peut survenir lorsqu'une porte protégée est ouverte.

Le système peut :

- Envoyer une notification
- Afficher une alerte
- Déclencher d'autres actions configurées

---

# 6. Comprendre les délais

## Délai de sortie

Temps accordé pour quitter le logement après l'activation.

Exemple :

60 secondes.

## Délai d'entrée

Temps accordé pour désarmer après être entré.

Exemple :

30 secondes.

---

# 7. Vérifications avant départ

Avant d'activer l'alarme :

- Vérifier que toutes les portes sont fermées
- Vérifier qu'aucun capteur ne signale une anomalie

---

# 8. Changer le code

Si cette fonctionnalité est configurée :

1. Accéder aux paramètres Alarmo
2. Modifier le code utilisateur

Choisir un code facile à retenir mais difficile à deviner.

Éviter :

- 0000
- 1234
- année de naissance

---

# 9. Que faire en cas d'alerte ?

Si l'alerte est attendue :

1. Désarmer l'alarme
2. Vérifier le capteur concerné

Si l'alerte n'est pas attendue :

1. Vérifier les ouvertures
2. Vérifier les notifications reçues
3. Contrôler l'état des capteurs

---

# 10. Entretien

Une fois par mois :

- Vérifier l'état des capteurs
- Contrôler le niveau des piles
- Effectuer un test d'armement

Une fois par an :

- Vérifier tous les équipements Zigbee
- Tester chaque ouverture protégée

---
