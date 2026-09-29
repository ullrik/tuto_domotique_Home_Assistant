# Guide Home Assistant : créer et modifier un tableau de bord

Les tableaux de bord permettent d'afficher et de contrôler les équipements de la maison depuis Home Assistant.

Ils peuvent notamment afficher :

- les portes et fenêtres ouvertes ;
- les températures ;
- l'humidité ;
- l'état des lumières et des prises ;
- le niveau des batteries Zigbee ;
- les graphiques d'historique ;
- les caméras ;
- les alertes importantes.

Un tableau de bord est constitué de plusieurs éléments :

```text
Tableau de bord
├── Vue Accueil
│   ├── Section Sécurité
│   ├── Section Température
│   └── Section Éclairage
├── Vue Portes
├── Vue Batteries
└── Vue Maintenance
```

Une **vue** correspond à un onglet ou à une page.

Une **section** permet de regrouper les cartes par thème.

Une **carte** affiche une information ou permet de contrôler un équipement.

---

# 1. Accéder aux tableaux de bord

Dans Home Assistant, aller dans :

```text
Paramètres
→ Tableaux de bord
```

Cette page affiche les tableaux de bord disponibles.

Le tableau de bord principal est généralement accessible directement depuis le menu latéral de Home Assistant.

---

# 2. Créer un nouveau tableau de bord

Il est préférable de créer un tableau de bord personnalisé plutôt que de modifier directement le tableau de bord par défaut.

Aller dans :

```text
Paramètres
→ Tableaux de bord
→ Ajouter un tableau de bord
```

Renseigner les informations demandées.

Exemple :

```text
Titre : Maison
Icône : mdi:home
URL : maison
Afficher dans la barre latérale : Oui
```

Enregistrer le tableau de bord.

Le nouveau tableau de bord apparaît ensuite dans le menu latéral de Home Assistant.

---

# 3. Passer en mode modification

Ouvrir le tableau de bord à modifier.

Cliquer sur l'icône en forme de crayon située en haut à droite.

Le tableau de bord passe alors en mode modification.

Dans ce mode, il est possible de :

- créer une vue ;
- modifier une vue ;
- créer une section ;
- ajouter une carte ;
- déplacer une carte ;
- redimensionner une carte ;
- modifier une carte ;
- supprimer une carte.

Une fois les modifications terminées, cliquer sur :

```text
Terminé
```

---

# 4. Comprendre les vues

Une vue correspond à un onglet du tableau de bord.

Chaque vue peut représenter une pièce ou une catégorie.

Exemple d'organisation :

```text
🏠 Accueil
🚪 Portes et fenêtres
🌡️ Températures
💡 Éclairage
🔋 Batteries
⚙️ Maintenance
```

Pour un usage simple, il est préférable de ne pas créer trop de vues.

Les informations les plus importantes doivent rester accessibles depuis la vue d'accueil.

---

# 5. Ajouter une vue

Passer le tableau de bord en mode modification :

```text
Tableau de bord
→ Icône en forme de crayon
→ Ajouter une vue
```

Selon la version de Home Assistant, le bouton d'ajout peut prendre la forme d'un symbole `+`.

Renseigner les informations de la vue.

Exemple :

```text
Titre : Portes
Icône : mdi:door
Type de vue : Sections
```

Enregistrer la vue.

## Exemples d'icônes

```text
Accueil              mdi:home
Portes               mdi:door
Fenêtres             mdi:window-closed
Températures         mdi:thermometer
Éclairage            mdi:lightbulb
Batteries            mdi:battery
Sécurité             mdi:shield-home
Maintenance          mdi:tools
Zigbee               mdi:zigbee
```

Retrouver l'ensemble des icônes mdi sur ce lien : https://pictogrammers.com/library/mdi/

---

# 6. Choisir le type de vue

Home Assistant propose plusieurs types de vues.

## Vue Sections

La vue Sections organise les cartes dans une grille et permet de les regrouper dans différentes sections.

C'est le type recommandé pour créer un tableau de bord moderne, lisible et adapté aux smartphones.

Exemple :

```text
Accueil
├── Section Sécurité
├── Section Température
├── Section Éclairage
└── Section Informations
```

## Vue Maçonnerie

La vue Maçonnerie répartit automatiquement les cartes dans plusieurs colonnes en fonction de leur taille.

Elle est pratique pour les anciens tableaux de bord ou pour une disposition libre.

## Vue Panneau

La vue Panneau affiche une seule carte sur toute la largeur.

Elle peut être utile pour :

- une carte géographique ;
- une caméra ;
- une grande image ;
- un plan de maison ;
- un graphique occupant toute la page.

## Vue Barre latérale

La vue Barre latérale répartit les cartes dans deux colonnes :

- une colonne principale ;
- une colonne latérale plus petite.

---

# 7. Créer une section

Dans une vue de type Sections :

```text
Modifier le tableau de bord
→ Ajouter une section
```

Donner un titre à la section.

Exemples :

```text
Sécurité
Températures
Éclairage
Portes et fenêtres
Batteries
Maintenance
```

Une fois la section créée, des cartes peuvent être ajoutées à l'intérieur.

---

# 8. Ajouter une carte

Ouvrir la vue dans laquelle la carte doit être ajoutée.

Passer en mode modification :

```text
Icône en forme de crayon
→ Ajouter une carte
```

Dans une vue Sections, le bouton d'ajout se trouve généralement directement dans la section concernée.

Home Assistant permet d'ajouter une carte :

- en sélectionnant une entité ;
- en choisissant directement un type de carte ;
- en écrivant la configuration YAML.

---

# 9. La carte Tuile

La carte Tuile est particulièrement adaptée aux tableaux de bord récents.

Elle permet d'afficher rapidement :

- le nom de l'équipement ;
- son état ;
- son icône ;
- des boutons ou commandes supplémentaires.

## Exemple avec un capteur de porte

```yaml
type: tile
entity: binary_sensor.porte_entree_contact
name: Porte d'entrée
icon: mdi:door
```

## Exemple avec une température

```yaml
type: tile
entity: sensor.temperature_salon
name: Température du salon
icon: mdi:thermometer
```

## Exemple avec une lumière

```yaml
type: tile
entity: light.salon
name: Lumière du salon
icon: mdi:ceiling-light
```

Selon l'équipement, un appui sur l'icône peut permettre de le contrôler.

Un appui sur la carte ouvre généralement la fenêtre contenant les informations détaillées de l'entité.

---

# 10. La carte Entités

La carte Entités permet de regrouper plusieurs équipements dans une même carte.

## Exemple avec les portes et fenêtres

```yaml
type: entities
title: Portes et fenêtres
show_header_toggle: false
entities:
  - entity: binary_sensor.porte_entree_contact
    name: Porte d'entrée
  - entity: binary_sensor.fenetre_cuisine_contact
    name: Fenêtre de la cuisine
  - entity: binary_sensor.porte_garage_contact
    name: Porte du garage
```

## Exemple avec les températures

```yaml
type: entities
title: Températures
show_header_toggle: false
entities:
  - entity: sensor.temperature_salon
    name: Salon
  - entity: sensor.temperature_chambre
    name: Chambre
  - entity: sensor.temperature_cuisine
    name: Cuisine
```

## Exemple avec les batteries Zigbee

```yaml
type: entities
title: Batteries des capteurs
show_header_toggle: false
entities:
  - entity: sensor.porte_entree_battery
    name: Porte d'entrée
  - entity: sensor.fenetre_cuisine_battery
    name: Fenêtre de la cuisine
  - entity: sensor.detecteur_mouvement_battery
    name: Détecteur de mouvement
```

Les identifiants d'entités utilisés dans ces exemples doivent être remplacés par ceux de l'installation.

---

# 11. La carte Jauge

La carte Jauge permet de représenter visuellement une valeur.

Elle est adaptée pour :

- une température ;
- une humidité ;
- un niveau de batterie ;
- une consommation ;
- un espace disque.

## Exemple avec une température

```yaml
type: gauge
entity: sensor.temperature_salon
name: Température du salon
min: 0
max: 40
severity:
  green: 18
  yellow: 25
  red: 30
```

## Exemple avec une batterie

```yaml
type: gauge
entity: sensor.porte_entree_battery
name: Batterie porte d'entrée
min: 0
max: 100
severity:
  red: 0
  yellow: 20
  green: 50
```

---

# 12. La carte Graphique d'historique

La carte Graphique d'historique permet d'afficher l'évolution d'un ou plusieurs capteurs.

## Exemple avec la température et l'humidité

```yaml
type: history-graph
title: Salon sur les dernières 24 heures
hours_to_show: 24
entities:
  - entity: sensor.temperature_salon
    name: Température
  - entity: sensor.humidite_salon
    name: Humidité
```

Cette carte est utile pour vérifier :

- l'évolution de la température ;
- les changements d'humidité ;
- les ouvertures d'une porte ;
- les détections de mouvement ;
- le fonctionnement d'un équipement.

---

# 13. La carte Bouton

La carte Bouton permet de commander rapidement un équipement ou d'exécuter une action.

## Exemple pour éteindre une lumière

```yaml
type: button
name: Éteindre le salon
icon: mdi:lightbulb-off
tap_action:
  action: perform-action
  perform_action: light.turn_off
  target:
    entity_id: light.salon
```

## Exemple pour allumer une prise

```yaml
type: button
name: Allumer la prise
icon: mdi:power-socket-fr
tap_action:
  action: perform-action
  perform_action: switch.turn_on
  target:
    entity_id: switch.prise_salon
```

---

# 14. La carte Markdown

La carte Markdown permet d'afficher :

- un titre ;
- des consignes ;
- un message ;
- une valeur calculée ;
- l'état d'une entité ;
- la date et l'heure.

## Exemple simple

```yaml
type: markdown
content: |
  # Bienvenue

  Ce tableau de bord permet de surveiller les principaux équipements de la maison.
```

## Exemple avec des valeurs Home Assistant

```yaml
type: markdown
content: |
  # État de la maison

  Température du salon : **{{ states('sensor.temperature_salon') }} °C**

  Porte d'entrée : **{{ states('binary_sensor.porte_e**ree_contact') }}**

  Dernière actualisation : **{{ now().strftime('%d/%m/%Y à %H:%M') }}**
```

## Exemple avec un texte conditionnel

```yaml
type: markdown
content: |
  # Porte d'entrée

  {% if is_state('binary_sensor.porte_entree_contact', 'on') %}
  ⚠️ La porte d'entrée est ouverte.
  {% else %}
  ✅ La porte d'entrée est fermée.
  {% endif %}
```

---

# 15. Modifier une carte existante

Passer le tableau de bord en mode modification :

```text
Icône en forme de crayon
→ Sélectionner la carte
→ Modifier
```

Selon le type de carte, il est possible de modifier :

- le nom ;
- l'icône ;
- l'entité utilisée ;
- la couleur ;
- l'action réalisée lors d'un appui ;
- les fonctionnalités affichées ;
- la visibilité ;
- la taille de la carte.

Après la modification, cliquer sur :

```text
Enregistrer
```

Puis quitter le mode modification avec :

```text
Terminé
```

---

# 16. Modifier une carte en YAML

Dans la fenêtre de modification d'une carte, ouvrir le menu disponible en haut à droite.

Choisir :

```text
Afficher l'éditeur de code
```

La configuration YAML de la carte apparaît.

Exemple :

```yaml
type: tile
entity: sensor.temperature_salon
name: Température du salon
icon: mdi:home-thermometer
color: red
```

Attention à l'indentation YAML.

Les espaces placés au début des lignes sont importants. Il ne faut pas utiliser de tabulations.

---

# 17. Déplacer une carte

Passer le tableau de bord en mode modification.

Maintenir la carte puis la déplacer vers l'emplacement souhaité.

Dans une vue Sections, une carte peut être déplacée :

- dans la même section ;
- dans une autre section ;
- avant ou après une autre carte.

Terminer en cliquant sur :

```text
Terminé
```

---

# 18. Redimensionner une carte

Dans une vue Sections :

```text
Modifier le tableau de bord
→ Sélectionner la carte
→ Mise en page
```

La taille de la carte peut ensuite être ajustée.

Toutes les cartes ne proposent pas exactement les mêmes possibilités de redimensionnement.

Il est conseillé de vérifier le résultat :

- sur un ordinateur ;
- sur un smartphone ;
- sur une tablette, si le tableau de bord doit y être utilisé.

---

# 19. Supprimer une carte

Passer le tableau de bord en mode modification.

Sélectionner la carte puis utiliser l'option :

```text
Supprimer
```

La suppression d'une carte ne supprime pas l'équipement ni l'entité.

Elle retire uniquement la carte du tableau de bord.

---

# 20. Trouver l'identifiant d'une entité

Une entité Home Assistant possède un identifiant unique.

Exemples :

```text
sensor.temperature_salon
binary_sensor.porte_entree_contact
light.salon
switch.prise_salon
```

Pour trouver une entité :

**Paramètres → Appareils et services → Entités**

Il est également possible d'utiliser :

**Paramètres → Outils de développement → États**

Rechercher ensuite un mot correspondant à l'équipement :

```text
porte
temperature
battery
motion
humidity
```

Il est préférable de copier directement l'identifiant de l'entité pour éviter les erreurs de saisie.

---

# 21. Exemple de tableau de bord pour une installation Zigbee2MQTT

Pour une installation simple, il est possible d'utiliser l'organisation suivante :

```text
🏠 Accueil
🚪 Portes et fenêtres
🌡️ Températures
🔋 Batteries
⚙️ Maintenance
```

## Vue Accueil

Cette vue doit contenir les informations les plus importantes :

- état de la porte d'entrée ;
- température principale ;
- alertes ;
- éclairage principal ;
- niveau de batterie faible.

Exemple de carte :

```yaml
type: entities
title: État de la maison
show_header_toggle: false
entities:
  - entity: binary_sensor.porte_entree_contact
    name: Porte d'entrée
  - entity: sensor.temperature_salon
    name: Température du salon
  - entity: sensor.humidite_salon
    name: Humidité du salon
```

## Vue Portes et fenêtres

```yaml
type: entities
title: Portes et fenêtres
show_header_toggle: false
entities:
  - entity: binary_sensor.porte_entree_contact
    name: Porte d'entrée
  - entity: binary_sensor.porte_garage_contact
    name: Porte du garage
  - entity: binary_sensor.fenetre_cuisine_contact
    name: Fenêtre de la cuisine
```

## Vue Températures

```yaml
type: history-graph
title: Températures sur 24 heures
hours_to_show: 24
entities:
  - entity: sensor.temperature_salon
    name: Salon
  - entity: sensor.temperature_chambre
    name: Chambre
  - entity: sensor.temperature_cuisine
    name: Cuisine
```

## Vue Batteries

```yaml
type: entities
title: Batteries Zigbee
show_header_toggle: false
state_color: true
entities:
  - entity: sensor.porte_entree_battery
    name: Porte d'entrée
  - entity: sensor.porte_garage_battery
    name: Porte du garage
  - entity: sensor.temperature_salon_battery
    name: Thermomètre du salon
  - entity: sensor.detecteur_mouvement_battery
    name: Détecteur de mouvement
```

## Vue Maintenance

Cette vue peut regrouper :

- l'état de Zigbee2MQTT ;
- les mises à jour disponibles ;
- l'espace disque ;
- l'utilisation de la mémoire ;
- l'utilisation du processeur ;
- la dernière sauvegarde ;
- les capteurs indisponibles.

Les entités disponibles dépendent de la configuration de Home Assistant.

---

# 22. Afficher une carte seulement dans certaines conditions

Une carte peut être affichée uniquement lorsque certaines conditions sont remplies.

Par exemple, afficher une alerte uniquement lorsque la porte est ouverte :

```yaml
type: conditional
conditions:
  - condition: state
    entity: binary_sensor.porte_entree_contact
    state: "on"
card:
  type: markdown
  content: |
    # ⚠️ Attention

    La porte d'entrée est actuellement ouverte.
```

Lorsque la porte est fermée, la carte n'est plus affichée.

Cette méthode évite de surcharger la vue d'accueil avec des informations inutiles.

---

# 23. Afficher une vue pour certains utilisateurs

Une vue peut être rendue visible uniquement pour certains utilisateurs.

Pour configurer cette option :

```text
Modifier le tableau de bord
→ Modifier la vue
→ Visibilité
```

Cette fonction peut être utilisée pour :

- cacher une vue de maintenance ;
- réserver les commandes importantes à un administrateur ;
- simplifier l'interface d'un utilisateur ;
- créer une interface différente pour un smartphone ou une tablette.

Cette visibilité sert principalement à organiser l'interface. Elle ne doit pas être considérée comme l'unique protection d'un équipement sensible.

---

# 24. Recommandations pour un tableau de bord simple

Pour une personne débutante, il est conseillé de :

- limiter le nombre de vues ;
- utiliser principalement les cartes natives ;
- privilégier les cartes Tuile ;
- placer les informations importantes sur la vue d'accueil ;
- utiliser des noms simples ;
- utiliser des icônes faciles à reconnaître ;
- éviter de multiplier les couleurs ;
- vérifier l'affichage sur smartphone ;
- regrouper les batteries dans une vue dédiée ;
- utiliser les cartes conditionnelles pour les alertes.

Exemple de structure simple :

```text
Accueil
├── Porte d'entrée
├── Température du salon
├── Lumière principale
└── Alertes

Portes
├── Porte d'entrée
├── Porte du garage
└── Fenêtres

Batteries
├── Capteurs de porte
├── Détecteurs de mouvement
└── Sondes de température
```

---

# 25. Conseils avant une modification importante

Avant de modifier un tableau de bord complexe, créer une sauvegarde :

```text
Paramètres
→ Système
→ Sauvegardes
→ Créer une sauvegarde
```

Il est également possible de copier la configuration YAML d'une carte dans un fichier texte avant de la modifier.

Cela facilite le retour à la configuration précédente en cas d'erreur.

---

# 26. Dépannage

## La carte affiche « Entité introuvable »

Vérifier l'identifiant de l'entité dans :

**Paramètres → Outils de développement → États**


L'entité utilisée dans la carte a peut-être été renommée ou supprimée.

## La carte affiche « Inconnu »

Vérifier :

- que l'équipement est connecté ;
- que Zigbee2MQTT fonctionne ;
- que l'entité possède une valeur ;
- que le capteur n'est pas indisponible ;
- que la pile du capteur n'est pas vide.

## La carte n'apparaît pas

Vérifier :

- la vue sélectionnée ;
- la section dans laquelle elle a été créée ;
- les règles de visibilité ;
- les conditions de la carte ;
- les droits de l'utilisateur connecté.

## La modification n'est pas visible

Essayer :

```text
Actualiser la page
```

Sur un ordinateur, il est aussi possible d'effectuer un rechargement forcé :

```text
Ctrl + F5
```

Sur l'application mobile, fermer puis rouvrir le tableau de bord peut également actualiser son affichage.

## Le YAML affiche une erreur

Vérifier :

- l'indentation ;
- les espaces ;
- les deux-points ;
- les guillemets ;
- l'identifiant de l'entité ;
- le type de carte ;
- le nom de l'action appelée.

Ne pas utiliser de tabulations dans une configuration YAML.

---

# 27. Exemple d'organisation finale

Une organisation simple et adaptée à une installation Home Assistant avec Zigbee2MQTT peut être :

```text
🏠 Accueil
   ├── État de la maison
   ├── Porte d'entrée
   ├── Température du salon
   ├── Éclairage principal
   └── Alertes

🚪 Portes et fenêtres
   ├── Porte d'entrée
   ├── Porte du garage
   └── Fenêtres

🌡️ Températures
   ├── Salon
   ├── Chambre
   ├── Cuisine
   └── Historique sur 24 heures

🔋 Batteries
   ├── Capteurs de porte
   ├── Détecteurs de mouvement
   └── Sondes de température

⚙️ Maintenance
   ├── État de Zigbee2MQTT
   ├── Mises à jour
   ├── Stockage
   └── Équipements indisponibles
```

Cette organisation reste simple à utiliser tout en permettant d'ajouter progressivement de nouveaux équipements.

---

## Utiliser HACS et les cartes personnalisées (niveau intermédiaire)
<details>
<summary>Afficher le détail</summary>
Une fois à l'aise avec les dashboards de base, HACS permet d'ajouter des cartes très populaires :

- Mushroom Cards
- Button Card
- Mini Graph Card
- ApexCharts Card
- Auto Entities

Pour quelqu'un qui débute avec Home Assistant, je recommande particulièrement Mushroom car les cartes sont modernes, simples à configurer et très lisibles sur smartphone et tablette.

Exemple :
```
type: custom:mushroom-entity-card
entity: sensor.temperature_salon
name: Salon
icon: mdi:home-thermometer
```

Le résultat est généralement beaucoup plus esthétique que les cartes natives de Home Assistant.
</details>
