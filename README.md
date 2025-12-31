# CMOS Ring Oscillator PUF (UMC 180nm)

This repository contains the B.Tech project **“Design and Fabrication of a CMOS PUF Circuit using UMC 180nm Technology”**, implemented and simulated in **Cadence Virtuoso**.[file:4]

## Overview

Physical Unclonable Functions (PUFs) exploit unavoidable CMOS process variations to generate **device-unique digital signatures** for secure identification, authentication, and key generation.[file:4]  
This project implements a **Ring Oscillator (RO) based PUF** using the **UMC 180nm CMOS** process.[file:4]

## Architecture

The RO-PUF architecture consists of:[file:4]

- Multiple identical **ring oscillators** (ROs) designed from CMOS inverters  
- **AND-gate based enable logic** to control oscillator activation  
- **2:1 multiplexers (MUXes)** to select RO pairs based on the applied challenge  
- A **10-bit synchronous counter** to measure oscillation frequency over a fixed time window  
- A **digital comparator** to generate a **1-bit response** by comparing two RO counts  

Due to random process variations (threshold voltage, channel length, parasitics), each RO exhibits a slightly different frequency, which becomes the entropy source for the PUF.[file:4]

## Features

- Implemented in **Cadence Virtuoso** using **UMC 180nm PDK**  
- **Four ring oscillators** in the prototype (scalable to larger arrays)  
- Challenge–response mechanism using MUX-based RO selection and counter–comparator chain  
- Demonstrates key PUF properties: **uniqueness, reliability, and unpredictability** through waveform and count analysis.[file:4]  

## Repository Structure

> Adjust this section according to your actual files.

- `schematics/` – Cadence Virtuoso schematic cells (AND, MUX, inverter, RO, counter, comparator)  
- `netlists/` – Exported netlists for simulation (if shared)  
- `waveforms/` – Plots / screenshots of transient simulations showing RO outputs and PUF responses  
- `docs/` – Report, diagrams, and architecture descriptions  
- `README.md` – Project overview (this file)

## How It Works

1. **Challenge input** selects a pair of ring oscillators via MUXes.  
2. Selected ROs are **enabled** and start oscillating.  
3. A 10-bit counter measures oscillation counts for each RO during a fixed time window.  
4. The comparator outputs `1` if RO1 is faster than RO2, else `0`, forming a **1-bit PUF response**.[file:4]  
5. Repeating this for multiple challenges builds a **challenge–response pair (CRP) set** for authentication.[file:4]

## Applications

- Device identification and authentication  
- Secure key generation without storing keys in non-volatile memory  
- Anti-counterfeiting in embedded, IoT, and RFID systems.[file:4]

## Future Work

- Scale RO array to 32/64/128 oscillators to enlarge CRP space and strengthen security  
- Layout design and silicon fabrication in 180nm CMOS  
- Reliability characterization across **PVT (Process–Voltage–Temperature)** corners  
- Integration with a **Hardware Security Module (HSM)** for real-world secure boot and key derivation.[file:4]

## Authors

- **Lakavath Hari Prasad Naik** – B.Tech, Electrical Engineering, IIT Jodhpur  
- **Mudavath Shiva Sai** – B.Tech, Electrical Engineering, IIT Jodhpur  

Supervisor: **Prof. Harshit Agarwal**, Department of Electrical Engineering, IIT Jodhpur.[file:4]
