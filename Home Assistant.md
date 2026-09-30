# Guide Utilisateur Home Assistant

Bienvenue !

Cette installation domotique permet de surveiller et gérer différents équipements de la maison depuis un ordinateur ou un smartphone.

---

# Architecture de l'installation

L'installation est composée de :

- Un Raspberry Pi
- Un disque dur externe
- Home Assistant OS
- Une clé Zigbee
- Zigbee2MQTT
- Plusieurs capteurs Zigbee

Le Raspberry Pi fonctionne 24h/24.

⚠️ Ne jamais débrancher le Raspberry Pi ou le disque dur sans raison.

---

# À quoi sert Home Assistant ?

Home Assistant centralise toute la domotique de la maison :

- Surveillance des portes
- Gestion de l'alarme
- Consultation des capteurs
- Réception des notifications
- Historique des événements

C'est le "cerveau" de toute l'installation.

---

# Accès depuis un ordinateur

|  |  |  |
| :--- | :--- | :--- |
| Adresse locale |  | http://homeassistant.local:8123/ |
| Exemple locale | http://ADRESSE_IP_DU_RASPBERRY:8123 | http://192.168.1.50:8123/ |
| Exemple Web | https://NOM_DE_DOMAINE.XXX | https://nom_de_domaine.fr |

---

# Accès depuis un téléphone

Installer l'application :

- Home Assistant Android
- Home Assistant iPhone

Puis se connecter avec :

- Identifiant
- Mot de passe

fournis lors de l'installation.

---

# Tableau de bord

Le tableau de bord affiche :

## Etat de l'alarme

Permet :

- d'armer
- de désarmer
- de voir l'état actuel

---

## Capteurs de portes

Etat possible :

✅ Fermé

🚪 Ouvert

⚠️ Indisponible

---

## Historique

Permet de retrouver :

- les ouvertures
- les fermetures
- les déclenchements d'alarme
- les notifications

---

# Comprendre les couleurs

Vert :

- fonctionnement normal

Orange :

- attention requise

Rouge :

- alarme ou anomalie

Gris :

- appareil hors ligne

---

# Vérification quotidienne

Une vérification rapide consiste à regarder :

- que l'alarme soit dans le bon état
- qu'aucun capteur ne soit indisponible
- qu'aucune pile ne soit faible

Durée : moins d'une minute.

---

# Remplacement d'une pile

Si Home Assistant indique une pile faible :

1. Ouvrir le capteur
2. Remplacer la pile par le même modèle
3. Refermer correctement

Attendre quelques minutes.

Le niveau se met généralement à jour automatiquement.

---

# Que faire si le système n'est plus accessible ?

Vérifier dans l'ordre :

1. Internet fonctionne-t-il ?
2. Le Wi-Fi fonctionne-t-il ?
3. Le Raspberry Pi est-il allumé ?
4. Le disque dur est-il branché ?

Si tout semble normal mais que Home Assistant reste inaccessible :

Contacter l'administrateur.

---

# Redémarrage de Home Assistant

Uniquement si demandé.

Paramètres → Système → Redémarrer

Ne jamais couper l'alimentation directement.

---

# Sauvegardes

Le système réalise des sauvegardes régulières.

Ces sauvegardes permettent de restaurer l'installation en cas de panne.

Aucune action n'est nécessaire au quotidien.

---

# Bonnes pratiques

✅ Laisser l'installation allumée en permanence

✅ Vérifier les notifications reçues

✅ Remplacer rapidement une pile faible

❌ Débrancher la clé Zigbee

❌ Réinitialiser un capteur

❌ Modifier la configuration sans connaître l'impact

---

# Quand demander de l'aide ?

Si :

- plusieurs capteurs deviennent indisponibles
- l'alarme ne fonctionne plus
- Home Assistant ne démarre plus
- un message d'erreur apparaît régulièrement

Faire une capture d'écran si possible.
``
