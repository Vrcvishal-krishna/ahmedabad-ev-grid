# Greater Ahmedabad & Gandhinagar EV Charging Telemetry Command Center

Live operational command center and high-precision telemetry engine for the Greater Ahmedabad & Gandhinagar metropolitan area across the Sabarmati, SG Highway, and GIFT City corridors.

### Network Coverage
- **Metropolitan Grid:** 188 deduplicated public charging hubs
- **Hardware Capacity:** 377 physical guns | 22,350.0 kW installed grid load
- **CPO Integration:**
  - Statiq Network: 188 sockets
  - ChargeZone (Gujarat HQ): 102 sockets
  - Tata Power EZ Charge: 53 sockets
  - Jio-bp pulse (GOBP): 34 sockets

### Architecture & Standby Policy
- **Zero Synthetic Data:** 100% genuine hardware telemetry directly queried from CPO cloud APIs and OCPP gateways.
- **Standby Baseline:** Default state is locked at `{"running": false}` (0 active charging, real Available/Faulted baseline). Polling daemon activates strictly when triggered via `[▶ START LIVE TELEMETRY]`.
- **Zero Cross-City Contamination:** Isolated registry bounded strictly between latitudes 22.85–23.30 N and longitudes 72.40–72.78 E.

### Deployment
Configured for automated zero-dependency deployment on Render using standard Python HTTP server and SQLite:
```bash
python app.py
```
