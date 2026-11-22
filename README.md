# TerraDefenders

## Website Build Overview

This project provides the officer dashboard website for the **Smart Forest Protection Tower** network.

To build the website, the implementation follows this approach:

1. Set up a clear project structure and basic homepage layout.
2. Implement core dashboard features and design elements using modern web technologies.
3. Ensure responsive behavior and accessibility across screen sizes.
4. Test across major browsers and devices for compatibility and reliability.

---

## Smart Forest Protection Tower — Officer Dashboard

TerraDefenders is the officer dashboard for the **Smart Forest Protection Tower** network.  
Each tower runs local edge AI to detect:

- Motion
- Chainsaw sounds
- Smoke
- CO (carbon monoxide)
- Temperature anomalies

To preserve bandwidth and privacy, towers do **not** stream raw audio.  
Instead, they send compact LoRaWAN alert packets to the backend containing:

- Tower ID
- GPS coordinates
- Event type
- Timestamp
- Confidence score

---

## Dashboard Capabilities

### 1) Real-time Alert Map
- Live geospatial map view of incoming tower alerts
- Marker clustering and event-type filtering (motion/chainsaw/smoke/CO/temp)
- Color-coded severity/confidence visualization
- Click-through to full alert detail and nearby tower context

### 2) Tower Health Monitoring
- Per-tower status panel with:
  - Battery level
  - Solar charging state
  - Last seen timestamp
- Health indicators and warning thresholds for degraded/offline towers
- Fleet-level overview for quick operational awareness

### 3) Alert Lifecycle Management
- Officer workflow states:
  - New
  - Acknowledged
  - Assigned
  - Resolved
- Actions available from alert detail:
  - Acknowledge
  - Assign to officer/team
  - Resolve with notes/outcome
- Full status timeline for accountability and incident tracking

### 4) Alert History & Search
- Historical alert log with pagination
- Search by tower ID, event type, date range, status, and confidence
- Export-ready data structure for reporting/compliance use cases

### 5) Analytics & Insights
- Trend analytics by:
  - Event type
  - Region/geofence
  - Time-of-day/day-of-week
- Tower reliability and uptime patterns
- Incident response performance metrics (ack/assign/resolve times)

### 6) Role-Based Access Control (RBAC)
- Role-scoped access to dashboard capabilities:
  - Officer
  - Supervisor
  - Admin
- Permission boundaries for:
  - Alert actions
  - Assignment controls
  - Analytics visibility
  - Administrative configuration

---

## System Integration Approach

The dashboard integrates with backend services for real-time processing and synchronization:

- Towers transmit LoRaWAN alert packets
- Backend validates, enriches, stores, and broadcasts events
- Frontend subscribes to live updates for map and status refresh
- State transitions (ack/assign/resolve) are persisted and propagated in real time
- Health telemetry updates continuously inform fleet status widgets

This architecture supports low-bandwidth field deployment while providing officers with immediate, actionable situational awareness.