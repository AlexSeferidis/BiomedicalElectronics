# Lecture Notes

---

- [ ] Have Revised

## Bio-Potentials

```{hint} Today!
Today we are going to get more in depth into designing systems, specifically looking at systems for bio-potentials and instrumentation.
```

Bio-potentials are important because our bodies inherently have **electrically excitable cells**. This means they generate potentials (similar to voltage potentials) which can measure for various purposes.

For example:

* ECG - measures our heart
* EMG - measures contracting of muscles
* EEG - Brain behaviour

### Action-Potentials

So let's return and have a look at where these action-potentials originate (See L2 for more detail):

* The cell is surrounded by sodium, potassium and chlorine ions.
* Current flow due to movement of Sodium and Potassium ions
* There are **more** potassium ions **inside** the cell
* There are **more** sodium ions **outside** the cell
* This imbalance sets up a nernst potential, or the imbalance of charge (See L2)

We can think of the lipid membrane almost like a capacitor, because inside the cell it's full of enriched intracellular potassium ions and outside of the cell, enriched extracellular sodium ions. This insulating membrane with different charges constitutes a potential difference or EMF.

```{figure} ..\Images\L3\labpotengraph.png
:label: labelledgraphpotential
:alt: Labelled Potential Graph
:align: center
```

[Here](#actioncycle) you can see the action / generation of this spike visually:

```{figure} ..\Images\L3\actioncyclediagram.png
:label: actioncycle
:alt: Action Potential Graph and Diagram Cycle
:align: center
```

```{tip} Definition!!!

So what is a **Bio-Potential**?

**An electric potential that is measured between points in living cells, tissues, and organisms, and which accompanies all biochemical processes**

```

We have seen already the [ranges of freq and signal strength of different biopotentials](#rng) and now we will explore them in greater detail, for example [their morphologies][#sigmorph]

```{figure} ..\Images\L3\signalmorph.png
:label: sigmorph
:alt: Signal Morphologies for ECG, EMG and EEG
:align: center
```

## ECG

Our heart pumps due to the rhythmic electrical activity to circulate oxygenated around our body. It all starts in the atrium and then our through the ventricles. We get an initial sinusoidal boom which resonates down into the rest of the heart, providing a superposition kind of effect, we can see this here[#heartsig] in the final waveform.

```{figure} ..\Images\L3\pqrst.png
:label: heartsig
:alt: Signal Superposition for PQRST
:align: center
```

This is described as the **PQRST(U) complex**

### PQRST Complex

So the PQRST complex refers to the characteristic waveform seen on an ECG, representing the electrical activity of the heart's beat.

* **P-Wave**
    - Reflects the **atrial depolarisation** which is the electrical activity that causes the **atria** to contract
    - This pushes blood from the atria into the **ventricles**
    - This shows up as a small, rounded upward deflection on the ECG
* **QRS Complex**
    - Reflects the **ventricular depolarisation**, which is the electrical acitvity that triggers the **ventricles to contract**
    - This pumps blood from ventricles to the lungs
    - The ECG shows a small downward deflection (**Q-Wave**), a sharp tall upward deflection (**R-Wave**) and a small downward deflection (**S-Wave**)
*  **T-Wave**
    - Reflects the **ventricular repolarisation** which is the process of ventricles returning to their resting electrical state after contraction
    - This shows the muscle relaxing
    - This shows up as a broad, rounded upward deflection
* **U-Wave (Optional)**
    - Reflects the **repolarisation of the Purkinje fibres**
    - Is only **sometimes** present
    - Appears as a small , rounded wave following the T-Wave

P-Q, Q-R-S, S-T segments are commonly used for diagnosis.

```{figure} ..\Images\L3\pqrstdiagram.png
:label: pqrstdiagram
:alt: PQRST Diagram
:align: center
```

### Measuring ECG

So how do we measure an ECG?

Well given that this is an electrical process, it should be of no suprise that this generates an **electric field**. This allows us therefore to connect 2 electrodes in the local proximity of the heart to pick up this electric field.

We can characterise this as the **cardiac vector**

```{figure} ..\Images\L3\measuringECG.png
:label: ECGmeasure
:alt: Body Diagram of Heart Electrode Measurements for ECG
:align: center
```

### ECG Basics

| Feature   | Description |
| :----:    | :---:       |
| Amplitude | 1-5 mV      |
| Bandwidth | 0.05-100 Hz |

* Largest measurement error sources:

    - Motion artifacts (electrodes generated from skin movement)
    - 50/60 Hz powerline interference

ECG has several applications such as diagnosis of ischemia (lack of blood flow), Arrhythmia (pre-cursor to heart attack), Conduction defects.

```{figure} ..\Images\L3\heartproblems.png
:label: ECGprob
:alt: Heart Problems diagnosed by ECG
:align: center
```

## EEG

EEG measures the brain electric activity from the scalp, the measured signal results from the activity of billions of neurons. This is broken into various frequency bands for Beta, Alpha, Theta and Delta waves, these can be seen [here](#EEGbands).

```{figure} ..\Images\L3\EEGfreqbands.png
:label: EEGbands
:alt: Frequency bands of EEG
:align: center
```

So these constituent bands can tell us varying things, for example Theta waves can be used to determine whether someone is sleeping, they have their eyes open or closed, etc...

| Feature   | Description   |
| :----:    | :---:         |
| Amplitude | 0.001-0.01 mV |
| Bandwidth | 0.5-40 Hz     |

```{note} Note!

We note that the amplitudes are **extremely small**. This means that **thermal noise** and **RF noise** can impact the recorded signal

```

EEG is typically used to study sleep, detect seizures and perform cortical mappings (identification and localisation of functional areas within the cerebral cortex).

## EMG

EMG measures the electric activity of active muscle fibres. Electrodes are always connected very close to the muscle group being measured. The rectified and integrated EMG signals gives rough indication of the muscle activity.

| Feature   | Description |
| :----:    | :---:       |
| Amplitude | 1-10 mV     |
| Bandwidth | 20-2000 Hz  |

Errors can occur with regards to 50/60 Hz and RF interference as well as motion artifacts (similar to ECG because we measure from the skin).

The applications of EMG include: Observing muscle function, neuromuscular disease and prosthesis.

## Other Bio-Potentials

We also have some other bio-potentials that are touched on in this course:

* **Neural Spikes**

These are directly monitored from individual neurons in the brain through an implanted microelectrode array

```{figure} ..\Images\L3\neuralspike.png
:label: nspike
:alt: Neural Spike
:align: center
```

You can see from [these graphs](#nspike) that we see a similar action potential, with an extremely small signal amplitude in the micro volts.

* **LFP**

Local field potentials is the average DC baseline activity measured from an implanted microelectrode. So essentially a measurement of constant activity. This is measured directly on top of the brain using an implant.

```{figure} ..\Images\L3\LFP.png
:label: LFPgraph
:alt: LFP graphs
:align: center
```

These [graphs](#LFPgraph) are examples of LFP recordings, the red on the right might signify that an epileptic seizure is happening in the brain.

## Designing and Measuring for Bio-Potentials

So now we've covered the basics of the bio-potentials we will be looking at, below is a summary of all the signals and their descriptions.

| Signal                 | Freq Range (Hz) | Amplitude range (mV) |
| :---:                  | :---:           | :---:                |
| ECG                    | 0.05-100        | 1-5                  |
| EEG                    | 0.5-40          | 0.001 - 0.01         |
| EMG                    | 20-2000         | 1-10                 |
| Neural Spikes          | 300-5000        | 0.001 - 0.5          |
| Local Field Potentials | 10-200          | 0.001 - 5            |

In order to measure bio-potentials we generally need to use contacts on the body, like an electrode. This signal then goes into an **amplifier**, which measures the potential and then it goes onto a filter of some kind. This has to be robust as to avoid noise.

```{figure} ..\Images\L3\humancontactdiagram.png
:label: humancon
:alt: Human Contact Circuit Diagram
:align: center
```

This **amplifier** is very important and we need to consider some requirements:

* **High I/P Impedance** - so as not to attenuate the measured signal
* **High Gain & Low Noise** - to detect and amplify very small signals
* **High CMRR** - to discard common noise to both terminals, such as 50 Hz noise
* **Band Pass Filtering** - to select the frequency range of interest

```{note} Recall CMRR
:class: dropdown
CMMR is the ability of the amplifier to discard signals which are common to both terminals. In this case you'll have 50/60 Hz noise common to both terminals, so it should reject it.
```

The [general architecture](#genarch) of an ECG measurement system is as follows, this is **really important**:

```{figure} ..\Images\L3\generalarch.png
:label: genarch
:alt: Human Contact Circuit Diagram
:align: center
```

### Considerations for Detection

Before going into depth on each component of the architecture, let's see the things we should be considering when designing our systems:

* **High input impedance** (> 50MΩ)
* **Gain** (> 40dB)
* **High CMRR** (> 70dB)
* **Resolution** – 6-12 Bits (depending on application)
* **Noise** – signal dependent, typically < 10uV RMS
* **Frequency** – signal dependent, typically < 10 KHz
* **Power consumption** – application dependent
* **Interfering inputs** – mains noise, electrode impedance, offset.
* **Placement of Electrodes** – Distance, intracellular, extracellular.

### Electrodes

So let's start by looking at the main interface to the tissue, **electrodes**.

Electrodes are basically conductive to the skin, they can be silver (usually in a saline solution to enhance the conductive layer) or also implantable. These implantable ones usually go directly into the brain where as the skin surface electrodes are generally for ECG, EMG and EEG.

Electrode grids for recording for the brain surface is called ECoG. This generally measures low-frequency EEG/LFP-like signals (individual neurons not observable)

```{figure} ..\Images\L3\ECoG.png
:label: ECoG picture
:alt: ECoG Picture
:align: center
```

This is used to identify and localise areas of the brains causing seizures.

Something we need to be very mindful of is the impedance consideration between the surface of the skin and the actual signal source we are measuring. We can approximate this to a [resistor capacitor network](#skinapproximation).

```{figure} ..\Images\L3\skinapproximationcircuit.png
:label: skinapproximation
:alt: Skin Approximation Circuit
:align: center
```

This is something we need to consider when making our instrumentation. [This is a reasonably equivalent circuit model](#equivalentmodel) that we use for the electrode tissue interface.

```{figure} ..\Images\L3\equivalentcircuitmodel.png
:label: equivalentmodel
:alt: Equivalent Circuit Model for Electrode Tissue Interface
:align: center
```

Where:

* $C_{E}$ : capacitance of electrode-electrolyte interface
* $R_{p}$ : resistance of electrode-electrolyte interface
* $R_{s}$ : resistance of electrode lead wire
* $R_{tissue}$ : resistance of tissue
* $V_{sig}$ : detected bio-potential
* $V_{os}$ : common mode offset

We need measuring instruments to have **higher impedance than electrode impedance** so as not to attenuate the signal (we also need small input capacitance).

When designing we can treat the electrode-instrumentation interface as a simple RC circuit on the I/P of the amplifier.

```{figure} ..\Images\L3\electrode-instrumentation-interface.png
:label: elec-intru-inter
:alt: Electrode Instrumentation Interface
:align: center
```

### Impedance Levels

* We want **input impedance** $Z_{IN}$ to be very high so that it doesn't divide down your I/P signal. So it doesn't divert any current from the I/P to itself even if the input has very high resistance (e.g an opamp taking I/P from microelectrode)

* Our **output impedance** $Z_{OUT}$ should be very low, so that we can drop the maximum voltage over the next stage load. So it can supply output even to very low resistive loads and not expend most of it on itself.

```{figure} ..\Images\L3\impedancelevelcircuit.png
:label: impedancelvl
:alt: Impedance Level Circuit
:align: center
```

We note from the maths in [this diagram](#impedancelvl) that the input resistance must be huge and the input capacitance of the amplifier must be small relative to the electrode.

### Noise

#### Mains 50Hz Noise

So let's look a bit at noise, starting from the **mains 50Hz noise**.

```{figure} ..\Images\L3\mains50Hz.png
:label: mains50Hz
:alt: Mains 50 Hz Noise Source
:align: center
```

[Here](#mains50Hz) we see that the wire connecting the electrodes to the instrumentation are also passively coupled to the power line via capacitors $C_1$ and $C_2$. The net result of that is it will cause a small current to flow ($I_{d1}$ and $I_{d2}$).

This current flows through the skin-electrode impedances $Z_1$ and $Z_2$, this can be modelled like so:

```{math}

v_A - v_B = i_{d1}Z_1 - i_{d2}Z_2 \\
\text{With } i_{d1} \approx i_{d2} \text{ for wires next to each other} \\
v_A - v_B = i_{d1}(Z_1 - Z_2)

```

```{warning} So...
Assuming 50Hz noise causes an $i_d$=6nA
Skin electrode impedance can differ by 20 KΩ
This gives an unwanted signal on the input of:
$V_a-V_b$=6nA x 20 KΩ = 120uV !
```

#### Common Mode Noise

Another source of noise is **common mode noise**.

So if we get rid of the wires and integrate the circuit like a patch, current $i_{db}$ couples from the power line through $C_b$ and flows through the body and ground impedance

This causes a common mode voltage everywhere in the body ($V_cm$)

```{figure} ..\Images\L3\commonmodenoise.png
:label: commonmode
:alt: Common Mode Noise Source
:align: center
```

The induced noise on measured voltage is given as a consistent offset:

```{math}

v_{cm} = i_{db} Z_G

```

Typically $v_{cm}$ = 0.2uA x 50kΩ = 10mV.

**Normally common mode noise would be rejected by amplifiers**, however finite input impedance of the amplifier $Z_{in}$ and different impedance in leads $Z_1$ and $Z_2$ can cause a slight offset to appear:

```{math}

v_A - v_B = v_{cm}(\frac{Z_{in}}{Z_{in} + Z_1} - \frac{Z_{in}}{Z_{in} + Z_2}) \\
Z_1 \text{ and } Z_2 << Z_{in} \\
v_A - v_B = v_{cm}(\frac{Z_2 - Z_1}{Z_{in}}) \\
v_{cm} = i_{db} Z_G
```

#### Motion Artifacts

If a pair of electrodes is in an electrolyte and one moves with respect to the
other, a potential difference appears across the electrodes known as the
**motion artifact**.

This is a source of noise and interference in biopotential measurements. It is a result of the change in distribution of the double layer of charge on the polarizable electrode interface because of movement. This changes the half cell potential of the electrode temporarily.

```{figure} ..\Images\L3\motionartificat.png
:label: motionart
:alt: Motion Artifact Example
:align: center
```

#### Solutions

| Type of Noise       | Solution                               |
| :---:               | :---:                                  |
| 50 Hz power lines   | shielding, filtering                   |
| Other biopotentials | filtering                              |
| Motion artifacts    | relaxed subject, signal processing     |
| Electrode noise     | high quality electrodes, good contacts |
| Circuit noise       | good design, good components           |
| Common mode noise   | differential design, high CMRR         |

## Biopotential Amplifier

We will now proceed in designing some bio-potential amplifiers, but first we have some requirements.

An integrated front-end amplifier for bio-potentials should:

* Amplify signals in the **frequency bands** of interest;

* **Block dc offsets** present at the electrode-tissue interface to prevent saturation of the amplifier;

* Have sufficiently **low input-referred noise** to resolve biological signals in the low microvolt range;

* Have sufficient **dynamic range** to convey signals in the low millivoltrange;

* Have much higher **input impedance** than the electrode-tissue interface and have negligible dc input current;

* Reject common-mode signals (**high CMRR**) particularly at 50/60 Hz; reject power supply noise (**high PSRR**);

* Consume little power, to facilitate wearable or implantable applications.

### Instrumentation Amplifier

So we need to make an amplifier to set the voltage, the easiest amplifier we know is an opamp in a closed loop configuration.

```{figure} ..\Images\L3\simpleopamp.png
:label: simpopamp
:alt: Simple Opamp Circuits
:align: center
```
This can give us the gain we need however it **lacks immunity to common mode signals**. So our 50Hz noise will be amplified. So how do we get rid of this problem?

We can use a **difference amplifier**. These are good for rejecting common mode signals, so we don't have to worry about the 50Hz noise.

```{figure} ..\Images\L3\differenceampbasic.png
:label: difampbas
:alt: Simple Difference Amplifier Diagram
:align: center
```
This amplifies the difference between $V_1$ and $V_2$ but rejects any common mode signals.

### Differential Instrumentation Amplifier 1

```{figure} ..\Images\L3\DIA1.png
:label: dia1
:alt: Difference Amplifier 1 Diagram
:align: center
```
In this case:

```{math}
A_D = \frac{R_2}{R_1}; A_c=0
```

So **CMRR is infinite!** However this is assuming the resistors are matched, and mismatch seriously degrades CMRR, and therefore not infinite in the real world. Also input impedance is not infinite, it's set by $R_1$!

### Differential Instrumentation Amplifier 2

So how do we fix this? Well let's stick another stage in front of it which has a really high I/P impedance:

```{figure} ..\Images\L3\newstage.png
:label: nstage
:alt: Difference Amplifier New Stage Diagram
:align: center
```

So now we have really high I/P impedance from the opamps, we can then add this back to the previous circuit.

```{figure} ..\Images\L3\stage2difamp.png
:label: ostage
:alt: Difference Amplifier Original Stage Diagram
:align: center
```
Giving us [our final diagram](#dia2). This now has a **high I/P impedance** and **high CMRR**. The gain is normally **tuned by a variable resistor** in place of $R_1$.

```{figure} ..\Images\L3\DIA2.png
:label: dia1
:alt: Difference Amplifier 1 Diagram
:align: center
```

## Electrical Interference Reduction

What can we do to reject 50/60 Hz noise?

Common mode interference would be completely rejected by the instrumentation amplifier if the matching were ideal, however this is often not the case. A clever trick is the **"driven right leg circuit**, which works to enhance the CMRR for ECG.

**The idea being the Average of the $V_{CM}$ is inverted and driven back to the body via a reference electrode**

```{figure} ..\Images\L3\rlegcircuit.png
:label: rlegc
:alt: Right Leg Circuit Diagram
:align: center
```

### Right Leg Drive Circuit

Through feedback the body's displacement current flows not to instrument ground but to the O/P of the opamp. This reduces $V_cm$:

```{math}
\frac{V_{cm}}{R_1 / 2} + \frac{V_{out}}{R_2} = 0 \\
V_{out} = -\frac{2R_2}{R_1}V_{cm} \\
V_{cm} = R_o i_d + V_{out} \rightarrow \frac{R_o i_d}{1+2R_2 / R_1}
```

if we recall without the driven right leg circuit $V_{cm} = i_d R_o$ which has now been **reduced by ratio of resistors** $R_1$ and $R_2$. The circuit also provides electrical safety as the maximum current is limited by the feedback opamp.

## Filtering

What we've covered so far is on the front end, now we need to consider that different bio-potential signals occupy certain frequency ranges. This means we need a BPF to select only the range we want.

To do this we can **cascade a HPF and a LPF**

```{attention} IMPORTANT

**We always put the HPF first!!!**

This is because we need to remove DC and thus lets you add more gain in later stages to boost your signal.

```
**NOTE:** We also describe the cut off frequency $f_c$ at the 3dB point, when the I/P signal is attenuated of half the power

```{figure} ..\Images\L3\BPF.png
:label: bpf
:alt: BPF Freq Response
:align: center
```

We can use spectral analysis of the signal to determine the bandwidth. An estimate can also be derived by looking at the durations of the low and high frequency components of the signal.

```{figure} ..\Images\L3\highlowfreq.png
:label: hlfreq
:alt: Time to find freq
:align: center
```

* **High Frequency**: $t_{HF}$ is the minimum rise or fall time of the signal
* **Low Frequency**: $t_{LF}$ is the tilt of the baseline or lowest frequency component

### Filter Response Laplace

```{figure} ..\Images\L3\filterresponselaplace.png
:label: laplace
:alt: Laplace Filter Response
:align: center
```

$Q$ factor : Determines the height and width of the peak of the frequency response of the filter

### RC Filter

The RC filter has no active components, only passive. Therefore they require no power supply and there's no gain attenuation. However there is no buffering or high I/P impedance.

```{figure} ..\Images\L3\RCFilters.png
:label: rcf
:alt: RC Filters
:align: center
```
To prevent loading we add a voltage buffer op-amp between stages

### Op-Amp Filter

This is an active filter which can also amplify the signal (with a gain of $1+\frac{R_1}{R_2}). This also does not do loading of successive stages. Unfortunately this is limited by the op-amp's frequency response.

```{figure} ..\Images\L3\opampfilters.png
:label: opampfilters
:alt: Opamp Filters
:align: center
```

### Sallen-Key Filter

These are relatively simple circuits which can realise 2nd order filters with a single op-amp. If we cascade these we can make **brick wall filters**. 

```{figure} ..\Images\L3\sallenkey.png
:label: skey
:alt: Sallen Key Filters
:align: center
```

```{hint} Remember!
By selecting equal components ($R_1=R_2$, $C_1=C_2$) there is no gain attenuation, so you can cascade without worrying about saturating O/P
```

### Notch Filter

These directly filter out 50/60Hz noise. BUT be careful that you don't filter out vital information if it is within the frequency bandwidth, therefore it's best to use only when you absolutely have to.

```{figure} ..\Images\L3\notchfilter.png
:label: notchfilter
:alt: Notch Filters
:align: center
```

```{figure} ..\Images\L3\notchresponse.jpg
:label: notchresponse
:alt: Notch Filters Response
:align: center
```

### Final ECG

```{figure} ..\Images\L3\ECGcircuit.png
:label: ECGcircuit
:alt: ECG Circuit
:align: center
```

## AC Coupled Bio-Potential Amplifiers

For very small Bio-potentials in the mV range we need a really high gain at the I/P stage. This is why we need AC coupled Bio-Potential amplifiers, which **only let AC go to the amplifier at the 1st stage**.

The idea is that DC offset voltage on I/P can be so large that it saturates the amplifier, this makes it difficult to add lots of gain in front-end. The solution is to **capacitvely couple**

```{figure} ..\Images\L3\accouple.png
:label: accouple
:alt: AC Coupled Amp Circuit
:align: center
```

There are some **problems** with this method:

* This can degrade CMRR due to poor matching of components.
* Input capacitance must be smaller than electrode capacitance otherwise there will be attenuation.
* Charging currents can cause undefined voltages on the input, thus need to add resistor $R_f$ to fix the input DC voltage.
* This reduces the input impedance significantly.

### The Harrison Amplifier

The Harrison Amplifier is an example of a state of the art AC coupled instrumentation amplifier.

```{figure} ..\Images\L3\Harrisonamp.png
:label: harriscircuit
:alt: AC Coupled Harrison Amp Circuit
:align: center
```
Need to ensure that $C_1$ is smaller then electrode capacitance so signal is not attenuated AND resistor $R_2$ is required to set the common mode I/P of the amplifier.

Below is the complete TF, don't worry you don't have to derive:

```{math}

\frac{v_{\text{out}}}{v_{\text{in}+} - v_{\text{in}-}} = \frac{C_1}{C_2} \cdot \frac{1 - sC_2 / G_m}{\left( \frac{1}{sR_2C_2} + 1 \right) \left( s \frac{C_1C_L}{G_mC_2} + 1 \right)} \\
= A_M \cdot \frac{1 - s / (2\pi f_z)}{\left( \frac{2\pi f_L}{s} + 1 \right) \left( \frac{s}{2\pi f_H} + 1 \right)}

```

This network of capacitors and resistors produce a frequency response of a BPF as well.

```{figure} ..\Images\L3\harrisonfreqresponse.png
:label: harrisfreqres
:alt: AC Coupled Harrison Amp Freq Response
:align: center
```

And we can also add a 2nd amplification stage

```{figure} ..\Images\L3\harrison2stage.png
:label: harris2s
:alt: AC Coupled Harrison Amp 2 Stage
:align: center
```