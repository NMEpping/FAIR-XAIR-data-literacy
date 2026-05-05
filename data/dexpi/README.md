# DEXPI Data Files

This directory contains DEXPI P&ID XML files used by the PSE-KG project.

## Current Files

### C01V04-VER.EX01.xml
- **Source**: DEXPI Reference P&ID
- **Copyright**: © DEXPI e.V.
- **Description**: DEXPI version 1.3 reference P&ID example
- **Content**: 
  - 5 tagged plant items (heat exchangers, pumps, tank)
  - 11 piping network systems
  - 3 actuating systems
  - 4 process instrumentation functions
- **Used in**: All example scripts (01, 02, 03)
- **Reference**: https://gitlab.com/dexpi/TrainingTestCases

## Adding Your Own Files

Place your DEXPI XML files (Proteus export) in this directory and reference them in your scripts:

```python
from dexpi_kg import load_dexpi

model = load_dexpi("data/dexpi/your-file.xml")
```

## File Format

DEXPI files should be:
- XML format (Proteus serialization)
- DEXPI version 1.3 or compatible
- Valid against DEXPI schema
