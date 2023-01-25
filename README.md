# Blueprints for Hilo challenges
Blueprints for Home Assistant to use the Hilo integrations easily. You will be able to set your climate controls to increase your Hilo rewards.

## Setup

You will need the [Hilo](https://github.com/dvd-dev/hilo) integration for this to work

**You need to set the appreciation period to 3 hours**

Create an `input_text` input, this will store the current phase of challenges and references

* Right here in your configuration: [![Open your Home Assistant instance and show your helper entities.](https://my.home-assistant.io/badges/helpers.svg)](https://my.home-assistant.io/redirect/helpers/)

Add a `sensor` in your configuration file with this pattern:

```yaml
challenge_in_progress:
  friendly_name: Challenge in progress sensor
  value_template: "{{ is_state('sensor.defi_hilo', 'appreciation') or is_state('sensor.defi_hilo', 'pre_heat') or is_state('sensor.defi_hilo', 'reduction') }}"
```

Install your blueprints with those links:

* Challenge entity status: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fchallenge_entity_updater.yaml)

* Automatic challenges: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FEradash%2Fha-hilo-blueprints%2Fmain%2Fgeneric_challenges.yaml)

## Contributing

I need help abstracting the Hilo integration. For now, a sensor is still needs to know if a challenge is in progress or not, this needs to change.

## To do:

This list is not complete, if you have any ideas, please send a Pull request :)

* Add Blueprints for notifications with estimates and results
* Complete the README with screenshots
* Add a way to add an electric car charger control in the challenges