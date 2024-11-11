#  Implementation-Analysis-of-Ring-Oscillator-using-Cadence-EDA-Tools
Skill Assessment 2 
#### Name   : Sachin B
#### Reg.No : 212222060207

### Title: Implementation & Analysis of Ring Oscillator using Cadence EDA Tools  

### Aim:
To design and implement a ring oscillator using Cadence EDA tools, simulate its behavior, and analyze its performance metrics, such as oscillation frequency, power consumption, and stability, for a deeper understanding of oscillator circuits.

### Tools Required:
- Personal Computer
- Cadence Virtuoso Software

---

### Schematic Simulation - Procedure for Creating the Schematic Simulation - Commands to get into Cadence

1. **Open Terminal:**
   - Right-click and open a terminal window.
   - Enter the following commands:
     - `csh`
     - `source /cadence/install/cshrc`
     - `virtuoso`

---

### Procedure for Schematic Simulation Using Cadence

1. **Open Cadence Interface:**
   - After launching, two windows should open:  
     i) `Virtuoso/Command Interpreter Window (CIW)`  
     ii) "What's New" window

2. **Close the “What's New” Window.**

3. **Use the CIW Window for Further Processing.**
   - Follow the steps below to create and configure the ring oscillator:

#### i) **Creating a New Library:**
   - Go to `File` → `New` → `Library`
   - Enter the library name, e.g., `RingOscillator_Lab`
   - Select `Attach to an existing technology library` and click **OK**
   - Attach the library to the technology library `gpdk045`, then click **OK**

#### ii) **Creating the Schematic Cell View:**
   - In the CIW, navigate to `File` → `New` → `Cell View`
   - Set up the new file with the following details:
     - **Library:** The library you created earlier
     - **Cell:** RingOscillator_Schematic
     - **Type:** Schematic
   - Click **OK**

   - **Adding Components:**
     - Use the instance menu (shortcut key `I`) to add instances.
     - Browse for components in the library (e.g., `gpdk045`) and select `nmos1v` and `pmos1v` transistors.
     - Add the necessary inverters to form an odd number of stages (usually three or five) to ensure oscillation.

   - **Creating Connections:**
     - Add input and output pins for the oscillation signal.
     - Use the wire tool to connect each inverter in a loop, with the output of the last inverter feeding into the input of the first.

   - **Check and Save:**
     - Verify the schematic and click **Check and Save**.

![Screenshot 2024-11-11 013014](https://github.com/user-attachments/assets/cbbaafba-9772-4eed-9d0d-ae8cc894b767)


#### iii) **Creating the Symbol for the Schematic Cell View:**
   - In the schematic window, go to `Create` → `Cell View` → `From Cell View`
   - The `Cell View from Cell View` window will appear. Ensure the library name, cell name, and view name are correct. Click **OK**.
   - A default symbol will be generated. Customize it if needed.
   - Verify the pin positions, then click **OK** to finalize the symbol.

#### iv) **Creating a New Test Cell View:**
   - Go back to the CIW window.
   - Select `File` → `New` → `Cell View`
   - Set up the new file with the following details:
     - **Library:** The one you created
     - **Cell:** Use a different cell name, e.g., `RingOscillator_Test`
     - **Type:** Schematic
   - Click **OK**

   - **Configuring the Test Schematic:**
     - Follow the steps in (ii) to make connections, but in this cell, include additional components (like power supply and ground) to test the ring oscillator.

---
![Screenshot 2024-11-11 013225](https://github.com/user-attachments/assets/d87c6868-2568-433f-b4bd-3636639128bd)

### Analog Simulation by Spectre

1. **Open Analog Design Environment (ADE):**
   - In the test cell view window, go to `Launch` → `ADE L` (Analog Design Environment).

2. **Set Up Simulation:**
   - Execute `Setup` → `Simulation/Directory/Host`
   - Choose **Spectre** as the simulator and click **OK**

3. **Transient Analysis Settings:**
   - Go to `Analysis` → `Choose`
   - Select **Transient** as the analysis type, and set the duration according to the expected oscillation frequency. Click **OK**

4. **Plotting the Oscillation Signal:**
   - Go to `Outputs` → `To be Plotted` → `Select on Schematic`
   - Select the output wire of the ring oscillator to observe oscillations.

5. **Run the Simulation:**
   - Execute `Simulation` → `Netlist and Run`


![Screenshot 2024-11-11 014045](https://github.com/user-attachments/assets/05e4c42e-880a-42ca-84a1-371325d377c0)

---

### Results:
The design and implementation of the ring oscillator using Cadence EDA tools were successfully completed. The simulated results demonstrated a stable oscillation waveform, confirming the proper functionality of the oscillator circuit. Key performance metrics, such as oscillation frequency and power consumption, were measured and analyzed, matching theoretical predictions.

--- 
