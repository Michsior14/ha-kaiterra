# Home Assistant kaiterra sensors component
Home Assistant custom component for the Kaiterra's devices

## Installation

### Getting the Kaiterra's API key
First you need to get the device id and api key from kaiterra site.
1. Register on https://dashboard.kaiterra.cn
2. Add device to dashbord using "+" sign on the bottom and write down device uuid
3. Open [Profile/Developer](https://dashboard.kaiterra.cn/me/account/developer), generate new key and write it down

### Manual installation
1. Using the tool of choice open the directory (folder) for your HA configuration (where you find configuration.yaml).
2. If you do not have a `custom_components` directory (folder) there, you need to create it.
3. In the custom_components directory (folder) create a new folder called `kaiterra`.
4. Download all the files from the `custom_components/kaiterra/` directory (folder) in this repository.
5. Place the files you downloaded in the new directory (folder) `custom_components/kaiterra/` you created.
6. Add the following to your _configuration.yaml_ using your device id and api key from the Kaiterra's dashboard. You can adjust/remove optional parameters.

```yaml
sensor:
  - platform: kaiterra
    api_key: xxxxx
    devices:
      - device_id: xxxxx
        type: laseregg 
```

7. Restart home-assistant

### HACS installation
1. Ensure that [HACS](https://custom-components.github.io/hacs/) is installed.
2. Search for and install the "Laser Egg" integration.
3. Configure the `kaiterra` sensor.

```yaml
sensor:
  - platform: kaiterra
    api_key: xxxxx
    devices:
      - device_id: xxxxx
        type: laseregg 
```

4. Restart Home Assistant.


## Configuration options

### Sensor configuration

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`api_key` | `string` | `True` | `-` | The api key from Kaiterra's dashboard
`aqi_standard` | `string` | `True` | `us` | The Air Quality Index standard, available options: ["cn", "in", "us"]
`scan_interval` | `string` | `False` | `30` | The api communication interval
`preferred_units` | `-` | `False` | `[]` | The preferred units list, available values: ["x", "%", "C", "F", "mg/m³", "µg/m³", "ppm", "ppb"]
`devices` | `-` | `True` | `-` | The devices configuration list

### Device configuration

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`device_id` | `string` | `True` | `-` | The device id from Kaiterra's dashboard
`type` | `string` | `True` | `-` | The device id from Kaiterra's dashboard
`name` | `string` | `False` | `-` | Name of the integration


## Contribution
PRs and help welcomed ;)
