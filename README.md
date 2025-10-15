# Urban Rail Network Resilience Analysis [Currently Under Review at npj Sustainable Mobility and Transport]

The PDF of the manuscript is [here](Urban_Rail_Research_Manuscript%20%5BFinal_Version%5D.pdf).

## 📊 Overview

This repository contains the code and data for the research paper **"Resilience of urban rail networks globally guided by mesoscale and connectivity attributes"** Currently Under Review at npj Sustainable Mobility and Transport. The study analyzes the resilience of 45 global metro rail systems under various failure and recovery scenarios, providing insights into how network topology influences system robustness.


## 🚇 Research Highlights

- **Global Scale**: Analysis of 45 metro rail networks across 5 continents
- **Comprehensive Metrics**: 25 structural network attributes evaluated
- **Multiple Strategies**: 7 different failure and recovery intervention strategies
- **Practical Application**: Demonstrated retrofitting strategies for Boston's metro system
- **Novel Methodology**: Integration of DomiRank centrality and mutual information analysis

## 📈 Key Findings

### Failure Resilience
- **Dense, globally connected networks** with reduced modularity show better failure resilience
- **High average betweenness centrality** enables alternate routing during disruptions
- **Global efficiency metrics** and **connectivity patterns** are crucial for robustness

### Recovery Resilience
- **Degree heterogeneity** and **loop structures** accelerate recovery
- **Balanced degree distribution** promotes efficient reconnection
- **Modularity patterns** influence restoration capacity

### Practical Impact
- **11.9% improvement** in failure resilience through targeted retrofitting
- **3% improvement** in recovery performance with topology-aware interventions
- Actionable insights for urban planners and infrastructure designers

## 🗂️ Repository Structure

```
urban_rail_research/
├── README.md                           # This file
├── all_network_attributes.csv         # Network attributes for all 45 metro systems
├── all_networks.gpickle              # NetworkX graphs of all metro systems
├── failure_replication.ipynb         # Failure simulation analysis
├── recovery_replication.ipynb        # Recovery simulation analysis
├── visual_script.ipynb               # Visualization and plotting scripts
├── failure_results.pkl               # Pre-computed failure simulation results
└── recovery_results.pkl              # Pre-computed recovery simulation results
```

## 🚀 Quick Start

### Prerequisites

```bash
pip install networkx numpy matplotlib pandas scipy scikit-learn
```

### Running the Analysis

1. **Failure Analysis**:
   ```bash
   jupyter notebook failure_replication.ipynb
   ```

2. **Recovery Analysis**:
   ```bash
   jupyter notebook recovery_replication.ipynb
   ```

3. **Visualization**:
   ```bash
   jupyter notebook visual_script.ipynb
   ```

## 📊 Data Description

### Network Attributes (25 total)

The analysis includes 25 structural attributes grouped into 6 categories:

#### 1. Structural Size & Connectivity
- Number of Nodes
- Number of Edges  
- Average Degree
- Average Shortest Path Length
- Network Diameter

#### 2. Density & Redundancy
- Network Density
- Meshedness Coefficient
- Normalized Number of Loops
- Global Efficiency
- Local Efficiency

#### 3. Topological Cohesion & Hierarchy
- Clustering Coefficient
- Modularity Index
- Assortativity Coefficient
- Transitivity
- Rich Club Coefficient

#### 4. Centrality-based Influence
- Average Degree Centrality
- Average Betweenness Centrality
- Average Closeness Centrality
- Average Eigenvector Centrality

#### 5. Statistical Inequality Measures
- Gini Coefficient of Degree
- Gini Coefficient of Betweenness
- Coefficient of Variation
- Degree Variance

#### 6. Spectral & Algebraic Properties
- Algebraic Connectivity
- Gamma Index

### Metro Systems Analyzed (45 total)

**Large Networks** (>200 nodes):
- New York (463 nodes, 2,076M annual ridership)
- London (369 nodes, 1,411M annual ridership)
- Shanghai (345 nodes)
- Paris (302 nodes)
- Madrid (240 nodes)
- Tokyo (223 nodes, 2,380M annual ridership)
- Delhi (205 nodes, 2,032M annual ridership)

**Medium Networks** (50-200 nodes):
- Berlin, Chicago, Santiago, Boston, Milan, Oslo, Stockholm, Vienna, Valencia, Washington DC, Buenos Aires, Toronto, Rome, Rotterdam, Montreal, Athens, Cairo, Lille, Brussels, Prague, Hyderabad, Dubai, Vancouver, Philadelphia, Lisbon, San Francisco, Nuremberg, Budapest, Bilbao, Lyon, Copenhagen, Amsterdam, Atlanta, Toulouse, Warsaw, Marseille, Naples, Kobe

## 🔬 Methodology

### 1. Network Performance Metrics

**Functionality Ratio**:
```
F(t) = G(t) / G(0)
```
Where G(t) is the size of the largest connected component at time t.

**Resilience Score (AUC)**:
```
R = (1/N) ∫ F(t) dt
```
Normalized area under the performance curve.

### 2. Intervention Strategies

#### Failure Strategies (Node Removal)
1. **DomiRank**: Novel centrality measure considering dominance and propagation effects
2. **Betweenness**: Nodes on shortest paths between others
3. **Degree**: Nodes with highest connectivity
4. **Closeness**: Nodes closest to all others
5. **Eigenvector**: Nodes connected to high-scoring nodes
6. **Greedy**: Iterative optimization for maximum damage
7. **Mean Random**: Random removal with confidence intervals

#### Recovery Strategies (Node Addition)
- Same centrality-based strategies applied in reverse
- Focus on rapid restoration of connectivity

### 3. Statistical Analysis

#### Redundancy Detection
- **Kendall's Tau correlation** analysis
- **Multidimensional Scaling (MDS)** for attribute clustering
- **Mutual Information** for non-linear dependency detection

#### Clustering
- 9 distinct attribute clusters identified
- High mutual information threshold (75th percentile)
- Cluster-specific resilience patterns

## 🏗️ Boston Metro Retrofitting Case Study

### Failure-Focused Retrofit
- **7 strategic connections** added
- Bypass high-betweenness hubs
- Strengthen peripheral redundancy
- **11.9% improvement** in failure resilience

### Recovery-Focused Retrofit  
- **Inner loop densification**
- Balance degree distribution
- Accelerate reconnection
- **3% improvement** in recovery performance

## 📊 Key Results

### Resilience Patterns by Strategy

**Most Damaging Failures**:
- DomiRank, Betweenness, Degree, Greedy strategies
- Target critical network hubs

**Most Effective Recovery**:
- DomiRank and Greedy strategies
- Prioritize high-impact restorations

**Random vs. Targeted**:
- Random strategies show gradual degradation
- Targeted strategies create rapid breakdown

### Attribute-Strategy Relationships

**Failure Resilience Drivers**:
- Cluster 1: Connectivity and efficiency metrics
- Cluster 5: Average betweenness centrality  
- Cluster 4: Modularity index

**Recovery Resilience Drivers**:
- Cluster 8: Degree heterogeneity and inequality
- Cluster 2: Loops and meshedness
- Cluster 9: Betweenness inequality

## 🎯 Applications

### For Urban Planners
- Identify vulnerable network components
- Prioritize infrastructure investments
- Design resilient metro expansions

### For Emergency Managers
- Understand failure propagation patterns
- Develop targeted recovery strategies
- Prepare for cascading disruptions

### For Network Designers
- Optimize topology for resilience
- Balance efficiency and robustness
- Implement redundancy strategies

## 📚 Citation

If you use this code or data in your research, please cite this repo:

## 👥 Authors

- **Orijeet Mukherjee** - Northeastern University (mukherjee.o@northeastern.edu)
- **Dongqin Zhou** - Northeastern University (d.zhou@northeastern.edu)  
- **Ashis Pal** - Northeastern University (ashispalrony@gmail.com)
- **Jack Watson** - Northeastern University (watson.jac@northeastern.edu)
- **Marta Gonzalez** - UC Berkeley (martag@berkeley.edu)
- **Samrat Chatterjee** - Pacific Northwest National Laboratory (samrat.chatterjee@pnnl.gov)
- **Auroop Ganguly** - Northeastern University (a.ganguly@northeastern.edu) - *Corresponding Author*

## 🏛️ Affiliations

- **Sustainability and Data Sciences Laboratory**, Northeastern University
- **AI for Climate and Sustainability**, Institute for Experiential AI, Northeastern University  
- **Department of City and Regional Planning**, University of California, Berkeley
- **Pacific Northwest National Laboratory**

## 💰 Funding

This research was supported by:
- U.S. Department of Defense (US DOD) Strategic Environmental Research and Development Program (SERDP) project RC20-1183
- U.S. Department of Homeland Security (DHS)
- Northeastern University AI for Climate and Sustainability (AI4CaS) focus area


## 📞 Contact

For questions about this research, please contact:
- **Auroop Ganguly** (a.ganguly@northeastern.edu) - Principal Investigator
- **Orijeet Mukherjee** (mukherjee.o@northeastern.edu) - Lead Researcher

---

*This research contributes to the growing field of urban infrastructure resilience, providing actionable insights for making metro rail systems more robust against diverse threats and disruptions.*
