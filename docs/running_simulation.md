# Running the Simulation

## Requirements

- LTspice

## Usage

### 1) Open the schematic

- Open `RED_LIGHT_SYSTEM.asc` in LTspice.

### 2) Make sure the custom model is discoverable

This project includes an additional SPICE model:

- `include/tl431.mod`

Place (or reference) the `include/` directory so LTspice can find it.

Common approaches:

- Add the directory to LTspice’s library search path
- Or copy the `.mod` file into your LTspice `lib/sub/` directory

### 3) (If needed) generate symbols for subcircuits

If you open a model file and see a subcircuit definition like:

```spice
.subckt <COMPONENT_NAME> ...
```

You can:

1. Right-click the subcircuit name
2. Choose “Create Symbol”

LTspice will then list the symbol under an auto-generated category.

### 4) Run the transient simulation

This simulation uses a transient run (for example, `2 s`):

```spice
.tran 2
```

Click the “Run” button to start the simulation.

### 5) Probe outputs

Probe useful points such as:

- Voltage at the NMOS drain (LED node)
- Current through the LED branch

Tip: If you don’t see the expected flashing, first verify the comparator output and the 555 timer output independently, then verify the AND output.
