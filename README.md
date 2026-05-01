# RadioIndustryMap

**RadioIndustryMap** is a large-scale, high-fidelity, time-varying electromagnetic (EM) / radio map dataset designed for **Electromagnetic Map Reconstruction**, **Radio Environment Mapping (REM)**, and **6G Industrial Internet of Things (IIoT)** research.

Unlike conventional radio map datasets that mainly focus on static base stations in simplified urban concrete-canyon environments, RadioIndustryMap targets realistic industrial and offshore scenarios with **mobile transmitters**, **dynamic radio propagation**, **heterogeneous material compositions**, and **complex industrial geometries**. The dataset explicitly models representative material categories such as **metal, concrete, vegetation, road surfaces, water surfaces, industrial facilities, and moving vessels**, enabling research on radio map reconstruction under realistic and safety-critical industrial wireless conditions.

This repository provides the dataset described in our paper:

> **[Paper Title Will Be Updated]**

The full citation will be provided after the paper is accepted and published.

---

## Citation

If you use RadioIndustryMap in your research, please cite our paper.

```bibtex
@inproceedings{radioindustrymap2026,
  title     = {RadioIndustryMap: A Large-Scale Dynamic Radio Map Dataset for Industrial Wireless Environments},
  author    = {Author Names Will Be Updated},
  booktitle = {IEEE ICC / IEEE GLOBECOM},
  year      = {2026}
}
```

Citation details will be updated after publication.

---

## Why Do We Need RadioIndustryMap?

Most existing EM map and radio map datasets are built upon simplified assumptions, such as **static transmitters**, **homogeneous building materials**, and relatively regular urban layouts. These assumptions are useful for early-stage algorithm development, but they are insufficient for modeling the radio propagation characteristics of real industrial environments.

In practical wireless systems, especially in **smart factories**, **automated container ports**, **chemical plants**, **offshore industrial zones**, **autonomous driving systems**, **UAV swarms**, and **robotic inspection networks**, the radio environment is highly dynamic and materially heterogeneous. The received signal distribution can be strongly affected by:

- Mobile transmitters mounted on vehicles, robots, vessels, or temporary communication nodes;
- Metallic objects such as containers, cranes, ship hulls, storage tanks, and pipelines;
- Heterogeneous materials, including metal, concrete, vegetation, road surfaces, and water surfaces;
- Severe multipath propagation, strong specular reflection, diffraction, and scattering;
- Dynamic blockage and time-varying shadowing caused by moving industrial objects;
- Abrupt line-of-sight / non-line-of-sight transitions in dense industrial infrastructures.

For example, stacked containers in ports can create strong canyon-like propagation effects; storage tanks and pipe galleries in chemical plants can introduce deep fading and severe shadowing; moving vessels and ship hulls in offshore scenarios can cause time-varying reflection and blockage. These effects are difficult to capture using conventional static urban datasets.

**RadioIndustryMap is designed to fill this gap.** It provides a dynamic, material-aware, and large-scale radio map benchmark for developing and evaluating learning-based radio map reconstruction algorithms in realistic industrial wireless environments.

---

## Dataset Highlights

### 1. Dynamic and Time-Varying Radio Maps

RadioIndustryMap provides **50 consecutive temporal frames** for each dynamic sequence. The transmitter trajectories are discretized with a time interval of **2 seconds**, resulting in a sampling duration of **100 seconds** for each scenario.

The dataset includes both fixed and mobile transmitters. Mobile transmitters are used to emulate practical industrial communication sources, such as:

- Automated guided vehicles;
- Port delivery vehicles;
- Robotic inspection platforms;
- Mobile emergency communication nodes;
- Moving vessels and ship-mounted communication equipment.

This design enables research on:

- 4D radio map reconstruction;
- Dynamic radio environment prediction;
- Mobility-aware coverage estimation;
- Communication dead-zone prediction;
- Proactive handover and resource allocation;
- Active interference mitigation in industrial networks.

---

### 2. Realistic Industrial and Offshore Scenarios

RadioIndustryMap covers representative industrial and offshore environments, including:

- Automated chemical plants;
- Smart container ports;
- Offshore industrial zones;
- Moving-vessel scenarios;
- Large-scale industrial factory areas.

These environments are much more complex than regular urban blocks. They contain irregular industrial layouts, dense metallic facilities, large open spaces, water surfaces, and moving objects. As a result, the dataset can better represent the propagation characteristics of practical 6G IIoT systems.

---

### 3. Material-Aware Electromagnetic Modeling

RadioIndustryMap explicitly considers heterogeneous material compositions. The dataset contains semantic and material information for different environmental elements, including:

- **Metal:** containers, cranes, ship hulls, pipelines, storage tanks, and industrial equipment;
- **Concrete:** buildings, workshops, warehouses, and factory structures;
- **Vegetation:** trees, green belts, and vegetation-covered regions;
- **Water surfaces:** offshore areas, port-side waters, and maritime propagation environments;
- **Road and ground surfaces:** industrial roads, factory lanes, and port operation areas.

This material-aware design enables the dataset to capture strong metal-induced reflection, shielding effects, vegetation attenuation, and maritime reflection, which are essential for realistic industrial radio map modeling.

---

### 4. Multi-Frequency and Multi-Height Coverage

RadioIndustryMap supports multiple frequency bands and receiver heights. This enables the study of frequency-dependent and height-dependent propagation characteristics.

The current release includes the following frequency bands:

```text
500 MHz, 700 MHz, 900 MHz, 1500 MHz, 1800 MHz, 2000 MHz,
2100 MHz, 3500 MHz, 4900 MHz, 5000 MHz, 5800 MHz
```

The dataset includes five receiver heights:

```text
1.5 m, 5 m, 10 m, 20 m, 60 m
```

These receiver heights correspond to different industrial communication layers, including ground users, vehicles, elevated infrastructure, low-altitude nodes, and aerial communication platforms.

---

### 5. Large-Scale High-Fidelity Dataset

RadioIndustryMap contains approximately:

| Item | Description |
|---|---|
| Number of scenarios | Approximately 400 scenes |
| Number of samples | Approximately 400,000 radio map samples |
| Scenario types | Industrial plants, smart ports, offshore zones, moving-vessel scenarios |
| Frequency bands | 11 frequency bands from 500 MHz to 5800 MHz |
| Receiver heights | 5 heights: 1.5 m, 5 m, 10 m, 20 m, 60 m |
| Temporal frames | 50 frames per dynamic sequence |
| Time interval | 2 seconds |
| Duration per sequence | 100 seconds |
| Grid size | 512 × 512 |
| Spatial resolution | 3 m per grid cell |
| Physical coverage | 1536 m × 1536 m per radio map |
| Data formats | `.npy`, `.png`, `.gif`, metadata files |

The dataset is suitable for training, validating, and benchmarking learning-based radio map reconstruction methods under realistic industrial propagation conditions.

---

## Dataset Description

RadioIndustryMap is organized by **scenario type**, **frequency band**, **receiver height**, and **temporal frame**. Each radio map sample corresponds to a specific industrial scene, carrier frequency, receiver height, and time index.

For each scenario, the dataset provides:

- Raw radio map matrices in `.npy` format;
- Visualization images in `.png` format;
- Dynamic radio map animations in `.gif` format;
- Building spatial distribution information;
- Vegetation spatial distribution information;
- Material and environmental semantic information;
- Road topology and transmitter trajectory information;
- Geographic metadata and coordinate-related information.

The radio maps are generated on a `512 × 512` grid with a spatial resolution of `3 m`, corresponding to a physical coverage area of `1536 m × 1536 m`. For dynamic scenarios, the transmitter trajectory is sampled every `2 s`, and each sequence contains `50` consecutive temporal frames.

RadioIndustryMap can be used for both supervised learning and benchmark evaluation. It supports tasks such as sparse radio map reconstruction, time-varying radio map prediction, cross-frequency learning, multi-height radio map reconstruction, and physics-informed radio environment modeling.

---

## Dataset Preview

The following figures are placeholders. Please replace them with real images from the dataset before releasing the repository.

### Fig. 1. Dataset Overview

<p align="center">
  <img src="assets/radioindustrymap_overview.png" width="850">
</p>

<p align="center">
  <em>Overview of RadioIndustryMap, including realistic geographic maps, industrial simulation scenes, and generated radio maps.</em>
</p>

---

### Fig. 2. Geographic Map and Radio Map Pair

<p align="center">
  <img src="assets/map_radio_pair_example.png" width="850">
</p>

<p align="center">
  <em>Example of a geographic map and its corresponding generated radio map.</em>
</p>

---

### Fig. 3. Dynamic Radio Map Sequence

<p align="center">
  <img src="assets/dynamic_radio_map.gif" width="650">
</p>

<p align="center">
  <em>Example of a time-varying radio map sequence generated by mobile transmitters.</em>
</p>

---

### Fig. 4. Material and Environmental Layers

<p align="center">
  <img src="assets/material_layers.png" width="850">
</p>

<p align="center">
  <em>Example of environmental semantic layers, including buildings, vegetation, materials, roads, and geographic information.</em>
</p>

---

## Download

The dataset can be accessed through the following cloud storage link:

- Baidu Netdisk: [Link will be updated]()

Additional download links, such as Google Drive or OneDrive, may be provided in future releases.

---

## File Description

RadioIndustryMap contains radio map files, visualization files, dynamic animations, and global environmental metadata.

### Radio Map Matrix

```text
mapx_hm_t=y.npy
```

Raw radio map matrix data for model training and evaluation.

Example:

```text
map1_1.5m_t=1.npy
map1_1.5m_t=50.npy
```

where:

- `mapx` denotes the scenario or map index;
- `hm` denotes the receiver height;
- `t=y` denotes the temporal frame index.

---

### Radio Map Visualization

```text
mapx_hm_t=y.png
```

Visualization image of the corresponding radio map.

Example:

```text
map1_1.5m_t=1.png
map1_1.5m_t=50.png
```

---

### Dynamic Radio Map Animation

```text
mapx_hm.gif
```

Animated visualization of a continuous time-varying radio map sequence.

Example:

```text
map1_1.5m.gif
```

---

### Building Information

```text
Building.zip
```

This compressed file contains building spatial distribution information for the corresponding scenes.

---

### Vegetation Information

```text
vegetation.zip
```

This compressed file contains vegetation spatial distribution information.

---

### Road and Trajectory Information

```text
way.zip
```

This compressed file contains road topology and transmitter trajectory-related information.

---

### Material Information

```text
Material/
```

This directory contains material distribution maps and material labels for industrial objects.

---

### Geographic Information

```text
Geography/
```

This directory contains geographic information, including OpenStreetMap data and longitude-latitude mapping files.

---

## Directory Structure

The dataset is organized as follows:

```text
RadioIndustryMap/
├── Automated_Chemical_Plant/
│   ├── 500MHz/
│   │   ├── 1.5m/
│   │   │   ├── npy/
│   │   │   │   ├── map1_1.5m_t=1.npy
│   │   │   │   ├── map1_1.5m_t=2.npy
│   │   │   │   ├── ...
│   │   │   │   └── map1_1.5m_t=50.npy
│   │   │   ├── png/
│   │   │   │   ├── map1_1.5m_t=1.png
│   │   │   │   ├── map1_1.5m_t=2.png
│   │   │   │   ├── ...
│   │   │   │   └── map1_1.5m_t=50.png
│   │   │   └── gif/
│   │   │       ├── map1_1.5m.gif
│   │   │       └── ...
│   │   ├── 5m/
│   │   │   └── ...
│   │   ├── 10m/
│   │   │   └── ...
│   │   ├── 20m/
│   │   │   └── ...
│   │   └── 60m/
│   │       └── ...
│   ├── 700MHz/
│   │   └── ...
│   ├── 900MHz/
│   │   └── ...
│   ├── 1500MHz/
│   │   └── ...
│   ├── 1800MHz/
│   │   └── ...
│   ├── 2000MHz/
│   │   └── ...
│   ├── 2100MHz/
│   │   └── ...
│   ├── 3500MHz/
│   │   └── ...
│   ├── 4900MHz/
│   │   └── ...
│   ├── 5000MHz/
│   │   └── ...
│   └── 5800MHz/
│       └── ...
│
├── Smart_Container_Port/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
├── Offshore_Industrial_Zone/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
├── Moving_Vessel/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
└── Global_Index/
    ├── Material/
    │   ├── map1_material.npy
    │   ├── map2_material.npy
    │   ├── ...
    │   └── material_labels.json
    │
    ├── Building/
    │   ├── map1_building.npy
    │   ├── map2_building.npy
    │   ├── ...
    │   └── Building.zip
    │
    ├── Vegetation/
    │   ├── map1_vegetation.npy
    │   ├── map2_vegetation.npy
    │   ├── ...
    │   └── vegetation.zip
    │
    ├── Trajectory/
    │   ├── map1_tx_trajectory.npy
    │   ├── map2_tx_trajectory.npy
    │   ├── ...
    │   └── trajectory_metadata.json
    │
    └── Geography/
        ├── Open_Street_Map/
        │   └── way.zip
        │
        └── longitude_and_latitude/
            ├── map1_coordinates.npy
            ├── map2_coordinates.npy
            └── ...
```

---

## Example Usage

The following example shows how to load and visualize a radio map sample stored in `.npy` format.

```python
import numpy as np
import matplotlib.pyplot as plt

# Load one radio map sample
radio_map = np.load(
    "RadioIndustryMap/Smart_Container_Port/500MHz/1.5m/npy/map1_1.5m_t=1.npy"
)

print("Radio map shape:", radio_map.shape)

# Visualize the radio map
plt.figure(figsize=(6, 5))
plt.imshow(radio_map, origin="lower")
plt.colorbar(label="Radio map value")
plt.title("Example Radio Map")
plt.xlabel("X grid index")
plt.ylabel("Y grid index")
plt.tight_layout()
plt.show()
```

---

## Recommended Research Tasks

RadioIndustryMap can support a wide range of research tasks, including:

- Sparse radio map reconstruction;
- Electromagnetic map completion;
- Radio environment mapping;
- Dynamic radio map prediction;
- 4D radio map reconstruction;
- Multi-frequency radio map learning;
- Multi-height radio map reconstruction;
- Cross-scenario generalization;
- Industrial wireless coverage prediction;
- Communication dead-zone forecasting;
- Mobility-aware radio map prediction;
- Geometry-aware neural network design;
- Material-aware radio map reconstruction;
- Physics-informed radio environment modeling;
- 6G IIoT network planning and optimization.

---

## Data Split Recommendation

To avoid data leakage, we recommend splitting the dataset by **scenario index** rather than randomly splitting individual temporal frames from the same sequence.

For example:

```text
Training set:     map1  - map280
Validation set:   map281 - map340
Test set:         map341 - map400
```

For temporal prediction tasks, users may also split each sequence by time:

```text
Input frames:     t = 1, 2, ..., 40
Prediction frames: t = 41, 42, ..., 50
```

The exact split can be adjusted according to the target task.

---

## Benchmark

We provide a preliminary benchmark using the classical **RadioUNet** model under an extremely sparse sampling condition.

The mask ratio is set to:

```text
0.95
```

The benchmark results are:

| Model | Mask Ratio | NMSE | PSNR | SSIM |
|---|---:|---:|---:|---:|
| RadioUNet | 0.95 | 0.7108 | 11.7047 | 0.5752 |

The results show that industrial radio map reconstruction is significantly more challenging than conventional urban radio map reconstruction. The complex industrial geometry, heterogeneous material composition, strong metallic reflection, dynamic blockage, and non-stationary fading effects pose substantial challenges to existing learning-based methods.

---

## Notes

1. The current dataset release contains approximately 400 scenes and 400,000 radio map samples.

2. RadioIndustryMap is generated for academic research on radio map reconstruction, radio environment mapping, and 6G industrial wireless communication.

3. Users should carefully check the task setting before training, especially for temporal prediction, cross-frequency learning, cross-height generalization, and cross-scenario evaluation.

4. Some geographic information is derived from OpenStreetMap-related data. Please follow the corresponding OpenStreetMap data usage and attribution requirements when using such information.

5. The dataset structure may be updated in future releases. Please refer to the latest version of this repository for updated file organization and metadata descriptions.

---

## License

The license information will be updated before the public release.

For academic use, please cite the corresponding paper and this repository.

---

## Contact

If you have any questions about the dataset, please open an issue in this repository or contact the project team.

Project contact information will be updated after the dataset is released.
