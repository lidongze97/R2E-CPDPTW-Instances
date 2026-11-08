# Instances for the robust 2E-CPDPTW

This repository contains the 48 benchmark instances of the paper *Robust Optimization for the Two-Echelon
Crowdsourced Pickup and Delivery Problem with Time Windows under Travel Time Uncertainty*.

## Naming

An instance `C20-S3-H3-L3` has the spatial class `C` (clustered), 20 customer nodes, 3 satellites,
3 crowdsourced couriers (`H`), and 3 lockers (`L`). The other classes are `R` (random) and `RC` (hybrid).

## File format

Each instance is a CSV file in `instances/` with the columns `Name, X, Y, Demand, Left_TW, Right_TW, Serve_Time`.

| Rows | Meaning |
|---|---|
| `1` to `n/2` | pickup nodes, with positive demand |
| `n/2+1` to `n` | delivery nodes, where delivery node `i+n/2` belongs to pickup node `i` and has demand `-q_i` |
| `S1`, `S2`, ... | satellites |
| `L1`, `L2`, ... | lockers (transshipment nodes) |
| `cO1`, `cD1`, ... | origin and destination of each crowdsourced courier, where `Left_TW` of `cO` is the earliest available time |

`X` and `Y` are coordinates, `Left_TW` and `Right_TW` bound the time window, and `Serve_Time` is the service
time. All other parameters, such as capacities, costs, and the uncertainty sets, are given in Section 5.1 of the
paper.
