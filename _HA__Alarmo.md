# Guide Utilisateur Alarmo

Alarmo est le système d'alarme utilisé dans Home Assistant.

Il s'appuie sur les capteurs Zigbee installés dans la maison.

---

# Fonctionnement général

Lorsque l'alarme est activée :

- les portes sont surveillées
- les ouvertures sont détectées
- une alerte peut être déclenchée

Lorsque l'alarme est désactivée :

- les ouvertures restent visibles
- aucune alerte n'est déclenchée

Exemple de vue Alarmo
![image Alarmo Page d'accueil](/images/alarmo_page_accueil.png)

---

# Etats de l'alarme

## Désarmée

Mode normal.

Aucune surveillance active.

---

## Armement total

Protection complète de la maison.

A utiliser lorsque personne n'est présent.

---

## Armement nuit

Protection partielle.

Permet généralement de dormir tout en gardant certaines zones protégées.

Selon la configuration installée.

---

# Armer l'alarme

1. Ouvrir Home Assistant
2. Ouvrir la carte Alarmo
3. Sélectionner le mode souhaité
4. Saisir le code si demandé

L'armement démarre alors.

---

# Délai de sortie

Après l'armement :

Exemple :

60 secondes

Pendant ce délai :

- quitter la maison
- fermer les portes

Aucune alarme n'est déclenchée pendant cette période.

---

# Délai d'entrée

Lors du retour :

Exemple :

30 secondes

Le compte à rebours démarre.

Il faut désarmer avant la fin du délai.

---

# Désarmer

1. Ouvrir Home Assistant
2. Carte Alarmo
3. Saisir le code
4. Désarmer

L'alarme repasse immédiatement en mode inactif.

---

# Pourquoi l'alarme refuse de s'armer ?

Causes fréquentes :

- porte ouverte
- capteur indisponible
- problème de communication Zigbee

Vérifier les messages affichés.

---

# Déclenchement d'alarme

Un déclenchement survient lorsqu'un capteur protégé détecte une intrusion.

Exemple :

- une porte est ouverte alors que l'alarme est armée

Le système :

- change d'état
- conserve un historique
- envoie éventuellement une notification

---

# Historique des événements

Permet de voir :

- heure d'armement
- heure de désarmement
- capteur déclencheur
- utilisateur concerné

Utile pour comprendre un incident.

---

# Test mensuel recommandé

Une fois par mois :

1. Armer l'alarme
2. Attendre la fin du délai
3. Tester une ouverture
4. Vérifier les notifications
5. Désarmer

Cette vérification prend quelques minutes.

---

# Bonnes pratiques

✅ Toujours fermer les ouvertures avant armement

✅ Vérifier les piles des capteurs

✅ Contrôler les notifications reçues

❌ Communiquer son code à des personnes non autorisées

❌ Modifier les paramètres Alarmo sans assistance
