# Texas School Mobility Efficiency & Activity System (TxSMEAS)

**USDOT University Transportation Center Grant #69A3552348329**  
**Center for Efficient Mobility (CEM) — Project #02-09-TTI**  
**Project Title:** *Health and Activity Impacts of Student Commute Modes*  
**Principal Investigator:** Minjie Xu, Texas A&M Transportation Institute (`m-xu@tti.tamu.edu`)

---

## System Overview
**TxSMEAS** is an open-access, browser- and mobile-compatible decision-support system integrating four analytical modules:
1. **Statewide Texas ISD Dashboard (All 1,019 Public ISDs):** Interactive GIS map and efficiency matrix across all 20 ESC regions and 254 Texas counties (9,513 campuses, 5.70M students), featuring deep-dive comparative benchmarks for **Austin ISD**, **San Antonio ISD**, **Fort Worth ISD**, **Round Rock ISD**, and **Leander ISD**.
2. **Client-Side Mobile GPS & Mode-Shift Physical Activity Simulator:** Privacy-preserving HTML5 Geolocation route calculator and district-level traffic operations simulator quantifying door-to-door travel minutes, morning drop-off queue delay savings, and daily student Moderate-to-Vigorous Physical Activity (MVPA) gains.
3. **Open-Source 20-Item Local ISD Commute Audit Survey Toolkit:** Digitized self-assessment version of the Task 2 parent survey instrument with 5-axis readiness radar diagnostics and instant JSON/CSV export.
4. **PRISMA Meta-Analysis & Elasticity Engine (*k* = 42 Studies, Cumulative *N* = 186,456):** Interactive random-effects forest plot explorer and searchable 42-study reference table with direct DOI links.

## Authoritative Open-Data Sources & Derivation Equations
1. **Texas Education Agency (TEA) Public Open Data Portal & TAPR:** District IDs (`TEA_ISD_ID`), ESC Regions (01–20), Campus Counts, K–12 Enrollment, and GIS boundaries (`https://schoolsdata2-tea-texas.opendata.arcgis.com/`).
2. **NCES Common Core of Data (CCD):** 12-category urban-centric locale classifications (`Urban`, `Suburban`, `Town`, `Rural`) (`https://nces.ed.gov/ccd/pdf/2026003.pdf`).
3. **Street Network Connectivity & Smart Location GIS (Block Group v3):** Intersection density (`D3b`), 4-way connectivity, and block-group access scores (`https://www.epa.gov/smartgrowth/smart-location-mapping`).
4. **National Household Travel Survey (NHTS) — TxDOT Texas Add-On:** K–12 school trip mode shares, trip durations, distance distributions, and parent work trip-chaining rates (`https://nhts.ornl.gov/media/assets/2018_NHTS_Workshop_E-Circular_238.pdf`).
5. **TxDOT Crash Records Information System (CRIS):** School-zone pedestrian/cyclist safety records and morning drop-off queue delay parameters (`https://cris.dot.state.tx.us/public/Query/`).
6. **PRISMA Meta-Analysis Database (*k* = 42 Studies, *N* = 186,456):** Pooled Odds Ratios and daily MVPA minute gains by commute mode.

### Core Equations
* **Equation 1 (ISD Composite Efficiency Score, 0–100):** `Eff_i = 0.35(R_i) + 0.25(C_i) + 0.25(100 - Q_i) + 0.15(A_i)`
* **Equation 2 (1-Way Door-to-Door Travel Time, min):** `T_m = (D / V_m) * 60 + W_c + I(m=car) * Q_drop`
* **Equation 3 (Round-Trip Daily MVPA & District Queue Savings):** `MVPA_day = 2 * T_active * alpha_m` and `Hrs_saved = (E_i * S_car * Delta_s * 0.82 * Q_i) / 60`
