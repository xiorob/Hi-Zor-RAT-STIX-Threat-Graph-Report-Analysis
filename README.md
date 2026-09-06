# Hi-Zor-RAT-STIX-Threat-Graph-Report-Analysis
Full report on a certain malware RAT called Hi-Zor RAT, including a full analysis of the kill chain, a StixViz data visualization &amp; risk mitigation using the MITRE ATT&amp;CK Framework.

# STIX Threat Intelligence & ATT&CK Graph Modeling

## Overview
This project models and analyzes unstructured threat intelligence on the **Hi-Zor RAT (Software S0087)** using standardized threat frameworks. By translating raw malware telemetry and multi-stage kill chain behaviors into structured **STIX graph objects**, I mapped entity relationships using **STIXViz** to visualize adversary tactics, infrastructure, and technical indicators across the campaign.

![STIX Graph Preview](stix-threat-graph-modeling/visualizations/STIXViz9-6-2026.png)

## Data Architecture & Analytics Methodology

* **Data Normalization & Schema Mapping:** Converted messy, unstructured threat reports into machine-readable STIX graph entities (Threat Actor, Campaign, TTP, Indicator, Observable) to model directed node-and-edge relationships.
* **Graph Visualization & Topology Analysis:** Built interactive graph views in **STIXViz** to map high-dimensional relationships between threat actors, delivery channels, and C2 nodes, enabling clear multi-hop analysis of payload delivery vectors[cite: 1].
* **Ontology Alignment (MITRE ATT&CK):** Standardized multi-stage attack behaviors against the MITRE enterprise ontology, mapping execution paths to technique IDs including:
  * `T1105` — Ingress Tool Transfer[cite: 1]
  * `T1570` — Lateral Tool Transfer[cite: 1]
  * `T1547.001` — Registry Run Keys / Startup Folder Persistence[cite: 1]
* **Detection Engineering & Anomaly Analysis:** Evaluated string stacking, double XOR obfuscation, and registry run key insertions (`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`) to establish data-driven detection strategies (DET0365, DET0060) and execution mitigation pathways[cite: 1].

## Repository Structure

```
stix-threat-graph-modeling/
├── README.md
├── reports/
│   └── Hi-Zor_RAT_Final_Report.pdf
├── data/
│   ├── (All HTML files)
├── visualizations/
│   ├── STIXViz9-6-2026.png
└── docs/
    └── Soltra-EdgeScreenshot1-12-2025.jpeg
