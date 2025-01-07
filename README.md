# Blueprints pour les challenges Hilo
Blueprints pour Home Assistant pour utiliser l'intégration Hilo facilement. Vous allez être en mesure d'automatiser la température cible de vos thermostats pour augmenter vos récompenses Hilo

## Configuration
### L'application Hilo
Pour un fonctionnement optimal, désactivez la prise en charge des thermostats pendant les défis dans l'application Hilo. Vous participerez tout de même aux défis et recevrez les récompenses. Il est également recommandé de ne pas avoir de scènes programmées. Cela s'applique également à tous les autres thermostats non-Hilo, qui pourraient être gérés par ces automatisations.

### Intégration Hilo
Vous allez avoir besoin de l'intégration [Hilo](https://github.com/dvd-dev/hilo) pour que ces Blueprints fonctionnent

**La période d'appréciation doit être de 3 heures. Vous pouvez le mettre dans la configuration de l'intégration Hilo**

### Création d'un 'input_text'
Créez une entrée `input_text`, ceci va stocker la phase courante des défis.

Allez dans les "helpers" pour la configuration: [![Open your Home Assistant instance and show your helper entities.](https://my.home-assistant.io/badges/helpers.svg)](https://my.home-assistant.io/redirect/helpers/)
Choisissez "Text", donnez-lui un nom unique comme "text defi en cours" sans autre option et appuyé sur "create".

### Creéation d'un 'Sensor'
Ajoutez un `sensor` dans le fichier de configuration (configuration.yaml) accessible via le addon "File Editor" avec ce code:

```yaml
template:
  - sensor:
      - name: Senseur de défi en cours
        state: "{{ is_state('sensor.defi_hilo', ['appreciation','pre_heat','reduction','pre_cold']) }}"
```

**Redémarrez Home Assistant pour que le `sensor` devienne disponible.**

### Installation des "Blueprints"
Installez les blueprints avec ces liens:

* Entité de référence: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fdefis_entite_reference.yaml)

* Défi automatiques: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fdefis_automatiques.yaml)


## Contribution

Si vous voulez améliorer, gênez-vous pas! Présentement, j'aimerais ajouter une manière de mieux contrôller une thermopompe, pour réduire les coûts liés au pré-chauffage. Cela doit être configurable avec une valeur limite de température extérieure.

## À faire:

La liste n'est pas complète, si vous avez des idées, envoyez une Pull Request ;) 

* Ajouter des Blueprints pour des notifications avec des estimés et des résultats
* Compléter le README avec les détails sur comment les automatisations sont configurées
* Ajouter une manière de contrôler la charge d'un véhicule électrique durant les défis
