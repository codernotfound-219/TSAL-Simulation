### REQUIREMENTS:
    - LTSpice Software

### USAGE:
    1. Load the additional modules
        Place the files in the include/ directory in your LTSpice library path.
    2. Load the symbols
        Open these files within LTSpice, and find the component name:
            .subckt <COMPONENT_NAME>
        Right click on the requried component_name and click create_symbol.
        The symbols will now be available under the auto-generated components category.

    3. the .tran 2 directive is used to run the simulation.
    
    4. Probe the output points, say the voltage at drain or current throught the LED.
