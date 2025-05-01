# Automated-Warehouse-DES

**Overview**<br>
This repository contains a comprehensive discrete-event simulation framework for evaluating and optimizing various automated storage and retrieval systems (AS/RS) in warehouse environments. The simulation models different warehouse configurations, storage strategies, and operational policies to provide insights into throughput, efficiency, and cost-effectiveness.

**Technical Details**
- Built with Python using SimPy for discrete event simulation
- Matplotlib for visualization and interactive dashboard
- Implements realistic modeling of mechanical constraints and operational uncertainties
- Validated against real-world warehouse operation patterns

  *Getting Started*<br>
1.	Clone this repository
2.	Install required dependencies: pip install -r requirements.rtf
3.	Run the interactive dashboard: python Automated_Warehouse_Sim.py
4.	To run the ABC storage analysis instead, edit the main execution section at the bottom of the file:<br> 
```python
if __name__ == "__main__":
    # Uncomment one of the following to run specific functions
    # create_interactive_dashboard()
    # analyze_abc_storage_impact()
```

*Requirements*<br>
Python 3.7+, SimPy, NumPy, Matplotlib, Random, GridSpec

<img width="1130" alt="Screenshot 2025-04-30 at 10 04 38 AM" src="https://github.com/user-attachments/assets/bbf58da3-f5b2-4a59-ba99-b20194b8cd31" />

This simulation is run and tested using the following toy example:<br>
"...the distribution of different characteristics of the batch picking operation where the average number of batches in the system at any given time varies between 500 and 2,300 with batch size ranging from 1 to 10. On average, 38% of the batches consist of 10 orders, the maximum allowable size. Daily number of batches is roughly constant, where 66% of the batches are created during morning shift from 5:00 a.m. to 1:00 p.m. On average, a batch consists of six orders, 11 distinct SKUs, and 35 items..."[[1]](#1)

**Key Features**

*Multiple Storage System Types*
- Unit-Load AS/RS: For handling large loads on pallets
- Miniload AS/RS: For handling smaller items in totes or bins
- Shuttle-Based Storage and Retrieval Systems (SBS/RS): For high-density storage with horizontal and vertical transport
- Cube-Based Storage: For high-density grid-based storage with mobile robots [[2]](#2)

*ABC Storage Classification*
- Implements multiple ABC storage curves (20/70, 20/90, 20/50, 20/20)[[3]](#3)
- Simulates how product placement strategies impact picking efficiency
- Analyzes the effects of different product activity distributions on overall warehouse performance

*Order Processing Strategies*
- Batch picking with customizable batch size generation
- Wave picking for time-based order processing
- Cross-docking simulation
- Single and dual command cycles

*Equipment Configuration*
- Configurable number of cranes, shuttles, and robots
- Adjustable speeds, acceleration/deceleration times
- Customizable storage depth (single or double-deep)
- Realistic failure rates and recovery times

<img width="1136" alt="Screenshot 2025-04-30 at 10 01 11 AM" src="https://github.com/user-attachments/assets/e741038a-724c-485f-864b-6e9cf3db80a6" />

*Dynamic Storage Management*
- Dynamic storage reallocation
- Periodic replenishment processes
- Storage reorganization based on demand patterns

*Performance Metrics*
- Throughput (orders per hour), Sliding-window Throughput
- Resource utilization and queue statistics
- Order fulfillment and wait times
- Total operational cost

*Interactive Visualization Dashboard*
- Real-time parameter adjustment
- Visual performance comparison across different configurations
- Throughput, resource usage, and cost analysis graphs
- ABC curve visualization and pick density maps

<img width="1140" alt="Screenshot 2025-04-30 at 9 56 45 AM" src="https://github.com/user-attachments/assets/1093a605-3d5f-4013-bde9-4488963f8424" />
<img width="1139" alt="Screenshot 2025-04-30 at 10 02 14 AM" src="https://github.com/user-attachments/assets/3f1a7b32-0223-41f2-83e4-47b876512bc2" />
<img width="1145" alt="Screenshot 2025-04-30 at 10 02 38 AM" src="https://github.com/user-attachments/assets/00f35710-31a9-4148-b37e-3a437738235c" />

**Applications**<br>
This simulation framework can be used for:
1.	Warehouse Design: Evaluate different AS/RS technologies before investment
2.	Storage Policy Optimization: Compare the effectiveness of various storage assignment strategies
3.	Resource Planning: Determine optimal equipment quantities and configurations
4.	Operational Strategy Testing: Assess batch sizes, wave timing, and order prioritization approaches
5.	Performance Forecasting: Model how the system will perform under varying demand patterns
6.	Cost Analysis: Calculate total operational costs across different configurations
7.	Research and Education: Study warehouse automation concepts and principles

*License*
This project is licensed under the MIT License. See [`LICENSE`](./LICENSE)

**References**<br>
<a id="1">[1]</a>
Bayram, V., Baloch, G., Gzara, F., & Elhedhli, S. (2022). 
Optimal order batching in warehouse management: A data-driven robust approach.
*INFORMS Journal on Optimization*, 4(3), 278–303.

<a id="2">[2]</a> 
Gue, K. R., & Kim, B. S. (2007). 
Puzzle‐based storage systems. 
*Naval Research Logistics (NRL)*, 54(5), 556-567.

<a id="3">[3]</a> 
Yu, Y., deKoster, R. B., & Guo, X (2015). 
Class‐based storage with a finite number of items: Using more classes is not always better. 
*Production and Operations Management*, 24(8), 1235-1247.
