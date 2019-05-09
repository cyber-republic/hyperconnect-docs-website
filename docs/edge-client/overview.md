# Edge Client Overview

The Edge Client is the software component that runs on the IoT device and can be used with a Graphical User Interface (GUI) or via Command Line (Terminal).

## Edge Client Hosts
- Linux (based) OS: Raspbian, Ubuntu Core, etc.
- Windows OS: IoT Core
- Android OS: Android Things

## Main Features
- Connect to peer-to-peer carrier network
- Connection administration (add, remove, block)
- Manage sensors (add, remove, modify)
- Manage sensor logic with built-in compiler
- Test and validate sensor logic
- Calculation of data averages (interval & frequency based)
- Manage events (add, remove, enable, disable)
- Notifications (events, connections, errors, warnings)
- Local storage of sensor reading history
- Graphs from sensor readings
- Connect multiple clients to form event groups
- Distributed file storage (Elastos Hive)
- Offline messaging
- Update Client
- Backup / Restore
- Audio / Video file sharing
- Live streaming

### Optional
- Elastos DittoBox (ownCloud)

### Integration possibilities
- Blockchain
- Machine Learning
- Home Assistant
- Other services with SDKs

### Program Components
- Elastos Native Carrier
- Elastos Java SDK
- JavaFX Framework (only for GUI version)
- SQLite Database
