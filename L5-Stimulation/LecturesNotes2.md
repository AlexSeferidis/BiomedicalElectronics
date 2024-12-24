# Lecture Notes - 5.2

---

- [ ] Have Revised

## Introduction

This lecture will focus specifically on the fundamentals of how you would design a stimulator, the nuts and bolts and the fundamentals behind stimulation circuit design.

```{hint} So why do we need a stimulator, and what does it actually do?

Basically electrical stimulation is a way of changing activity in electrically excitable cells.

```

So as discussed in 5.1, we've covered the following applications of stimulation. They typically come in 2 types:

1. Muscle Stimulation

    - Cardiac Stimulation
        * Pacemaker
        * Defibrillator
    - FES
2. Neural Stimulation

    - CNS
        * DBS
        * Sensory prosthesis (cochlear implant, retinal implant, vestibular implant)
    - PNS
        * VNS for epilepsy
        * Motor control (for FES)

### Stimulation Circuit Examples

[This circuit](#4chan) is designed to extract a nerve from an animal which can stay alive for 12 hours and then try out different stimulation waveforms on it, to find the most efficient way of stimulating that nerve.

```{figure} ../Images/L5/4channelstim.png
:label: 4chan
:alt: 4 Channel Stimulator for Acute Neurophysiology
:align: center
```
[This](#bidir) is another designed implantable chip that had a recording pathway and a stimulation circuit. The idea is that you can record activity from the NS but also stimulate activity at the same time.

```{figure} ../Images/L5/bidirectneural.png
:label: bidir
:alt: Bidirectional Neural Interface for a Chronic Implanatable Device
:align: center
```

In this lecture we are going to cover these types of circuits, and we go about designing them.

### Electrode Types

So when we talk about stimulation circuits, what are we actually stimulating? Well we are trying to **communicate an electronic current to an ionic current in the tissue**.

This **translation** between electrons and ions are done by **electrodes**.

```{math}

\text{electrodes } = \text{electric current } \rightarrow \text{ ionic current}
```

We have different styles of electrodes. [This electrode](#penelec) is used for cochlear implants in the brain. You can use that to stimulate the brain directly.

* **CNS - Penetrating Electrodes**

```{figure} ../Images/L5/penetratingelectrodes.png
:label: penelec
:alt: Penetrating Electrodes
:align: center
```

We also have [these](#cufflifetime) types of electrodes which typically wrap around nerves or they can be threaded through nerves.


* **PNS - Cuff/ LIFE/ TIME**

```{figure} ../Images/L5/cufflifetime.png
:label: cufflifetime
:alt: Cuff/LIFE/TIME Electrodes
:align: center
```

Other types of electrodes include:

* Cochlear Implant Electrodes
* Retinal Implant Electrodes
* DBS Electrodes
* Electrodes for Cardiac Rhythm

And many others...

## Electrode Configurations

So now we've spoken about electrodes, what are the different ways in which we can configure electrodes in order to achieve stimulation. 

Fundamentally **we need 2 electrodes in order to stimulate**. Because if we have a current source, we push that current into tissue, we then need to get that circuit back so that we can **close our circuit** and pass it to ground.

1.  **Monopolar Configuration**, with return electrode placed at a distance from the working electrode and with a larger surface area

    * So we have one big shared electrode
    * If we had a 10 channel system we would have 10 small electrodes and 1 big one for the reference

2. **Bipolar configuration**, with dedicated electrode pairs per channel

    * So for every site that we want to stimulate with a pair of electrodes
    * Therefore for 10 channels we need 20 electrodes

3. **Multipolar configuration**

    * This is more complicated
    * A scheme by which you actually stimulate through lots of electrodes
    * For example in [this one (on the right)](#elecconfig), 1 electrode is the cathode and 2 which are the anode, so basically part of the current is going between one pair of electrodes

At the end of the day you just have KCL, so the amount of current going into the tissue has to equal the amount of current going out of the tissue.

**In the majority of devices we use the Monopolar Configuration**

```{figure} ../Images/L5/electrodeconfig.png
:label: elecconfig
:alt: elecconfig
:align: center
```

```{warning} Remember!

Whenever you're applying a stimulation circuit **you need a minimum of 2 electrodes**, and you can configure them in a number of different schemes. We do this so we close the circuit.

```

## Electrode / Electrolyte Interface Model

We've seen [this model before](#equivalentmodel).

A complex electrochemical reaction occurs at the electrode/electrolyte interface model.

* Current flows cia electrons in metal but via ions in solution
* Any charge buildup can lead to non-reversible faradaic reactions (i.e. electrodes dissolving, gas formation, variation of pH, etc)

```{figure} ../Images/L3/equivalentcircuitmodel.png
:label: equivalentmodelagain
:alt: Equivalent Circuit Model for Electrode Tissue Interface Again
:align: center
```

Where:

* $R_S$ = Solution spreading resistance
* $R_P$ = Faradaic charge transfer resistance
* $C_E$ = Capacitive charge transfer via the interface capacitance (approx. $\mu F/cm^2$)

Note: the $R_S$ elements and $R_{\text{TISSUE}}$ can be lumped together

**Component values are dependent on the electrode's material and the tissue/electrolyte.**

**The electrode impedance is frequency dependent** - this is due to the capacitor.

## Waveform Profiles

Fundamentally, in order to stimulate tissue, we need to send a pulse into that tissue.

However it's very important that whatever charge we inject into the tissue, we then pull out of the tissue, **there must never be a net charge flow into the tissue or out of the tissue**, otherwise we have DC current. (area under [graph](#waveformprof) above and below zero should be equal)

```{warning} Why do we NOT want DC current?
:class: dropdown

Our electrodes will start to dissolve and bad things will happen

```

```{figure} ../Images/L5/waveformprofiles.png
:label: waveformprof
:alt: Waveform Profiles
:align: center
```

So to stimulate the tissue we would just need [monphasic](#waveformprof), but in order to pull the charge back out we would use [biphasic](#waveformprof), because it's 2nd phase is pulling it back out.

So let's go into more detail:

1. Stimulus must be charge balanced (i.e. net charge is zero) 
    * **Monophasic** waveforms rely on passive discharge (i.e capacitively coupled)
2. Stimulation waveforms are typically **biphasic** (with **cathodic** & **anodic** phases)
    * Cathodic phase: first pulse is for activation
    * Anodic phase: second pulse is for balancing
3. Additional considerations
    * **Interphasic delay** often used to prevent anodic phase blocking activation - i.e if we pull current in and out straight away, we might not stimulate the tissue, so add delay
    * **Shorting phase** often used to remove residual charge (every few cycles)

We can take a closer look at [a sample waveform](#samplewaveform), which has multiple phases.

```{figure} ../Images/L5/samplewave.png
:label: samplewaveform
:alt: Sample Waveform
:align: center
```

Things to note:

* The positive currents and negative currents are different magnitudes, this is because sometimes it's desirable for your stimulation phase to have larger current over less time, but your balancing phase to have smaller current over longer time.
* This is called an **Asymmetric waveform**, it's particularly good for a thing called fatigue.
* If you stimulate the tissue really, really quickly, the tissue will get tired after some time. So there's a maximum rate at which we can stimulate tissue. We can limit this by using asymmetric waveforms. 

There are lots of different types of waveforms but generally ($\approx$ 90%) devices use **monophasic** if you don't care about speed of stimulation and you do it through a capacitor. If you want to stimulate very quickly you use **biphasic**.

**NOTE: Asymmetric waveforms are not applicable to high channel/high refresh stimulation** 

This is because the overall stimulation period gets much longer, and we can only stimulate one channel at a time (if we pump current into different electrodes we'll get crosstalk between them). So we can't stimulate concurrently two sets of channels - therefore we have to do time division multiplexing.

```{hint} Why do we like perfect square pulses?
:class: dropdown

* Easier to implement
* It's easier to monitor the amount of charge (simple current * time)

```


## Stimulation Circuits / Design

Now let's move on to the actual circuits, we'll look at specific examples, design principles, requirements and applications.

### Stimulation Circuit Requirements

1. **Dynamic Range**

    * The minimum to maximum stimulus or magnitude
    * this depends on electrode - the smaller the electrode, the closer the electrode is to the tissue and therefore less current is needed 
    * Can range from $10 \mu A$ - $10mA$

2. **Needs to work with Electrode Variability**

    * We need to know the type of electrode we're stimulating so we can design our power supply to accomodate the voltage drop across the electrode impedance ($V=IR$)
    * **The larger the electrode, the lower the impedance**
    * Can range from $1k\Omega$ - $100k\Omega$

3. **Digitally-programmable**

4. **Should ensure charge balancing**

    * i.e Anodic/cathodic matching, so the stimulus does not exceed the maximum charge density of the electrode material
    * typically $\lt \lt 1$% mismatch 

5. **Energy efficiency**

    * Should be energy efficient, good battery lifetime / charge cucles
    * **Stimulation efficiency = power consumed at electrode / total power consumed**

6. **Reliable** 
    * Must be reliable over a period of years (if plantable)


### Stimulator System Design

```{figure} ../Images/L5/SSD.png
:label: SSD
:alt: Stimulator System Design
:align: center
```

Let's break down this design fundamentally:

* **Stimulus Generation Circuit**: A circuit which generates a quantity
* **Output Driver (Buffer)**: A circuit that matches the impedance of the electrode so that it can drive that current of voltage into the tissue
* **Electrode Configuration (MUX)**: Switches that can steer that current or voltage to different electrodes
* **Electrodes**
* **Digital Controller**: All components controlled with this, could be a micro-controller, FPGA, custom FSM, etc. It performs the digital timing and controlling the switches.


### Methods of Charge Delivery

It's possible to deliver charge to tissue, via circuits changing the stimulus, in different ways.

**Action potentials** can be generated by **Electrical Neural Stimulation**, triggered by injecting a charge packet to the extracellular space.

```{figure} ../Images/L5/chargedeliver.png
:label: cdeliver
:alt: Methods for Charge Delivery
:align: center
```

[Here](#cdeliver) we see 3 types of charge delivery, using programmable current, voltage and charge sources:

* **Voltage-Mode**: fixed voltage, monitor the current, control the duration
* **Current-Mode**: fixed current, control the duration
* **Charge-Mode**: fixed capacitor, charge to fixed voltage, then discharge to stimulus

**NOTE: The most common and safe method is current mode**

### Current-Mode Stimulus Generation

So how do we generate a current mode signal?

It's actually *very simple*. We use something like a current mirror. It's a **binary-weighted current mirror**

```{figure} ../Images/L5/CMstim1.png
:label: cm1
:alt: Circuit 1 for CM Stimulus Generation
:align: center
```

[A binary-weighted current mirror](#cm1) is a current mirror type circuit that is used for DAC. Here's a basic idea of how it works:

* We supply a bias current (say $100\mu A$)
* We get $100\mu A$ in branch 1, $200\mu A$ in branch 2, $400\mu A$ in branch 3 and $800\mu A$ in branch 4
* then by controlling the switches we can make whatever current we want
* and we can add and subtract current by connecting current sources together

The 2nd thing we need to worry about is when we're doing a current mode stimulator, is what actually drives the tissue. 

**If we're designing a current source our ideal O/P resistance is infinity**

In reality it doesn't have to be infinite, it just needs to be much, much higher than the load resistance. This is where we go back to the electrode, so if we have a $1 k\Omega$ electrode, you need your current source to have a $1 M\Omega$ resistance.

So there are 3 classes of O/P stages:

1. **A simple current mirror**
    * This supplies to load around $10$ - $50 k\Omega$

2. **Cascode current mirror**
    * This supplies something like $10$ - $100 M\Omega$

3. **Regulated cascode**
    * This supplies around $1 G\Omega$

```{figure} ../Images/L5/CMstim2.png
:label: cm2
:alt: Circuit 2 for CM Stimulus Generation
:align: center
```

The **disadvantage** of using the regulated cascode rather than a simple current mirror is that we're **losing voltage**. So therefore it is more power consuming as we must consider this voltage headroom by adding additional voltage to compensate.

### Voltage-Mode Stimulus Generation

So how do we design a voltage stimulation circuit?

We would use something like a **DAC**, like an **R-2R Ladder**,to generate the stimulus, which is an O/P voltage that represents the stimulation quantity we want to deliver to the tissue.

```{figure} ../Images/L5/VMstim1.png
:label: vm1
:alt: Circuit 1 for VM Stimulus Generation
:align: center
```

The challenges with this method include:

1. Need to maintain the output current within allowable limits 
    * i.e. electrode charge density

2. Monitoring charge delivered to the electrode
    * When we apply a voltage to out electrodes, we can't monitor the amount of charge delivered
    * The solution is a microcontroller with an ADC and a series resistor
    * We can measure the voltage drop over that resistor and get the current from there by integrating the current over time.
    * This gives us the charge delivered to the tissue

Now, in order to **deliver voltage** effectively to a resistance, we need a relatively **LOW resistance compared to the load** (opposite of CM).

So we have 3 possible solutions for our **Voltage Output Stage (Buffer)**:

1. **Source follower**
    * O/P resistance of about $50 \Omega$

2. **Unity gain buffer**
    * O/P resistance of about $1 \Omega$

3. **Voltage regulator**
    * O/P resistance of about $0.1$ - $0.001 \Omega$

```{figure} ../Images/L5/VMstim2.png
:label: vm2
:alt: Circuit 2 for VM Stimulus Generation
:align: center
```

### Charge-Mode Stimulus Generation

Charge delivery is quite simple, we charge up a capacitor to the stimulation voltage and then dump it on the tissue. This stimulation voltage is set by a DAC or voltage reference. 

```{figure} ../Images/L5/QMstim1.png
:label: qm1
:alt: Circuit 1 for QM Stimulus Generation
:align: center
```

The challenges with this method include:

1. Incomplete charge delivery due to charge sharing

2. Limited charge stimulus capacity
    * i.e requiring a large capacitance

### Comparison of 3 Types

```{figure} ../Images/L5/stimuluscompare.png
:label: stimcompare
:alt: Stimulus Generation Comparison
:align: center
```

### Charge Balancing

So how do we charge balance?

One thing we normally do is we always connect our stimulator onto our electrode through a capacitor. The beauty of this is that we never have DC current flow through our capacitor.

Some notes:

* It's the easiest method
* Desirable for safety (single component failure)
* Commonly used for cochlear implants

```{figure} ../Images/L5/chargebal1.png
:label: charbal1
:alt: Charge Balancing Method 1
:align: center
```

Another way we can charge balance is by reusing our current source. So if we have a single current source and we implement what's known as a **H-bridge**, depending on how we close and open out our switches, we can reverse our current.

[LHS](#charbal2) current moving from left to left. [RHS](#charbal2) current is moving from right to left.

Some notes:

* If you're implementing a stimulator using an anodic current source and current sink, then there's the problem of mismatch between the two.
* Whereas here you're reusing the same current source

```{figure} ../Images/L5/chargebal2.png
:label: charbal2
:alt: Charge Balancing Method 2
:align: center
```

We also can have a circuit that basically shorts our electrodes together, and does what we call passive discharging.

Some notes:

* This is the most commonly applied technique to remove residual charge - typically after each stimulation cycle (or after a series of cycles)
* RC time constant (electrode and short discharge path) however can significantly increase the overall stimulation timing

```{figure} ../Images/L5/chargebal3.png
:label: charbal3
:alt: Charge Balancing Method 3
:align: center
```

The final example is where we do a crude charge balancing. So we stimulate, then take out our current, but there might be a bit of residual charge. It's not precisely balanced. So we can look at the voltage on the electrodes and if that voltage is not 0 we can add a few pulses to bring it to 0.

Some notes:

* So we measure delivered charge in cathodic phase, and adjust anodic phase accordingly
* After stimulation cycle is complete (after both phases), monitoring the net charge and compensating using discrete compensating pulses

```{figure} ../Images/L5/chargebal4.png
:label: charbal4
:alt: Charge Balancing Method 4
:align: center
```

```{note} An overall note

When we need to charge balance a voltage mode stimulator or charge based stimulator it's not as simple as a current mode stimulator
```