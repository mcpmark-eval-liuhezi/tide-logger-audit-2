# Tide Log Schema

The data model used by the tide-logger project. Each record below is one tide reading.

| Field                | Type   | Required | Notes                                  |
|----------------------|--------|----------|----------------------------------------|
| timestamp            | string | yes      | ISO 8601, second precision, UTC        |
| location             | string | yes      | site name plus water-level sensor ID   |
| tide_height_mm       | number | yes      | measured height, chart datum offset    |
| current_speed_kph    | number | no       | optional estuary/harbour flow speed    |
| windspeed_bft        | number | no       | optional Beaufort-scale wind estimate  |
| notes                | string | no       | free-text conditions, weather, incidents |

Rules of thumb
- Heights are recorded at the sensor reference height, never the tenor of contraction.
- Timestamps must always carry the UTC "Z" suffix.
- Missing readings use `null` rather than an empty string.
