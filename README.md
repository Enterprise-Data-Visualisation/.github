# Enterprise Data Visualisation Platform (EDVP)

[![React](https://img.shields.io/badge/Frontend-React%2018-blue)](https://github.com/Enterprise-Data-Visualisation/react-client)
[![Python](https://img.shields.io/badge/Backend-Python-yellow)](https://github.com/Enterprise-Data-Visualisation/asset-service)
[![Architecture](https://img.shields.io/badge/Architecture-Decoupled-green)](#system-architecture)

**A high-performance, decoupled visualization system designed to render complex asset data for enterprise analytics.**

## 🚀 Overview

The **Enterprise Data Visualisation Platform** is a micro-service based solution designed to bridge the gap between heavy backend data processing (Python) and high-performance client-side rendering (React). 

Unlike traditional monolithic dashboards, EDVP decouples the **Data Aggregation Layer** from the **Presentation Layer**, allowing for independent scaling and optimized payload delivery for financial datasets.

## 🏗 System Architecture

This platform follows a modern **Consumer-Provider pattern**, tailored for financial data visualization.

```mermaid
graph LR
    User[Client Browser] -->|HTTP/WebSocket| FE[React Frontend]
    FE -->|REST API| BE[Python Asset Service]
    BE -->|Data Aggregation| DS[(Data Sources/CSV)]
    
    subgraph Frontend Layer
    FE
    State[Zustand Store]
    Viz[Plotly/D3 Charts]
    end
    
    subgraph Backend Layer
    BE
    Pandas[Pandas Processing]
    API[FastAPI/Flask]
    end
