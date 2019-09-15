# Home Assistant Kaiterra's sensors component
Home Assistant custom component for the Kaiterra's sensors

## Getting the Kaiterra's API key
First you need to get the device id and api key from kaiterra site.
1. Register on https://dashboard.kaiterra.cn
2. Add device to dashbord using "+" sign on the bottom and write down device uuid
3. Open [Profile/Developer](https://dashboard.kaiterra.cn/me/account/developer), generate new key and write it down

## Usage

```yaml
sensor:
  - platform: kaiterra
    api_key: xxxxx
    devices:
      - device_id: xxxxx
        type: laseregg 
```

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
