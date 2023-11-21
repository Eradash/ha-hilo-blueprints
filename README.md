# Blueprints pour les challenges Hilo
Blueprints pour Home Assistant pour utiliser l'intégration Hilo facilement. Vous allez être en mesure d'automatiser la température cible de vos thermostats pour augmenter vos récompenses Hilo

## Configuration

Vous allez avoir besoin de l'inrégration [Hilo](https://github.com/dvd-dev/hilo) pour que ces Blusprints fonctionnent

**La période d'appréciation doit être de 3 heures**

Créez une entrée `input_text`, ceci va stocker la phase courante des défis.

* Juste ici pour la configuration: [![Open your Home Assistant instance and show your helper entities.](https://my.home-assistant.io/badges/helpers.svg)](https://my.home-assistant.io/redirect/helpers/)

Ajoutez un `sensor` dans le fichier de configuration avec ce code:

```yaml
sensor:
  - platform: template
    sensors:
      challenge_in_progress:
        friendly_name: Senseur de défi en cours
        value_template: "{{ is_state('sensor.defi_hilo', 'appreciation') or is_state('sensor.defi_hilo', 'pre_heat') or is_state('sensor.defi_hilo', 'reduction') }}"
```

Installez les blueprints avec ces liens:

* Challenge entity status: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fchallenge_entity_updater.yaml)

* Automatic challenges: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fdefis_automatiques.yaml)


## Contribution

Si vous voulez améliorer, gênez-vous pas! Présentement, j'aimerais ajouter une manière de mieux contrôller une thermopompe, pour réduire les coûts liés au pré-chauffage. Cela doit être configurable avec une valeur limite de température extérieure.

## À faire:

La liste n'est pas complète, si vous avez des idées, envoyez une Pull Request ;) 

* Ajouter des Blueprints pour des notifications avec des estimés et des résultats
* Compléter le README avec les détails sur comment les automatisations sont configurées
* Ajouter une manière de contrôler la charge d'un véhicule électrique durant les défis