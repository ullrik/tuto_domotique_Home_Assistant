# Guide Utilisateur Zigbee2MQTT

Zigbee2MQTT permet à Home Assistant de communiquer avec tous les équipements Zigbee.

C'est grâce à lui que les capteurs fonctionnent.

---

# Qu'est-ce qu'un appareil Zigbee ?

Les appareils Zigbee sont :

- capteurs de porte
- détecteurs de mouvement
- prises connectées
- boutons
- thermostats

Ils communiquent sans fil avec la clé Zigbee branchée au Raspberry Pi.

---

# Fonctionnement du réseau Zigbee

Le réseau Zigbee ressemble à une toile.

Chaque équipement communique :

- directement avec la clé Zigbee
- ou via d'autres équipements Zigbee

Cela permet une bonne portée dans la maison.

---

# Accéder à Zigbee2MQTT

Depuis Home Assistant :

Paramètres

→ Modules complémentaires

→ Zigbee2MQTT

→ Ouvrir l'interface

---

# Ecran principal

L'écran principal affiche :

- nombre d'appareils
- état du réseau
- qualité des connexions
- derniers messages reçus

---

# Comprendre les informations affichées

## Online

L'appareil communique correctement.

---

## Offline

L'appareil ne répond plus.

Causes possibles :

- pile vide
- appareil déplacé
- problème radio

---

## Batterie

Pourcentage restant.

Exemple :

- 100 %
- 80 %
- 50 %
- 10 %

En dessous de 20 %, il est conseillé de prévoir le remplacement.

---

## Link Quality (LQI)

Indique la qualité de la communication radio.

Valeurs typiques :

- supérieur à 100 : excellent
- 50 à 100 : correct
- inférieur à 50 : à surveiller

---

# Exemple : capteur de porte

Un capteur de porte affiche généralement :

- Ouvert
- Fermé
- Batterie
- Qualité radio

Exemple :

Porte Garage

Etat : Fermé

Batterie : 78 %

LQI : 115

Tout fonctionne correctement.

---

# Voir la carte réseau Zigbee

La carte réseau permet de visualiser :

- la clé Zigbee
- les capteurs
- les liaisons radio

C'est très utile pour diagnostiquer des problèmes de portée.

---

# Que faire si un capteur devient indisponible ?

Attendre quelques minutes.

Puis vérifier :

1. Batterie
2. Distance avec la clé Zigbee
3. Présence d'obstacles importants

Si le problème persiste :

Contacter l'administrateur.

---

# Changer une pile

1. Ouvrir le capteur
2. Remplacer la pile identique
3. Refermer le capteur

Après quelques minutes :

- l'état redevient normal
- la batterie se met à jour

---

# Ne jamais faire

❌ Supprimer un appareil

❌ Réinitialiser un équipement

❌ Modifier les paramètres avancés

❌ Changer le canal Zigbee

---

# Diagnostic simple

Si un capteur ne fonctionne plus :

Vérifier :

✅ Batterie

✅ Etat Online

✅ Historique

✅ Notifications

Si le problème dure plus d'une journée :

Contacter l'administrateur.

---

# Vérification mensuelle

Une fois par mois :

- vérifier les niveaux de batterie
- vérifier qu'aucun appareil n'est Offline
- consulter la carte réseau

Cela permet de prévenir les pannes avant qu'elles ne surviennent.
