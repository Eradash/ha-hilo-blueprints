# Blueprints for Hilo challenges
Blueprints for Home Assistant to use the Hilo integrations easily

## Setup

You will need the Hilo integration for this to work

* Create an `input_text` input, this will store the current phase of challenges and references

* Add a `sensor` in your configuration file with this pattern:
```yaml
challenge_in_progress:
  friendly_name: Challenge in progress sensor
  value_template: "{{ is_state('sensor.defi_hilo', 'appreciation') or is_state('sensor.defi_hilo', 'pre_heat') or is_state('sensor.defi_hilo', 'reduction') }}"
```

* Create a `Challenge entity updater` automation, and add the input text and the challenge_in_progress sensor.

* Create a `Generic Hydro-Québec challenges` automation, and add the input text, and all options you want

## Contributing

I need help abstracting the Hilo integration. For now, a sensor is still needed to know if a challenge is in progress or not, this need to change.

## To do:

This list is not complete, if you have any ideas, please send a Pull request :)

* Add a way to import easily the Blueprints to Home Assistant
* Add a way to not have the Hilo integration (for those with only the Hydro-Québec way of challenges)
* Add Blueprints for notifications with estimates and results