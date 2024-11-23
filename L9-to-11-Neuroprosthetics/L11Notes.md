# Retinal Prosthesis

---

- [ ] Have Revised

## Introduction


So this lecture will talk about the neuroprosthetic of **retinal prosthesis**.

### The Visual System

So we'll start with some physiology to get used to the systems and organs we are dealing with. 

So we have this optical system which is projecting the image of the world around. At the **back of the eye** there is a **thin layer of neurons called the retina**.

It actually consists of several layers of neurons, the light goes through these layers of neurones and hits the photoreceptors. There are 4 types of receptors, each better at detecting a certain type of light (dim, bright, colour etc).

**Basically, through the retina an optical signal is turned into an electric signal**

```{figure} ..\Images\L11\retina.png
:label: retina
:alt: retina
:align: center
```

This electrical signal travels up the optical nerve to the visual cortex in the brain. It's important to note that the **brain sees, NOT the eyes**. So actually it goes as follows:

1. Light enters eye and hits retina
2. Retina converts optical signal to electrical signal
3. Signal travels up optical nerve to LGN
4. LGN activates cells, which activate the visual cortex in the back of the brain
5. The brain processes the electrical content to give us visual perception (a process we don't know much about)

### Disorders of the Visual System

[As you can see](#visualdisorder) there are many things that can go wrong with this visual system

```{figure} ..\Images\L11\visualdisorder.png
:label: visualdisorder
:alt: visualdisorder
:align: center
```

```{note} Note!
About 150 different genes are required for proper functioning and operation of photoreceptor cells
```

We have a number of current emerging treatments:

* Gene therapy
* Stem cells
* Retina transplants
* Drug therapies
* Retinal Prosthesis (Electrical, Optogenetic, etc)

## Retinal Prosthesis 

**The aim of retinal prosthesis is to restore sight by electrically stimulating the remaining neurons in the retina**

Degenerately, neurons inside the retina can start to die, causing blindness. It's difficult to discriminate and stimulate individual neurons and therefore we perform ES on any remaining neurones.

Retinal prosthesis generally has 2 parts, one inside the body and another outside.

```{figure} ..\Images\L11\retinalprost.png
:label: retinalprost
:alt: retinalprost
:align: center
```

1. **Outside**

    * Camera
    * Video processing
    * Signal/Power Tx, giving instructions to the stimulator (when and where to)

2. **Inside**

    * Now passing the data into the eye
    * We have the stimulator cables and electrodes
    * Finally the stimulator which delivers the signal

### Position of Stimulation

There are typically 3 positions for ES of the retina for retinal prosthesis

1. **Epiretinal**
    * So it's all at the back of the eye, directly stimulating the retinal ganglion cells

2. **Sub Retinal**
    * So this is the layer where the actual photoreceptors are
    * So for some degenerative processes like retinitis pigmentosa, the photoreceptorsare the ones dying.
    * Logically then in some case it makes sense to put the stimulator here

3. **Supra Choroidal**


```{figure} ..\Images\L11\ESpositions.png
:label: ESpositions
:alt: ESpositions
:align: center
```

### Epiretinal Prosthesis - Argus II

Some time ago [this](#epiret1) was the only retinal prosthesis on the market.

```{figure} ..\Images\L11\epiret1.png
:label: epiret1
:alt: epiret1
:align: center
```

The architecture works as follows:

* Goggles - mounting device, and masks implant
* Camera - gets signal and sends to visual processing unit
* Video Processing Unit - performs signal processing, this creates data which is sent via telemetry inside the eye
* SoC - some processing electronics alongside some receiving coils to pick up the incoming signal
* Stimulator - to deliver processed signal to NS

```{figure} ..\Images\L11\epiret2.png
:label: epiret2
:alt: epiret2
:align: center
```

#### Technological Challenges:

Creation of a successful epiretinal prosthetic system requires advanced:
1. microelectronic design
2. wireless communication
3. microsystems (including electrodes and packaging)
4. Stimulation of retinal ganglion cells means loss of many features of natural retinal processing - hence need for good video processing algorithms

Microelectronics will perform several functions in a retinal prosthesis, including wireless communication and producing stimulus current in the implant.

#### Architecture

So [here](#epiret3) is the architecture of the 256 channel epiretinal prosthesis.

```{figure} ..\Images\L11\epiret3.png
:label: epiret3
:alt: epiret3
:align: center
```

In this implementation each pixel has individual electronics, starting with the external devices:

* Camera
* Signal Processor
* DPSK data encoding 
* Coil which then passses encoded data to the Rx side (typically sending 2Mbps)
* And an externally padded Tx (typically sending 100mW), which works with the power management system 
    * Internally this is received using capacitors, diodes and a power regulator to keep the voltage rails stable

On the inside we have the following:

* Rx coils for the aforementioned encoder and power management
* Rx/Decoder for DPSK
* Controller to program and send the appropriate signals to the stimulator, electrode array

#### Stimulation 

The stimulation is similar to what we've seen before. Recall the following requirements:

* **Effective** - Strong enough stimulation to achieve the stimulation threshold for targeted cells
* **Safe** - Not too strong to avoid tissue damage

```{figure} ..\Images\L11\epiret4.png
:label: epiret4
:alt: epiret4
:align: center
```
```{note} Note!
Empirically it has been shown that anodic first is more effective than cathodic first
```

It's important to remember (particularly for exams) that we typically have arrays of electrodes, not just one. We have a question of how to stimulate these electrodes. This is where we introduce **electrode scanning patterns** . Here are [some typical scanning patterns](#epiret5).

```{figure} ..\Images\L11\epiret5.png
:label: epiret5
:alt: epiret5
:align: center
```

#### Phosphenes

So what is actually seen by a patient using retinal prosthesis? It's something called phosphenes.

**Phosphenes** - Images of light or colour that you can usually see while your eye is closed, or when you rub them.

```{figure} ..\Images\L11\epiret6.png
:label: epiret6
:alt: epiret6
:align: center
```

So these phosphenes are seen as bright flashes during electrical stimulation. The brain can only pick this up as noise. [Here](#epiret6) we see where the electrodes map to the users actual vision, this is where the phosphenes will be seen.

#### Clinical Tests

The clinical trials for the Argus II had a total of 30 patients, all subjects see **phosphenes** with the system. They were followed up for a minimum of 6 months and up to 2.7 years.

There were 3 types of visual activity used to test the performance of the device:

1. **Square localisation** - Present a white square and ask them to touch it when the system is on and off
    * [See that](#epiret7) the accuracy was much higher with it on than off 
2. **Direction of Motion** - Here they were presented with a white bar on screen going from left to right and they were asked to say which direction it was going

```{figure} ..\Images\L11\epiret7.png
:label: epiret7
:alt: epiret7
:align: center
```
3. **Follow-the-Line Task** - Follow the white line course

4. **Find-the-Door Task** - Find the door on a white background

```{figure} ..\Images\L11\epiret8.png
:label: epiret8
:alt: epiret8
:align: center
```
The results were not perfect but showed some significant improvement in areas. Subjects performed statistically better with the system ON versus OFF in the visual tasks:

* 96% of subjects improved in object localization
* 57% of subjects improved in motion discrimination
* 23% of subjects improved in the discrimination of oriented gratings 

### Business and Market

Here's a timeline for **Second Sight**, the business responsible for the Argus II:

* 1998 - Founded
* 2002 - Commenced clinical trials in the US for the Argus I (2-16 electrodes)
* 2007 - Commenced clinical trials for Argus II (60 electrodes)
* 2011/13 - CE Mark in Europe / FDA approval for Argus II
* 2019 - Approx 60-80 implants per year, 120 employed in development, manufacture and commercialisation
    * 350 implanted over 13 years (now stopped)
    * Approx 300 million dollars of investment
    * Net revenue of 7-8 million dollars and incurred a net loss of 30-35 million dollars per year
    * Total accumulated deficit through Dec 31, 2018 was 270 million dollars
* 2022 - Merged with NPM, renamed to Vivian Medical and stopped producing Retinal Prosthesis

> “We have not been profitable to date and expect our operating losses to continue for the
> foreseeable future; we may never be profitable”

So some things are very clear:

* Earnings are low and costs are high due to procedural costs
* The size of the market is quite small, only a small subset of the 375000 legally blind people worldwide are eligible for the Argus II
    * This is due to legislation / approval in different countries
    * And that the approved baseline vision for the Argus II system is worse than legally blind (20/200)

So what is the **solution**?

**Orion - Visual Cortical Prosthesis**, the direct stimulation of the brain.

The advantage is that this Visual Cortical Prosthesis covers a **much bigger market** than retinal prosthesis. They include individuals blind from glaucoma, diabetic retinopathy, optic nerve disease and eye injury.

The disadvantage is it is **more invasive**, it's further down the visual pathway and hence harder to create the appropriate stimulus, because there is very little link between the spatial topology of the electrodes and the perceived image in the brain of the electrodes position.


## Subretinal Prosthesis

Recently more investment has been made into subretinal prosthesis.

```{figure} ..\Images\L11\subret1.png
:label: subret1
:alt: subret1
:align: center
```

An example is the Pixium, however even this one is as of 2024 asking for a buyer:

```{figure} ..\Images\L11\subret2.png
:label: subret2
:alt: subret2
:align: center
```
```{figure} ..\Images\L11\subret3.png
:label: subret3
:alt: subret3
:align: center
```

## Challenges

There are some estimated **resolution requirements** for the Artificial Retina. In our actual eye we have around 100 million rods and 7 million cones, this is difficult to match given the following requirements:

* Unaided Mobility
    * 256-600 pixels
* Reading Large Print/Recognizing faces
    * 1024 pixels
* Reading regular print at regular reading speed
    * 10,000 pixels

**Power consumption** is also an important consideration, we need to consider different electrode sizes for different applications and resources:

```{figure} ..\Images\L11\stimulusthreshold.png
:label: stimulusthreshold
:alt: stimulusthreshold
:align: center
```

So to summarise we have to deal with the following problems:

1. serious technological problems due to biocompatability
    * RGC stimulation, so far, produces only white spots in the brain essentially only noise - very fine tuning is needed
2. power consumption
3. complex surgical intervention on the eye
4. limited resolution

Our alternatives to retinal implants are:

1. Optic Nerve stimulation
2. Cortical Implants
3. Optogenetic Retinal Prosthesis
4. Using other senses for conveying the visual information to the brain (“Seeing” with tongue, “Seeing” with sound)