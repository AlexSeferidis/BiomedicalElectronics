# Brain Machine Interfaces

---

- [ ] Have Revised

## Introduction 

**What is a BMI/BCI?**

> “A neural interface that senses neural activity, decodes something useful and uses this for communication or to control an external device”

Although basically the same...

* **BMI** - Is used for invasive (and never non-invasive)
* **BCI** - Is used for non-invasive (but term has been used for both)

The idea is that BMI, the machine has become part of the brain and are closely linked. BCI is referring to an external device.

```{figure} ../Images/L10/exampleuses.png
:label: exampleuses
:alt: exampleuses
:align: center
```

**Biggest Challenges:**

* **Information Transfer Rate** - how many bits per second of useful information
* **Reliability** - Ensure that brain surgery is not necessary every year or 6 months and allow for the system to be reprogrammable to deal with changes over time

### Wearables vs Implantables

We have this important distinction between wearables and implantables.

* We see that everyone wants wearable currently, as noone wants surgery
* However wearables today are very, very uncomfortable and they don't have anywhere near the performance of implantable devices
* Repeatability also is a factor, because wearables cause a change in location of electrodes each time, whereas implants are more stable
* Signal better in implants as closer to source or target
* Compliance is another interesting one, it's basically saying whether someone will use it or not

```{figure} ../Images/L10/wearablevimplantable.png
:label: wearablevimplantable
:alt: wearablevimplantable
:align: center
```

### Applications

* Neuroscience – Investigative tool for brain research
    * Improved device technology – miniaturisation, low power, wireless
    * New opportunities – more channels, more data, better data
* Medical (clinical) – Ultimate end-goal
    * Spinal cord injury, Amputees, Stroke, Locked-in Syndrome
* Consumer devices
    * Brain computer interfaces – eg. Gaming (Emotiv)
    * Merging human/AI

```{figure} ../Images/L10/BCIBMIapplications.png
:label: BCIBMIapplications
:alt: BCIBMIapplications
:align: center
```

## Implantable BMIs

So these are the technologies currently in use, the 2 more mature technologies are known as:

1. **ECoG** - These are electrodes that are placed on the **surface** of the brain, they don't actually go inside the brain, it's like a higher resolution EEG
2. **Micro-Electrode Arrays** - You have these needles that are inserted into the brain tissue itself and you have recording electrodes on the tips of these needles.

Emerging technologies include:

1. **Centralised intracortical** - similar to Neuralink
2. **Intravascular** - Idea is that you can have an electrode array that looks a stent, inserted into the train through a blood vessal like and you can detect neural activity from there. This means you can enter from the head and therefore no brain surgery is required.
3. **Distributed intracortical** - This is an idea of lots of very small devices, drilling holes into the skull and implanting them, so you're not opening up the skull as such. The skull will heal itself over time.

```{figure} ../Images/L10/implantableBMI.png
:label: implantableBMI
:alt: implantableBMI
:align: center
```

### Technical Challenges

1. **Spatial Resolution vs Invasiveness**

    * The idea being that the less invasive you are, the further you are from the brain and therefore the lower your resolution

2. **Size of Electrode vs Number of Electrodes**
    
    * This is also linked to **invasiveness**
    * If you want 10'000 electrodes they're not going to be a cm in area reach, there isn't enough brain

3. **Noise vs Power vs Bandwidth**

    * We can't have low power, low noise, high bandwidth
    * If we want low noise, we have to consume power
    * If we want high bandwidth we have to consume power

```{figure} ../Images/L10/technicalchallengesBMI.png
:label: technicalchallengesBMI
:alt: technicalchallengesBMI
:align: center
```

#### Spatial Resolution vs Invasiveness

So let's look at resolution vs invasiveness, and specifically in the context of some different electrode types:

* **Invasive** - Penetrating electrodes (sub-mm pitch, coverage a few mm)
* **Minimally-invasive** - ECoG (>5mm pitch, coverage a few cm)
* **Wearable** - EEG (>10mm pitch, coverage entire scalp)

So the further you get from the cells, the bigger the electrode gets. Typically we get 2 types of signals (see [topright](#resvsinv)) LFPs and spikes. Smaller electrodes can observe **individual spikes** whereas further away you're measuring hundreds of thousands or even millions of neurones, this is called an LFP (a superposition of all the spikes). We can decode from spikes directly or from LFPs.

```{figure} ../Images/L10/resvsinv.png
:label: resvsinv
:alt: resvsinv
:align: center
```

#### Scalability vs Device Size

We like to think if we put more electrodes in we are going to get better performance - **this is not necessarily true** - More electrodes/channels means more data and this can add useless redundancy to process for particular uses.

We also have a question about where we are putting the electrodes:

* **High density probes** - focused target
* **Low density probes** - wider region


```{figure} ../Images/L10/scalabilitygraph.png
:label: scalabilitygraph
:alt: scalabilitygraph
:align: center
```

#### Signal Integrity (stability/variability)

When we insert and electrode into tissue a lot of things can happen:

* Damage the tissue
* Cause bleeding
* Electrode can start to dissolve
* Mechanical failures - wires breaking due to brain surface jelly

We need to account for the fact that the body will attempt to destroy any foreign object which enters it, therefore we need to use materials that are stable, but also biocompatible so the body doesn't reject it.

```{figure} ../Images/L10/signalinteg.png
:label: signalinteg
:alt: signalinteg
:align: center
```

Signal integrity is also something to consider for non-invasive electrodes (wearables) as well.

* Placement repeatability is important
* SNR
* Signal source can move

#### Energy Efficiency

The issue of energy efficiency is an important one, because **power is proportional to the number of channels**. So if you want 100 times more channels, you need 100 times more power, this means the body will need to dissipate that power.

If we have devices inside us increasing out core body temperature by 1 or 2 degrees, we don't feel very well, and it can cause a lot of damage.

```{warning} IMPORTANT!
Therefore when we implant a device, particularly in the brain, has to limit the temperature rise by half a degree - this puts major constraints on the amounts of power our circuits can consume
```

So our constraints are:

1. **Amount of data we generate**
    * More data = more channels = more power
2. **The energy source itself**
    * If a battery has a finite energy density, the energy density has to last for a certain time
    * If battery is external we have a [lot of losses](#lossestochip) along the way ($\approx 10$%)
    * We also need to consider where is power going to be dissipated along the way, because that will come off as heat and can cause damage
3. **Safety**
    * Generally stay below $10mW/cm^2$
    * keep any temp increase below 1 degree celcius

```{figure} ../Images/L10/lossestochip.png
:label: lossestochip
:alt: lossestochip
:align: center
```

#### Interpreting with "uncertainty"

Another challenge is enterpreting signals without any ground truths. All our brains are **completely different** and our neurones are wired up in completely different ways. 

On top of that our signals are changing over time, electrodes can degrade, neural signals and neurons can change, etc

This poses big challenges for using traditional ML/DL methods on the brain as the training data is constantly changinging and differs greatly between different people, so we have use different methods.

**So how do we generalise?**


```{figure} ../Images/L10/neuronuncertainty.png
:label: neuronuncertainty
:alt: neuronuncertainty
:align: center
```

### Opportunities

Now we've heard all the problems, what are all the solutions currently being proposed?

#### Beyond Medical -> Consumer

Obviously consumer electronics are trying to make headsets more confortable, so they're trying to improve the problem of **compliance**.

There are also efforts in the implantable space to go beyond medical - the challenge being it's not ethical or legal to do anything implantable to an individual without a massive benefit


```{figure} ../Images/L10/consumerelectronic.png
:label: consumerelectronic
:alt: consumerelectronic
:align: center
```

#### New Form Factors / Device Concepts

We can try to explore different geometries, different ideas for electrodes, such as the aforementioned intra-vascular implementation that got inside the blood vessels

```{figure} ../Images/L10/newforms.png
:label: newforms
:alt: newforms
:align: center
```

#### New "Big" Ideas

BCIs communicate by the patient thinking they want to move their arm (for example), this is fundamentally limited by how fast you can move your arm. However if you use another control signal such as speech, you could speak maybe 100-200 words per minute.

Thinking about the information transfer rate of how many bits of information you're able to transfer via speech vs movement of the hand, maybe we can therefore go to the speech cortex rather than the motor cortex. So we think about using different parts of the brain to do different things. 

```{figure} ../Images/L10/bigidea.png
:label: bigidea
:alt: bigidea
:align: center
```

#### ML/DL/AI etc

fMRI scans can extract and help teach models how people are thinking when prompted by given data, images, videos, etc. fMRI basically works by quantifying the amounts of oxygen in different parts of your brain, signalling activity.

```{figure} ../Images/L10/AIop.png
:label: AIop
:alt: AIop
:align: center
```

#### Cultivating a Platform Ecosystem

So we can use the idea that in industry they don't reinvent the wheel, e.g audi and volkswagen are the same company, they make different cars but a lot of the components are the same. We could do this with implants.

This could mean having regular chips that different implants use.

Another model is that of Uber or eBay or the App Store, i.e using a common hardware platform for a number of different devices - this might be able to make developing medical devices and BCIs more effective.

The principal being that if you had some common hardware and were only playing with software it would be easier.

```{figure} ../Images/L10/ecosystem.png
:label: ecosystem
:alt: ecosystem
:align: center
```

### Typical Requirements of BMI

What do we need to record brain activity (I.e. biopotential signals – either at single neuron or macroscopic level) and extract useful information and use it to do something useful.

* Signal conditioning
    * Biopotential pre-amplification, filtering
    * Digitisation, compression
* Communication
    * Transcutaneous biotelemetry
    * Wireless through-air communication
* Signal processing
    * Classification, eg. Spike sorting (feature extraction and clustering)
    * Analysis for multi-dimensional output
* Output - Actuation / Stimulation / Input to computer

### Basic Architecture of BMI

* Electrodes
* Amplifiers
* Filters
* Signal Processing
* We analyse
* Then we either stimulate of communicate

The front-end is typically analogue (amplification + conditioning) and the back-end is typically digital (communication + signal processing)

```{figure} ../Images/L10/BMIarch.png
:label: BMIarch
:alt: BMIarch
:align: center
```
#### Bio-Potential Signals

Our signals of interest are EAPs, LFPs, ECoG or EEG

```{figure} ../Images/L10/BMIpotent.png
:label: BMIpotent
:alt: BMIpotent
:align: center
```

#### Front-end

The front-end requirements are as follows:

* We need a low noise amplifier at the beginning because our signals are micro volt level adn we don't have ADCs or circuits that can interface with that level so we need to amplify
* High I/P impedance - To not affect bio-potential
* Low I/P-referred electronic noise - neural signals very weak
* Constant gain across signal bandwidth
* DC/offset rejection - due to electrode/eletrolyte/tissue interface

```{figure} ../Images/L10/frontend1.png
:label: frontend1
:alt: frontend1
:align: center
```

A typical front end will also have a number of gain stages and a number of filters, it will end in an ADC. The question is, **how do we map our signal at the input onto our ADC, and how do we spec our ADC?**

We have some indicative values [here](#frontend2). Need to design to eliminate the signals of LFPs if we are working with action potentials.

And we design our ADC based on the [signal dynamics](#BMIpotent), so highest potential signal is around 3-5 kHz so Nyquist tells us we should do twice that for our sampling rate.

**Number of bits is usually 6-8 bits but can calculate using noise performance of the amplifier**

```{figure} ../Images/L10/frontend2.png
:label: frontend2
:alt: frontend2
:align: center
```

Below is a typical front-end signal, we can see both the LFPs and the spikes.

```{figure} ../Images/L10/frontend3.png
:label: frontend3
:alt: frontend3
:align: center
```

#### Observation of EAPs

There's another layer of complexity. [See this neurone in grey in the background](#EAPs), what if we put an array of electrodes over the neurone and check the activity?

* Well as you can see we'd see that the closer we get to the body of the neurone the bigger the signal
* But also we observe that the signal changes shape
    * **Spike shape** changes with electrode position and orientation
    * **Spike amplitude** changes with electrode/cell proximity

```{figure} ../Images/L10/EAPs.png
:label: EAPs
:alt: EAPs
:align: center
```

This is an important observation because if you put an electrode in some tissue, it might be that every neurone has a slightly different shape - and so you can use that shape as a signature.

**HOWEVER** each electrode actually picks up signals from **multiple neurons** - Typically 2-3 (but can be 10). We use a method of **spike sorting** to exploit this to a separate single unit activity from neural recordings.

```{hint} Our observed signal (without spike sorting)

So we are looking at...

* Spiking activity of target neuron
* Adjacent neurons
* And the spiking activity of neurones a bit further away (but they have smaller amplitudes)
* As well as the LFP contribution from the thousands of neurones further away (much smaller amplitude) 

So we can't really differentiate them and they're all adding up

```

```{figure} ../Images/L10/observedEAP.png
:label: observedEAP
:alt: observedEAP
:align: center
```

So if we're seeing the [bottom signal](#observedEAP) but we need the [top signals](#observedEAP) to control the BMI, how do we get our desired signal?

#### Spike Sorting (Back-End)

Our solution is **spike sorting**...

1. Take our input signal
2. Apply HPF and amplify
3. Apply spike detection, using a threshold value
4. Every time the threshold is crossed we align all the spike waveforms to the detection point
5. We observe this in different feature spaces, so for each spike we get a spot in feature space (we could also end up doing PCA, wavelet analysis, etc)
6. Then we take our feature space representation (assuming it's a good representation) and start thinking about clustering
7. These clusters classify our different spikes

```{figure} ../Images/L10/spikesort.png
:label: spikesort
:alt: spikesort
:align: center
```

So the purpose of this **spike sorting** is data reduction/compression without compromising quality. i.e. Communicate low bandwidth, high level data instead of raw recordings.

* O/P is typically individual events (i.e. each neurons spike events)
* Spike sorting is typically computationally-intensive (i.e. an offline method)

```{figure} ../Images/L10/spikearch.png
:label: spikearch
:alt: spikearch
:align: center
```

#### Neural Decoding

**So how do we decipher something useful from these recorded signals?** Such as a neuron spike to a desire to move a robotic hand. There are 2 ways:

1. **Using EAPs - Spike Recording**
    * Spike detection - extract multi-unit activity (MUA), simple less targeted
    * Spike sorting - extracts single unit activity (SUA), advanced more targeted
    * These come up with **spike events** which would be converted into an instantaneous spike rate (rate of spiking)
    * Then decode the spike rate

2. **Using LFPs - Field Potentials**
    * Frequency analysis -> power in different bands
    * Similar to what was used in cochlear implants
        * receive a signal every second or half second
        * pass it through FFT
        * And we would then observe different band powers and use that for decoding

```{note} Note!
Spikes are generally more informative and field potentials are more stable
```

Then at the motor end-point, we need to decode for position and velocity:

* We look for patterns in the spike train or frequency content of the signal
* Use signal processing and control solutions
* And possibly some ML/DL/NNs


### BCI/BMI Performance

**Parameters for assessing performance:**
* Accuracy – how well does it decoded the desired target
* Speed – what is the useful output bandwidth (information transfer rate)
* Reliability – what is the stability over time, will it need recalibration?

**Factors affecting performance:**
* Signal to noise ratio
* Stability of neural interface (e.g. electrodes)
* Number of observed channels
* Specific neural target
* Decoding method