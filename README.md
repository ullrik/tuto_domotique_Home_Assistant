# Guide d'utilisation Home Assistant

Bienvenue !

Cette installation permet de superviser la maison grâce à Home Assistant et à différents équipements connectés.

---

# 1. À quoi sert cette installation ?

Le Raspberry Pi exécute Home Assistant, une plateforme de domotique qui centralise :

- Les capteurs de porte
- Les équipements Zigbee
- L'alarme (Alarmo)
- Les futurs équipements connectés

L'installation fonctionne localement dans la maison.

---

# 2. Accéder à Home Assistant

Depuis un ordinateur :

http://homeassistant.local:8123

Ou utilisez l'adresse IP communiquée lors de l'installation.

Depuis un smartphone :

- Installer l'application Home Assistant
- Android :
  - Google Play Store
- iPhone :
  - App Store

Se connecter avec :

- Nom d'utilisateur : XXXXX
- Mot de passe : XXXXX

---

# 3. Tableau de bord principal

Le tableau de bord permet de consulter :

- L'état des portes
- Les équipements Zigbee
- L'état de l'alarme
- Les informations générales de la maison

---

# 4. Comprendre les capteurs de porte

Les capteurs surveillent l'ouverture et la fermeture des portes.

États possibles :

- Fermé
- Ouvert
- Indisponible (problème de communication ou pile faible)

Si un capteur apparaît souvent indisponible :

- Vérifier la pile
- Vérifier qu'il n'a pas été déplacé

---

# 5. Recevoir des notifications

Selon la configuration :

- Notification sur smartphone
- E-mail
- Autres alertes

Les notifications permettent d'être informé rapidement en cas d'événement important.

---

# 6. En cas de panne

Vérifier dans l'ordre :

1. Alimentation du Raspberry Pi
2. Connexion Internet
3. Réseau Wi-Fi
4. Présence du disque dur externe

Redémarrer le Raspberry Pi uniquement si nécessaire.

---

# 7. Bonnes pratiques

Ne jamais :

- Débrancher brutalement le Raspberry Pi
- Retirer le disque dur à chaud
- Réinitialiser un équipement Zigbee sans conseil préalable

Toujours :

- Utiliser l'arrêt/reboot depuis Home Assistant
- Maintenir le Raspberry Pi alimenté en permanence

---

# 8. Sauvegardes

Le système réalise des sauvegardes de sa configuration.

Ces sauvegardes permettent de restaurer l'installation en cas de problème matériel.

---

# 9. Demander de l'aide

En cas de problème :

Décrire :

- Le problème rencontré
- Les messages affichés
- La date et l'heure de l'incident

Une capture d'écran est toujours utile.
