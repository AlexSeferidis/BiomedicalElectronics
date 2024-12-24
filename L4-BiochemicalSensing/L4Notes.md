# Lecture Notes

---

- [ ] Have Revised

## Introduction to Chemical Sensors

Let's start with a few definitions:

* **Chemical Sensor** - A device that transforms chemical information, ranging from concentration of a specific sample component to a total composition analysis, into an analytically useful signal

* **Analyte** - Substance or chemical constituent that is undergoing analysis

* **Concentration** - The amount of chemical in a fixed volume, typically measured in Molar (1 Molar = 1 mol/litre)

```{hint} What is the Chemical Sensor's importance to medicine?
:class: dropdown

Good for medical diagnosis and treatment as the body is full of chemical markers: DNA, glucose, pH, lactate.

```

> Chemical sensors are small-sized devices comprising a recognition element, a transduction element, and a signal processor capable of continuously and reversibly reporting a chemical concentration. 

```{figure} ../Images/L4/chemsense.png
:label: csen
:alt: Chemical Sensor
:align: center
```

* **Recognition Element** - Something which combines the molecule
* **Transduction Element** - Something which converts whatever happened into a voltage or current
* **Signal Processor** - Capable of continuously and robustly reporting a chemical reaction

### Desirable and Undesirable Attributes and Characteristics

We have some attributes that chemical sensors should generally have:

* Transform chemical quantities into electrical signals
* Respond rapidly to changes in concentration
* Maintain their activity over along time period
* Be small to help deployment.
* Be cheap to make them affordable.
* Be specific ,i.e. they should respond exclusively to one analyte, or at least be selective to a group of analytes. 

And we also have some more specific **desirable characteristics**:

* **Signal Response**: Output signal should ideally be linearly proportional to target species concentration and noise-free

    * This is because we need to characterise the O/P voltage to a specific molecule. This means we can equate an increase of current to that of concentration of the molecule in molars.

    * If it is non-linear, it makes it difficult to determine our molecule concentration
    

* **Response Time**: Fast response times are desirable since slow sensor response can limit the use in real-time monitoring applications

* **Signal-to-Noise Ratio (SNR)**: The ratio of total signal response to limit of detection (LOD) of target species, the SNR is ideally high

    * SNR reflects the limits of detection, we ideally want it very high

    * You can effectively think of it as the resolution of your chemical sensor

* **Selectivity**: Ideally a sensor should be highly selective, i.e. its signal output originates only from the target species and not from interfering species.

* **Sensitivity**: Defined as the change in signal per unit change in concentration, the sensitivity should be high to discriminate accurately and precisely between small differences in analyte concentration

Below are our **undesirable characteristics**:

* **Non-linearity**: Response is not proportional to the input signal

* **Slow response**: Output is slow to reach a steady-state value

* **Small working range**: Operating range is restricted

* **Low sensitivity**: Sensor can only respond to large input signals

* **Low selectivity**: Interference from other species affects sensor output

* **Baseline drift**: Output varies with time

    * When we put a solid sensor in contact with liquid, when the first contact happens an equilibrium process takes place between a solution and the chemical recognition process.

    * Within that you have some thermodynamics, an exchange of ions

    * The net result is that sensors inherently drift, if it's linear it's ok but if not it's hard to compensate for

* **Sensitivity drift**: Sensitivity varies with time (e.g. due to temperature change)

    * Slope changes over time, making it difficult to recognise molecule concentration.

* **Ageing**: Sensor output changes with time

* **Interference**: Output is sensitive to external conditions, e.g. stray electromagnetic radiation, humidity, etc.

* **Hysteresis**: Systematic error in the input-output curve

    * Following different trend to return to original concentration, making it difficult to determine sensor O/P

* **Noise**: Output contains an unwanted random signal

### Types of Chemical Sensors

```{figure} ../Images/L4/chemsensetypes.png
:label: csentypes
:alt: Chemical Sensor Types
:align: center
```

There are a number of categories of chemical sensors:

* **Electrochemical sensors**: based on the measurement of redox chemistry of chemical species; among them voltammetric and potentiometric devices, chemically sensitized field effect transistor (CHEMFET) and potentiometric solid electrolyte gas sensors

* **Electrical sensors**: based on the measurement of a change of electrical property of a device; include those with metal oxide and organic semiconductors as well as electrolytic conductivity sensors

* **Optical sensors**: based on the measurement of light ; include those following absorbance, reflectance, luminescence, fluorescence, refractive index, opto-thermal effect and light scattering.

* **Mass sensitive sensors**: based on the measurement of a change in mass ; include piezoelectric devices and those based on surface acoustic waves

* **Magnetic sensors**: (mainly for oxygen) based on paramagnetic gas properties

* **Thermometric sensors**: based on the measurement of the heat effect of a specific chemical reaction or adsorption which involves the analyte

There are also other sensors, mainly based on emission or absorption of radiation.

## Electrochemistry

**Electrochemistry** is the study of redox chemistry of chemical species and the potentials and currents associated with them.

We make measurements **IN** electrochemical cells consisting of 2 or more electrodes and the electronic circuitry for controlling and measuring the current and potential.

The **concentration** of the analyte is normally transduced as a voltage or current depending on what type of measurement you conduct

### Redox Reactions

Redox reactions (**reduction-oxidation reactions**) are chemical reactions where electrons are transferred between atoms, molecules, or ions.

* **Oxidation** - Loss of electrons
* **Reduction** - Gain of electrons

Example of Oxidation: 

```{math}
Zn \rightarrow Zn^{2+} + 2e^-
```

Here zinc loses 2 electronis and becomes a $Zn^{2+}$ ion. We must add the 2 electrons to balance the equation.

Example of Reduction:

```{math}
Cu^{2+} + 2e^- \rightarrow Cu
```

Here, copper ions $Cu^{2+}$ gain two electrons to form copper metal, so it’s reduced.

* **Oxidizing Agent**: Substance that is reduced and helps another to oxidize.
* **Reducing Agent**: Substance that is oxidized and helps another to reduce.

### The Galvanic Cell

```{figure} ../Images/L4/galvaniccell.png
:label: gcell
:alt: Galvanic Cell
:align: center
```
The galvanic cell converts **chemical energy** into **electrical energy** via spontaneous **redox reactions**.

This involves 2 **electrodes**:

1. **Anode** - The electrode where oxidation (loss of electrons) occurs
2. **Cathode** - The electrode where reduction (gain of electrons) takes place

Each **electrode** is placed in an **electrolyte solution** containing ions related to the electrode material. For example, if one electrode is made of zinc, the electrolyte may contain zinc ions ($Zn^{2+}$).

A salt bridge maintains electrical neutrality in the solutions by allowing ions to move between the two electrolyte solutions without directly mixing. It prevents the build-up of charge that would otherwise stop the flow of electrons.

#### How it works

1. Spontaneous redox reaction occurs, species at anode loses electrons (oxidation) while species at cathode gains electrons (reduction)
2. Electrons flow from anode to the cathode via an external wire, this generates a current so we can measure potential difference
3. to maintain charge balance ions in electrolyte move via salt bridge.

---

[This specific example](#gcell) is that of a **Zinc-Copper** Galvanic Cell.

* Anode (Zinc electrode): Zinc metal ($Zn$) loses two electrons and becomes $Zn^{2+}$ ions, which go into the solution.

```{math}
Zn \rightarrow Zn^{2+} + 2e^-
```

* Cathode (Copper electrode): Cu²⁺ ions in solution gain two electrons to form copper metal (Cu), which plates onto the cathode.

```{math}
Cu^{2+} + 2e^- \rightarrow Cu
```

The overall reaction is:

```{math}
Zn + Cu^{2+} \rightarrow Zn^{2+} + Cu
```
---

### Redox Potential 

In electronics we measure the voltage relative to ground whereas in chemistry they measure it relative to what's called the **standard hydrogen electrode (SHE)**.

**Therefore the potential of each ion has been determined with reference to the SHE**

```{figure} ../Images/L4/ionpotential.png
:label: ionpotent
:alt: Ion Potential Table
:align: center
```
[This table](#ionpotent) allows us to take our 2 known metals and calculate what the voltage will be when we put them together 

To calculate the electrode potential of an electro chemical cell in non-standard conditions, we use the following **Nernst Equation**

```{math}
E = E^\circ + \frac{RT}{nF}ln(\frac{C_O}{C_R})
```

Where:

* $E$ is the electrode or cell potential under non-standard conditions
* $E^\circ$ is the half cell standard potential
* $C_O$ is the concentration of oxidised species
* $C_R$ is the concentration of reduces species
* $n$ is the number of electrons
* $T$ is the temperature in Kelvin
* $R$ and $F$ are the universal gas constant and Faraday constant respectively

---

#### Example

The net reaction of a voltaic cell constructed from a standard zinc electrode and a standard copper electrode is obtained by adding the two half reactions together (See [table](#ionpotent))

```{figure} ../Images/L4/exampleredoxpotent.png
:label: exredoxpot
:alt: Example Redox Potential
:align: center
```
---

## Principles of Electrochemical Sensors

Let's look at the main categories of electrochemical measurement:

1. **Potentiometry**

    * This refers to the measurement of potential difference generated between an ion-selective electrode (ISE) - an electrode selected to the ions you're looking for - and a reference electrode.

    * The potential difference between them is caused by a difference of concentration between the sample (analyte) solution and a reference solution

    *  This gives you an indication as to what ion your ISE is selective to

2. **Voltammetry**

    * This refers to imposing a voltage (waveform potential) onto the electrodes (reference electrode)

    * If that voltage hits the redox potential, they'll start to generate a current and you measure that current.

    * We do a voltage scan and check when the max current is O/P.

    * When the voltage is fixed, this is referred to as amperometry

3. **Amperometry**

    * This refers to applying a fixed potential to a reference electrode

    * This causes a species of interest to be oxidised or reduced and thus current flows between this electrode and a 'working' electrode

    * We therefore measure the current

4. **Conductimetry**

    * We measure the conductance between electrodes

#### Naming of Electrodes

```{figure} ../Images/L4/namingelectrodes.png
:label: nameelec
:alt: ElectrodeNames
:align: center
```

* The WE is always sensitive to the molecule you are looking for

[In this configuration](#nameelec), with the op-amp, it's called a **potentiostat**

### Cyclic Voltammetry

* Cyclic Voltammetry (CV) is one of the more powerful and widely used techniques in electrochemistry;
* It involves the study of the currents associated with redox reactions;
* When the potential is swept in a linear ramp, in both the forward and reverse directions, between two switching potentials.
* Used to provide a broad overview of the system- identify what’s there.
* Identify the operating potential for amperometry.
* Peak potential allows identification, peak height is proportional to concentration.

#### Typical Waveforms

```{figure} ../Images/L4/CVwaveform.png
:label: CVwave
:alt: CV Typical Waveforms
:align: center
```

[Here](#CVwave) we do our **sweep** using a **triangular wave**, sweeping up and down. This is usually from 0-1V as post redox potentials are in the sub-volt range.

Then we get a **current peak** $i_p$ where the **redox reaction** happens.

* **Potential** at which the peak occurs identifies **what there is**
* **Amplitude** of peak identifies how **much there is**


#### Potentiostat 

```{figure} ../Images/L4/potentiostat.png
:label: CVpotentstat
:alt: Potentiostat
:align: center
```

To carry out Cyclic Voltammetry and Amperometry we need a **potentiostat**. It applies dynamic voltage onto the electrodes.

#### Peak Redox Current (Randles-Sevcik Equation)

In cyclic voltammetry, when a potential is applied to the electrode, an oxidation or reduction peak appears in the current vs. voltage plot (voltammogram). Using the **Randles-Sevcik Equation**, the peak current can be analyzed to extract information about the species in solution and the nature of their interaction with the electrode surface.

```{math}
i_p = 2.69 \text{ x } 10^5 \cdot n^{\frac{3}{2}} \cdot A \cdot D^{\frac{1}{2}} \cdot C \cdot  v^{\frac{1}{2}}
```

* $n$ = number of electrons transferred/molecule
* $A$ = electrode surface area (cm2)
* $C$ = concentration (mol/cm-3)
* $D$ = diffusion coefficient (cm2 s-1)
* $V$= scan rate (V/s)

Important to consider when designing the size of your electrodes and the maximum current you want to detect for a given concentration.

### Amperometry

```{figure} ../Images/L4/3electrodemeasure.png
:label: 3elec
:alt: 3 Electrode Measurement System 
:align: center
```

Unlike Voltammetry, in **Amperometry** we impose a **fixed potential** on the solution via the Reference Electrode.

If this potential is the **redox potential** of the analyte being measured, a **redox reaction** will start to occur. **Electrons** will be generated at the **working electrode** surface. 

Current in the circuit is proportional to the rate of generation of electrons. **Current** is therefore **proportional to the concentration of the analyte**.

```{figure} ../Images/L4/amperometricsensor.png
:label: ampsense
:alt: Amperometric Sensor 
:align: center
```

The most common amperometric sensor is a glucose sensor. The **working electrode** is the one that identifies the glucose. There's no surprise therefore it is the biggest as we want to **maximise the current**.

```{figure} ../Images/L4/glucosesensor.png
:label: glusense
:alt: Glucose Sensor 
:align: center
```

[Here](#doseresponse) we can see a typical dose response. We are used to having linear curves but every time the concentration is changed, it takes time for the concentration to settle.

```{figure} ../Images/L4/typicaldoseresponse.png
:label: doseresponse
:alt: Typical Glucose Sensor Response 
:align: center
```

#### Circuitry

So we've established for amperometry we need something to apply a **fixed potential** and something to **measure current**. Therefore we have some requirements:

* Requires current to flow through a fixed solution potential
* Voltage must be stable and not fluctuate with changing current
* Current must be buffered for further processing / conversion (e.g a A/D converter)

```{figure} ../Images/L4/amperometrycircuit.png
:label: ampcirc
:alt: Typical Amperometry Circuit 
:align: center
```

Below is the typical architecture:

```{figure} ../Images/L4/amperometricarchitecture.png
:label: amparch
:alt: Typical Amperometry Architecture 
:align: center
```

So we have:

* A potentiostat to apply the fixed redox potential to establish the $V_{\text{cell}}$ between the reference and working electrode

* A microcontroller and D/A converter which allows us to program what that voltage is

* A transimpedance amplifier which measures the amount of current flowing through the working electrode and then converts it into something to put into an A/D converter, which is then sampled with the microcontroller

---

#### Potentiostats

##### Electrodes

Before we go about designing circuit, we should first get an indiction of how these electrodes work at a surface level:

Similar to [last week](#elec-intru-inter) when we looked at interfaces, we can represent an electrochemical cell as a **grouping of resistors and capacitors**.

**NOTE: THIS IS JUST FOR MODELLING PURPOSES**

```{figure} ../Images/L4/RCcellmodel.png
:label: rccellmod
:alt: Electrochemical Cell Model with RC Circuit 
:align: center
```

##### Biasing the Solution

We need to apply a fixed voltage between the reference and working electrode. It should come as no suprise you can use an amplifier.

```{figure} ../Images/L4/potentiostatcircuit.png
:label: potentcircuit
:alt: Potentiostat Circuit 
:align: center
```

Let's break this circuit down:

* RE & WE should always be at a fixed stable potential.
* Control amplifier should be able to source/sink Redox current and establish a fixed closed loop potential.
* Voltage of chemical cell $V_{\text{cell}} = V_{\text{WE}}-V_{\text{RE}}$
* The voltage gain and input offset voltage of the control amplifier define the accuracy.
* Typically Gain > 104 and offset voltage < 10mV.
* Also need to consider output voltage swing and noise and bandwidth.
* With this configuration $V_{\text{in}}$ needs to be negative to establish positive $V_{\text{cell}}$.

So the **problem** with this configuration is that we have to **input a negative cell potential** to get the right $V_{\text{cell}}$. So for glucose $V_{\text{in}} = -0.7$.

That might be ok if you were only using discrete systems, however if we are using CMOS ASIC, for example, then we only work with **positive voltages** so this circuit wouldn't work. The solution is [this circuit](#pospotentiostat)

```{figure} ../Images/L4/pospotentiostatcircuit.png
:label: pospotentiostat
:alt: Positive Vin Potentiostat Circuit 
:align: center
```
Let's break this down:

* Allows application of a positive $V_{\text{in}}$ to establish a positive $V_{\text{cell}}$. ($V_{\text{in}} = -V_{\text{RE}}$)
* Good when driving from a single supply DAC
* Minimal RE leakage through voltage buffer

There are also implementations where you can ground the counter electrodes. This is often used to measure current, you can stick a differential instrumentation amplifier on the WE node and measure the current going through.

```{figure} ../Images/L4/groundedCEpotentiostatcircuit.png
:label: gndCEpotentiostat
:alt: Grounded CE Potentiostat Circuit 
:align: center
```

Let's break this grounded CE implementation:

* Now have a grounded CE implementation
* $V_{\text{cell}} = V_{\text{in}} = V_{\text{WE}}-V_{\text{RE}}$
* Allows single supply operation
* WE is susceptible to noise and interference
* Cannot supply multiple working electrodes

Again the problem with this circuit is that the **WE** now picks up all the noise from the **control amplifier**. Also you cannot supply multiple WEs, this means if you want an array of electrodes in [this configuration](#pospotentiostat) you can but not in the one above.

##### Current Measurement

How do we satisfy the requirement that we need at a ground node, and be nice and quiet, but **also measure current**?

You put what's called a **Trans-Impedance Amplifier**

```{figure} ../Images/L4/potenttransimpedanceamp.png
:label: transimpedance
:alt: Potentiostat Circuit with Transimpedance Circuit 
:align: center
```
So what does this circuit do?

* Transimpedance Amplifier - Converts current to voltage through a buffered resistor. $V_{\text{out}} = I_F R_M$
* WE sits at virtual ground
* Resistor size must be chosen so as not saturate the amplifier and maximise dynamic range $I_{F(\text{max})} = V_{DD}/R_M$
* R_M can be programmable and have a tunable gain allowing measurement of very small current

However we have some drawbacks:

* Resistor can add thermal noise to measurement. This is a problem when trying to measure small currents with large resistors
* Large resistors are generally difficult to realise in ASICs
* WE is at a virtual ground and thus susceptible to noise and interference pick up

So to avoid using a large resistance we can instead use a **capacitor implementation**

```{figure} ../Images/L4/capacitortransimpedance.png
:label: capactransimpedance
:alt: Transimpedance Circuit with Capacitor Implementation 
:align: center
```
Here's what we've done:

* Switched to Capacitor implementation
* Sensor current charges up capacitor. $V_{\text{out}} = I_F (T/2C_M)$
* Does not need resistors which take up a lot of space when large
* To measure small currents we can just increase the clock period $T$ !!
* Can add programmable gain through $C_{\text{range}}$

The beauty of this circuit is that we no longer need big resistors, you can tune the impedance of the network according to the period of your clock, so you can measure really small currents, just increase the clock periods.

##### Some More Potentiostats for Reference

Here's some more potentiostats for reference and example (likely not in exam):

```{figure} ../Images/L4/referencepotentiostat1.png
:label: referencepotent1
:alt: Reference Potentiostat 
:align: center
```

[Here's one](#referencepotent1) (on the left) where you can measure again from the working electrode through a resistor.

In order to maintain $V_{\text{cell}}$ at a constant potential, we get a bootstrap circuit that ensures when the working electrode voltage changes it uplifts the left side's voltage and inturn the reference voltage.

So effectively the $V_{\text{cell}}$ potential is always shifting, but always constant in this circuit

On the right we have a similar topology that does exactly the same thing.

---

We also have the configuration mentioned before to do with adding a differential amplifier.

```{figure} ../Images/L4/referencepotentiostat2.png
:label: referencepotent2
:alt: Reference Potentiostat 
:align: center
```

Here's we insert a resistor in the current path of the CE, this way we can measure the voltage generated using an instrumentation amplifier.

The WE is connected to true ground so it is not vunerable to pick up AND there are NO active components in signal path so it has better stability.

The only limitation on this circuit is ensuring $I_F R_M$ voltage generated doesn't saturate the control amplifier

##### ASIC Implementation

When working with ASIC, the one thing you need to bear in mind is 
that ground is actually the common mode voltage, whch is typically $V_{DD}/2$.

* So if operating of a single supply, then need to operate everything with reference to $V_{DD}/2$.
* Need to guarantee a stable common mode voltage $V_{DD}/2$
* I/P drive voltage is limited to $\pm V_{DD}/2$

```{figure} ../Images/L4/ASIC.png
:label: ASICimp
:alt: ASIC Potentiostat 
:align: center
```

```{note} Note!

Here we actually can use a negative potential because the difference $V_{DD}/2 - E_i$ is positive
```

##### Generating Voltage

The circuit below is how how we would generate the voltage on the chip. We need to ensure that there is stable voltage reference generation on chip.

```{figure} ../Images/L4/voltagegen.png
:label: voltagegenerator
:alt: Integrated Voltage Reference Generation 
:align: center
```
* We use a bandgap circuit to give a stable voltage reference, which is insensitive to temperature.
* Then we just have a bunch of current mirrors with resistors
* At each output of the resistance, we have a different voltage reference which can be used to drive the potentiostat

### Potentiometry

Potentiometric is a measurement of votlages between a reference electrode and an **ion selective electrode**

What is an **ion selective electrode**?

```{figure} ../Images/L4/ionselectivelectrode.png
:label: ionselect
:alt: Ion Selective Electrode 
:align: center
```
The ion-selective electrode is typically an electrode with an internal solution which is highly saturated and it measures the potential difference between that internal solution and the solution that you are measuring.

* It uses a membrane to establish a fixed potential
* There is a change in potential across a glass membrane when its two sides are in solutions of different concentration

The voltage you measure can be given by the **next equation**. It is effectively a relation between the internal ions in the stable reference electrode, and the ions in your sample

```{math}
E_{\text{mem}} = E_{\text{asym}} - \frac{RT}{zF}ln(\frac{(a_A)_{\text{int}}}{(a_A)_{\text{samp}}})
```
Where:

* $(a_A)_{\text{samp}}$ the analyte’s concentration (activity) in the sample
* $(a_A)_{\text{int}}$ the concentration (activity) of analyte in the ionselective electrode’s internal solution.
*  $E_{\text{asym}}$ the sum of constant redox constant potentials (it's constant)
*  $z$ or $n$ is the analyte's charge

The max we can get out of this is called the **Nernst potential** at **59mV**

At **room temperature** we can simplify the membrane potential equation by combining known constants into a single term $K$.

```{math}
E_{\text{cell}} = K + \frac{0.05916}{z}log(a_A)_{\text{samp}}
```

Here's an example of how it works:

```{figure} ../Images/L4/concentrationcalc.png
:label: conccalc
:alt: Concentration Calc 
:align: center
```

#### Circuit Requirements

So how do we measure that potential?

We need something that doesn't allow a current to flow but can measure voltage.

* Need to emasure the Cell voltage $E_{\text{cell}}$
* Requires high I/P impedance and no disruption of the measured potential, i.e no current flow
* Use a high impedance transducing element like a MOSFET or OpAmp to measure the electric field generated

```{figure} ../Images/L4/circuitrequirements.png
:label: circuitreq
:alt: Circuit Requirements 
:align: center
```

#### Solid State Ion-Selective Electrodes

We can use a transistor **ITSELF** as an ion-sensitive electrode. This is called an **ISFET**.

**The ISFET is a MOSFET transistor whereby the gate becomes your ion-selective electrode**

```{figure} ../Images/L4/ISFET.png
:label: ISFETdiagram
:alt: ISFET Diagram 
:align: center
```
* It is a chemically sensitive transistor
* The chemical sensitivity arises due to an Ion-Selective Membrane deposited on the Gate
* Insulators such as $\text{Al}_2 \text{O}_3, \text{Si}_3 \text{N}_4, \text{SiO}_2$ can make it pH sensitive.
* A change in concentration causes a change in the devices threshold, $V_\text{th}$ which we can monitor

We can also put **ionophores** on the surface to make it sensitive to different ions. When we do this, they are called CHEMFETs.

```{figure} ../Images/L4/ionophores.png
:label: chemfet
:alt: chemfet table 
:align: center
```

These can all be made in CMOS, meaning they are loss cost, can be mass-fabricated, they're small, fast and integrate easily.

Challenges include, chemical sensitivity, sensor drift and failure and temperature dependence.

The **sensing mechanism** of the sensing membrane works as follows: some bio-chemical processes occur, which we can model as 2 capacitors in series. They produce a big amount of charge in the solution which gets reflected on the surface and causes the change in potential.

```{figure} ../Images/L4/sensingmechanism.png
:label: sensemech
:alt: Sensing Mechanism 
:align: center
```

We can treat this whole process as a transistor, with the following macro-model:

```{figure} ../Images/L4/transistormacromodel.png
:label: tranmm
:alt: Transistor Macro Model 
:align: center
```

* All transistor equations remain the same in the linear region, saturation and gm
* The thing that changes is the threshold voltage, which changes based on ph
* This is defined [at the bottom](#tranmm)

Here's what an ID VGS sweep looks like for different pHs:

```{figure} ../Images/L4/idvgssweep.png
:label: idvgs
:alt: ID VGS Sweep for Different PH 
:align: center
```
Therefore if you want to keep track of what the pH is, you either need to establish a fixed potential and measure the current output of the transistor or establish a fixed current and measure the change in voltage.

* Threshold voltage shifts with pH concenration.
* 1 pH unit causes a change of 59mV.
* This is known as the Nernst Potential - 59mV/pH

#### ISFET Readouts

**WE want to measure the change in $V_{\text{chem}}$**

We use the following circuit, this is called the **Constant Charge Method (CCM)**, it is a **Opamp based** method:

```{figure} ../Images/L4/ISFETreadout.png
:label: isfetreado
:alt: ISFET Readout Circuit 
:align: center
```

* Fix $V_G$, $I_D$, $V_{DS}$ to operate at a fixed working point.
* $V_S$ then tracks changes in $V_T$.
* Opamp $A_2$ tracks changes in $V_S$ and through feedback of $A_1$, sets $V_D$ to ensure $V_{DS}$ is always constant.

We also have a **Bridge based** method (referring to the wheatstone bridge resistor circuit):

```{figure} ../Images/L4/bridgebasedreadout.png
:label: bbreadout
:alt: ISFET Bridge Based Readout Circuit 
:align: center
```

And we also have an **Instrumentation based** method, looking back to last week's instrumentation amplifier:

```{figure} ../Images/L4/instrumentationbasedreadout.png
:label: instrumentreadout
:alt: ISFET Instrumentation Based Readout Circuit 
:align: center
```

* The ISFET is connected at the terminals usually applied to the gain- determining resistor.

* The fixed voltage across the input terminals of the instrumentation amplifier (VDS) holds the ISFET drain- source voltage constant, and the gate- voltage is fixed by the grounded reference electrode.

* Thus any change in ion concentration modulates the current through the ISFET, and thus its channel resistance.

* The difference between this output and a fixed reference voltage acts as a feedback signal to adjust the common- mode level of VDS to keep the drain current constant and achieve constant charge mode operation. 

### Conductomety

Conductometric Measurement can be defined as follows:

* A change in concentration causes a change in the conductivity of the solution which we can measure.
* Measurement of the ability of a solution to carry electric current.
* Not very selective however as a solution can contain many ions.

We want to measure the *Conductance* $G = 1/R$ in units of $\text{ohms}^{-1}$ or Siemens

The *Conductivity*: 

```{math}
k = GK = GL/A = L/AR
```
Where:

* K ($\text{cm}^{-1}$) = cell constant based on...
* conduction length $L$
* and cross sectional ($A$) area of electrode surface $S$
* units $\text{ohms}^{-1}\text{cm}^{-1}$ or $S\text{cm}^{-1}$

And we use this $k$ to get more detail specifically on the conductivity of the solution, we call $A_m$ the *Molar Conductivity*

```{math}
A_m = k/c
```

Where:

* $k$ is the measured conductivity, 
* $c$ is the electrolyte concentration

```{figure} ../Images/L4/molarconductivity.png
:label: molarcond
:alt: molar conductivity 
:align: center
```
#### Wheatstone Bridge

How do we measure this resistance?

We use the wheatstone bridge circuit. We measure the voltage difference between the circuit bridge, this will give you an indiction of the solution conduction.

```{figure} ../Images/L4/wheatstonebridge1.png
:label: wheatsb1
:alt: Wheatstone Bridge 1 
:align: center
```
Below is a commonly used circuit, it's a balanced configuration whereby if you measure $V_G$, provided the resistor values $R_1$, $R_2$ and $R_3$ are fixed it gives you an indication as to what $R_x$ is.

```{figure} ../Images/L4/wheatstonebridge2.png
:label: wheatsb2
:alt: Wheatstone Bridge 2
:align: center
```
And how can we implement this?

We use a bog standard instrumentation amplifier, an LPF and then into a ADC.

```{figure} ../Images/L4/wheatstonebridge3.png
:label: wheatsb3
:alt: Wheatstone Bridge 3
:align: center
```