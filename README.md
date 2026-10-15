# Open Radar Sensor Dataset

Specifications for 132 commercial radar sensors and modules from 64 manufacturers. They cover automotive, industrial, traffic, presence-sensing and robotics uses, mostly in the 60 GHz and 76–81 GHz bands.

Data collected September 2026. Check the linked datasheet before relying on a value.

## Files

| File | Contents |
|---|---|
| `radars.csv` | One row per radar. |
| `sources.csv` | Source URL and verbatim quote for every value in `radars.csv` (`id`, `field`, `value`, `source_url`, `quote`, `conversion`). Join on `id`. |

## Conventions

- A blank cell means no public source was found for that value.
- Units are in the column name. Fields of view are full angles: ±60° is recorded as 120.
- For multi-mode sensors, FoV and max range are the largest stated values, and resolutions are the finest. These may come from different modes, so see `notes`.
- Velocities are radial in m/s. Negative means approaching.
- `fcc_id` is only filled when the grant is tied to that exact model.
- Prices are public list prices in USD, at `price_qty`, observed on `price_date`.
- Each radar included has a sourced horizontal FoV and max range, plus at least 9 of the 17 key performance and integration specs.

## Columns

| Column | Description |
|---|---|
| `id` | Unique identifier (manufacturer-model) |
| `manufacturer` | Brand that makes or sells the sensor |
| `model` | Model name |
| `part_number` | Orderable part number |
| `product_type` | `sensor`, `module` or `eval_kit` |
| `application` | `automotive_corner`, `automotive_front`, `automotive_interior`, `industrial`, `traffic`, `presence_people`, `robotics_drone`, `general_mmwave` or `other` |
| `band_ghz` | Operating frequency band (GHz) |
| `fcc_id` | FCC ID |
| `production_status` | `production`, `sample`, `development` or `discontinued` |
| `hfov_deg` | Horizontal field of view (°) |
| `vfov_deg` | Vertical field of view (°) |
| `elevation_measured` | Measures elevation per detection (3D/4D): `yes` / `no` |
| `range_min_m` | Minimum range (m) |
| `range_max_m` | Maximum range (m) |
| `range_res_m` | Range resolution (m) |
| `range_acc_m` | Range accuracy (m) |
| `az_res_deg` | Azimuth resolution (°) |
| `az_acc_deg` | Azimuth accuracy (°) |
| `el_res_deg` | Elevation resolution (°) |
| `velocity_min_ms` | Minimum radial velocity (m/s) |
| `velocity_max_ms` | Maximum radial velocity (m/s) |
| `velocity_res_ms` | Velocity resolution (m/s) |
| `output_type` | `point_cloud`, `tracks`, `point_cloud+tracks` or `presence` |
| `max_points_per_frame` | Maximum detections per frame |
| `static_targets` | Reports stationary objects: `yes` / `no` |
| `update_hz` | Update rate (Hz) |
| `interface` | Data interface |
| `supply_v_min` | Minimum supply voltage (V) |
| `supply_v_max` | Maximum supply voltage (V) |
| `power_w` | Power consumption (W) |
| `ip_rating` | Ingress protection rating |
| `temp_min_c` | Minimum operating temperature (°C) |
| `temp_max_c` | Maximum operating temperature (°C) |
| `dimensions_mm` | Dimensions (mm) |
| `weight_g` | Weight (g) |
| `ros_driver` | Public ROS/ROS 2 driver available: `yes` / `no` |
| `public_protocol` | Message protocol or DBC publicly available: `yes` / `no` |
| `list_price_usd` | List price (USD) |
| `price_qty` | Quantity the price applies to |
| `price_date` | Date the price was observed |
| `datasheet_url` | Datasheet or product page |
| `notes` | Additional details |

## Disclaimer

Values are manufacturer-published specifications and have not been independently tested. Product names and trademarks belong to their respective owners.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
