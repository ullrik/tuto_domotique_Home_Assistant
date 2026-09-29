# Guide Home Assistant - Automatisations et Notifications sur iPhone

## Introduction

Les automatisations sont l'un des éléments les plus puissants de Home Assistant. Elles permettent d'exécuter automatiquement des actions lorsqu'un événement se produit.

Quelques exemples :

- Envoyer une notification lorsqu'une porte s'ouvre.
- Allumer une lumière au coucher du soleil.
- Alerter lorsqu'un capteur de fuite détecte de l'eau.
- Recevoir une notification quand quelqu'un rentre à la maison.
- Être informé lorsqu'un appareil n'est plus alimenté.

Dans ce guide, nous allons créer une automatisation simple qui envoie une notification sur l'application Home Assistant installée sur un iPhone.

---

# Prérequis

Avant de commencer :

✅ Home Assistant fonctionne correctement.

✅ L'application Home Assistant est installée sur votre iPhone/Android.

✅ Vous êtes connecté à votre instance Home Assistant depuis l'application.

✅ L'application apparaît dans :

**Paramètres → Appareils et Services → Mobile App**

Vous devez y voir un appareil correspondant à votre iPhone/Android.

---

# Accès aux automatisations

Aller dans :
**Paramètres → Automatisations et scènes**

# Comprendre le principe d'une automatisation

Une automatisation est composée de trois parties :

## 1. Déclencheur (Trigger)

L'événement qui lance l'automatisation.

Exemples :

- Ouverture d'une porte
- Changement d'état d'un capteur
- Heure précise
- Lever ou coucher du soleil

## 2. Conditions (facultatif)

Des critères supplémentaires à respecter.

Exemples :

- Seulement la nuit
- Seulement lorsque personne n'est à la maison
- Seulement si l'alarme est activée

## 3. Actions

Ce que Home Assistant doit faire.

Exemples :

- Envoyer une notification
- Allumer une lampe
- Jouer un son
- Exécuter un script

---

# Identifier le service de notification de votre iPhone/Android

Une fois l'application configurée, Home Assistant crée automatiquement un service.

Pour le retrouver :

**Paramètres → Outils de développement → Actions**

Cherchez :
```text
notify.mobile_app_mon_smartphone
```

---

# Exemple

## Exemple 1 : Notification de test
<details>
<summary>Afficher le détail</summary>
  
Créer une nouvelle automatisation :

Paramètres → Automatisations et scènes → <strong>+</strong> Créer une automatisation

Choisir : 

**Créer une automatisation vide**

YAML :
```text
alias: Test notification smartphone
description: ""
trigger:
  - platform: time
    at: "20:00:00"

condition: []

action:
  - service: notify.mobile_app_mon_smartphone
    data:
      title: "Home Assistant"
      message: "Ceci est un test de notification."

mode: single
```

Résultat :
À 20h00, une notification apparaît sur l'iPhone.
</details>

## Exemple 2 : Notification lors de l'ouverture d'une porte
<details>
<summary>Afficher le détail</summary>
  
Supposons que votre capteur Zigbee soit :
```
binary_sensor.porte_entree_contact
```

Choisir : 

**Créer une automatisation vide**

YAML :
```text
alias: Alerte ouverture porte
description: ""

trigger:
  - platform: state
    entity_id: binary_sensor.porte_entree_contact
    to: "on"

condition: []

action:
  - service: notify.mobile_app_mon_smartphone
    data:
      title: "🚪 Porte d'entrée"
      message: "La porte d'entrée vient d'être ouverte."

mode: single
```

Résultat :
A l'ouverture de la porte (en question), une notification apparaît sur l'iPhone.
</details>

## Exemple 3 : Notification uniquement lorsqu'il n'y a personne
<details>
<summary>Afficher le détail</summary>
  
Supposons :
```
binary_sensor.porte_entree_contact
person.martin
```

Choisir : 

**Créer une automatisation vide**

YAML :
```text
alias: Porte ouverte en votre absence

trigger:
  - platform: state
    entity_id: binary_sensor.porte_entree_contact
    to: "on"

condition:
  - condition: state
    entity_id: person.martin
    state: "not_home"

action:
  - service: notify.mobile_app_mon_smartphone
    data:
      title: "⚠️ Alerte"
      message: "La porte d'entrée a été ouverte alors que vous êtes absent."

mode: single
```

Résultat :
A l'ouverture de la porte (en question) et que la personne n'est pas présente au domicile, une notification apparaît sur l'iPhone.
</details>

## Tester une automatisation créée
<details>
<summary>Afficher le détail</summary>

Soit sur la ligne de l'automatisation, soir dans une automatisation :

Cliquer sur les 3 petits points ( ⋮ ) > Exécuter les actions

Résultat :
La partie Déclencheur (Trigger) et Conditions (facultatif) sont ignorés et la partie Actions est exécutée.
</details>

## Tester une notification sans créer d'automatisation
<details>
<summary>Afficher le détail</summary>

Aller dans :

Outils de développement → Actions

Service :
```
notify.mobile_app_mon_smartphone
```

Données : 
```
message: "Message de test"
title: "Home Assistant"
```

Puis cliquer :

**Exécuter l'action**

Si vous recevez la notification, tout est correctement configuré.
</details>

