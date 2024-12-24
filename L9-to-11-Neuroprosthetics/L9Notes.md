# Cochlear Implants

---

- [ ] Have Revised

## Introduction to Neural Prosthetics

This is the first of 3 lectures which come under Neural Prosthetics. these are medical devices which **interact with the NS**.

These come in the form of 3 case studies:

1. Cochlear Implants
2. Brain-Machine Interfaces (BMI)
3. Retinal Implants

In Europe it was found that around 1 in 4 people either had a neurological condition or a mental health condition.

```{figure} ../Images/L9/stats.png
:label: statgraph
:alt: Graph of Number of People Suffering from Neurological Disease
:align: center
```

The first thought for treatment for all these conditions is medicine, however there any many conditions medicine cannot fix, such as strokes or a traumatic head injury. If in the case medicine is not an option and surgery is also not an option, then we look to medical devices.

Basically at the moment we have a lot of things such as dementia, epilepsy and Parkinson's that do not have ideal solutions for them. There's a huge opportunity for improvement.

### "erooM's Law"

That bring us to **"erooM's Law"**, the opposite of Moore's law. Basically what we are seeing is that in contrast to Moore's law, where everything is getting exponentially cheaper, developing new drugs for neurological conditions today costs more than 10 billion dollars.

```{figure} ../Images/L9/erooM.png
:label: erooMgraph
:alt: Graph of erooM's Law
:align: center
```

This isn't because it costs more to develop a drugs than before, it's simply that for every successful drug, there's now 250 failures. 

**Why is that?**

1. **The Blood-Brain Barrier** - Oral medicine cannot penetrate your NS, and it's extremely undesirable to have an injection directly into your spinal cord due to complications. So it's really difficult for drugs to reach your NS.

2. **Complicated Disease Mechanisms** - These mechanisms to do with brain and NS are generally extremely complicated so it's difficult to develop new therapies based on medicine. 

### Neural Interfaces

**So what are Neural Interfaces?**

**Neural Interfaces** - The direct connection of technical components to the brain or NS

* They can restore our typical functioning or even enhance, we generally use these to treat **neurological conditions**
* They could transform medicine and change how we interact with technology and each other

```{figure} ../Images/L9/neuralinterfaces.png
:label: neuralinterfaces
:alt: Plot of different Neural Interfaces
:align: center
```

[Here](#neuralinterfaces) is a plot detailing current devices which stimulate the NS vs observe/record the NS. On the left we have wearable devices, outside of the body and on the right we have implantable devices inside of the body. 


### Neural Prosthetics

**Neural Prosthetics** - Something we add to our bodies which interact with the brain and/or NS.

We have 3 kind of classes:

1. **Sensory Prosthesis** 
    * These are generally I/P devices
    * Used if you have some sensory impairment such as deafness, blindness or problems with balance.
    * Could be an external electronic device to sense and then communicate it to your brain
2. **Cognitive Prosthesis** 
    * These are things that interact internally with the brain with highler level processes
    * Used to address certain symptoms
3. **Motor Prosthesis**
    * Opposite of sensory, it gets signals FROM the brain
    * Used if you have some kind of spinal cord injury, if you're an amputee or have some kind of paralysis

```{figure} ../Images/L9/neuralprosthetics.png
:label: neuralprosthetics
:alt: Images of different Neural Prosthetics
:align: center
```

## Cochlear Implants

This first lecture will cover **Cochlear Implants**. 

### Market and Target Use

The Cochlear Implant has 2 use cases:

1. Somebody that used to be able to hear, that lost hearing due to medication or trauma
2. OR babies born with some deficits/issues to do with the inner ear

Currently there are well over a million implants currently in use. These devices are NOT cheap, they usually cost between 50000-100000 dollars each, over the lifetime of the patient (the device itself might only cost 5000-10000 dollars). The majority of the cost is actually for the surgery, the follow-up care etc - not the device itself.

```{note} Note!
This treatment is almost always covered by health services and insurance.
```


### Inner-Ear Anatomy

The ear basically has 3 portions:

1. **The outer ear** - this is what we see, it's a mechanical device which focuses a sound pressure wave onto the ear drum - the boundary of the outer ear and middle ear
2. **The middle ear** - Made up of 3 tiny bones (smallest in the body), when the eardrum moves, it causes a vibration through the 3 tiny bones. These connect to an organ called the **cochlea**
3. **The inner ear** - The cochlea is the inner ear, a spiral type structure where the resulting wave travels through a fluid filled membrane that gets progressively thinner, the thinner it gets the lower the frequency of the waveform. Along the cochlea are frequency-triggered hairs whose movement cause neurons to spike and fire towards the brain.

it's basically a mechanical impedance matching system, where a sound pressure wave turns into a vibration that propagates through the cochlea.


```{figure} ../Images/L9/innerear.png
:label: innerear
:alt: Diagram of Inner Ear Anatomy
:align: center
```

The most common causes for deafness is the hair cells in the cochlea are damaged and basically fall off and so this sound pressure wave is still propagating through the cochlea, it just doesn't cause any sensation.

**So a cochlear implant basically inserts an electrode array into the cochlea and they activate the underlying neurons**

### Typical Cochlear Implant

```{figure} ../Images/L9/cochlearimp.png
:label: cochlearimp
:alt: Diagram of Cochlear Implant
:align: center
```

[Here](#cochlearimp) is a typical cochlear implant, typically behind the ear, where it is embedded in the skull and the electrode array is inserted into the cochlear. This is a relatively low risk, standard surgery.

Here's the general procedure and a timeline:

* Incision made behind the ear, and surgeon drills recess into mastoid bone, to inset the receiver
* Inner ear also accessible through mastoid for electrode insertion (this avoids distrubing the ear canal and eardrum)
* Small opening is made into cochlear and electrode is threaded in as far as possible
* Incision closed with hidden absorbable stitches
* The surgery lasts a few hours (1-5) and patients are usually discharged the same day.
* Implant is left to stabilise for about a month, then an audiologist will turn it on and calibrate for the first time


```{figure} ../Images/L9/electrodearray.png
:label: electrodearray
:alt: Diagram of Cochlear Implant and Electrode Array
:align: center
```
[Here](#blockdiagramcoch) is a **block diagram** of a typical cochlear implant. 

1. On the left you have what's outside the implant
    * Like a microphone to get the audio signal
    * We then have an amplify chain, and a bunch of BPFs which decrease further up the electrode array
    * You then try to calculate the power in each band and translate that into a stimulation magnitude
2. In the middle is the actual implant,this takes all the inputs from the different channels, converts them into stimulus pulses and then it sequences them.
    * This is basically TDM, so it wills timulate channel 1 first, then channel 2, then 3, etc.
3. Finally you have the electrode array which is responsible for delivering the processed stimuli


```{figure} ../Images/L9/blockdiagramcoch.png
:label: blockdiagramcoch
:alt: Block Diagram of Cochlear Implant
:align: center
```

```{warning} Number of Channels
:class: dropdown

We know that as the number of channels (mimicking hair cells) increase, the better the sound heard by the patient, HOWEVER if we were to have 20'000 electrodes like we have 20'000 hair cells that they would be too close together so that when we try stimulating we will see no difference to having 20.

**This is because the second you inject charge into a fluid, it goes everywhere. Therefore there is a minimum possible resolution**
```

### Processing Strategy

**So how do you go from powering each frequency band to actually stimulating electrodes?**

#### Compressed Analogue (CA) Strategy

* Very first implants used this strategy
* They took the outputs of the filters
* Compressed them like a logarithm or square root compression
* Then applied that analogue signal directly onto the electrode

**This wasn't very effective** - This is because stimulating multiple electrodes at the same time doesn't work well, current goes everywhere and you get lots of destructive interference.

```{figure} ../Images/L9/ca.png
:label: ca
:alt: Compressed Analogue Cochlear Implant
:align: center
```

```{hint} More on the above diagram
:class: dropdown

* AGC reduces the dynamic range
* Signal is filtered into 4 filter bands and appropriately amplified
* Stimulation waveform is an analgoue signal as opposed to a biphasic pulse
```

#### Multi-Peak (MPeak) and Spectral-Peak (Speak) Stimulation Strategy

* 2nd strategy was Multi-Peak and Spectral-Peak (they're quite similar)
* Come up with a spectogram of what your incoming sound looks like at any moment in time, and then pick a few points (like the peaks)
* From there it will stimulate just those channels because that's where most of the power is
* So rather than stimulating 22 channels we stimulate key components
* These are 'interleaved' meaning they also are not stimulated at the same time

Below is an example of a MPeak system.

```{figure} ../Images/L9/Mpeak.png
:label: Mpeak
:alt: Mpeak Cochlear Implant
:align: center
```

#### Continuous Interleave Sampling (CIS) Strategy

* CIS is probably the simplest strategy, it's basically TDM
* It's used the most and found to be the most effective
* You cycle through channels, giving a stimulus pulse maybe every millisecond and you're stimulating all the frequencies
* So the frequencies are skewed in time - this makes sense because the way the sound wave travels through the cochlea, not all frequencies are stimulated at the same time

```{figure} ../Images/L9/CIS.png
:label: CIS
:alt: CIS Cochlear Implant
:align: center
```

### Monopolar or Bipolar Electrodes

**We also have the question of whether we want monopolar or bipolar electrodes**.

Both have been used and there are advantages both ways.

1. **Bipolar**

    * Bipolar allows you to have 2 electrodes very close to every site, so you can target better than monopolar
    * The downside being if you have 2 electrodes very close to each other, and the cells are away, when you stimulate between the 2 electrodes, most of the current will go directly from one electrode to the other - only a small part to actually activate the neurons
    * This means that we have low power efficiency for bipolar
2. **Monopolar**

    * Only one electrode per site
    * However other electrode is far away - so more current going between return electrode and active electrode so you're getting much more efficient activation of tissue

```{figure} ../Images/L9/monovsbi.png
:label: monovsbi
:alt: monovsbi Cochlear Implant
:align: center
```

## Case Study

So now let's go through a case study, [this](#cimplantcasestudy) was developed at Imperial about 20 years ago. 

It contained the following:

* Input (from microphone) – typically external
    * Audio signal processing
    * Cochlear processing
* Output (to electrode array) – typically implanted
    * Stimulation circuits
    * Patient fitting circuits
* Auxiliary
    * Power/Data transfer
    * Power management
    * Reference circuits
    * System settings


```{figure} ../Images/L9/cimplantcasestudy.png
:label: cimplantcasestudy
:alt: cimplantcasestudy Cochlear Implant
:align: center
```

This was produced recently after there was [a new electrode array that could curl around the cochlea](#electrodearray). This meant the electrode could get much closer to the membrane. Therefore the stimulation magnitudes went from hundreds of microamps, to a few tens of microamps - This reduction in power made it possible to envisage a completely implantable cochlear device.

* The problem was the majority of power consumption was actually from the signal processing and amplification, rather than the stimulation.

* So a new low-power analogue signal processor was developed to process everything in analogue but had a digital component to check on it 

### Dynamic Range

The real challenge to developing a cochlear implant is the [huge mapping of dynamic range](#dynamicrangemap). We can sense 120 dB, which is 6 orders of magnitude of sounds - electronics struggle to work at such a high dynamic range.

Most importantly, looking at the dynamics electrical stimulation can achieve, it's really limited. The maximum number of different values that we can perceive as an effect of valuing the magnitude of stimulation is only 6-20 dB.

```{figure} ../Images/L9/dynamicrangemap.png
:label: dynamicrangemap
:alt: dynamicrangemap Cochlear Implant
:align: center
```

**So how do we sense the whole dynamic rang eof human hearing with such a limited range?**

1. **Volume control** - If you have volume control then you can have essentially a sliding window that you can move up and down
    * There are signal processing techniques that can do this automatically - Automatic Gain Control (AGC)
2. **Filter Compression** - Then the filters perform some kind of compression from the signal processing mapping
    * We can just do the logarithm of it, and that logarithm will be what we use to stimulate with

These system components combined enable use to perceive very loud and very faint sounds.

**Dynamic range fitting** was implemented using a bunch of current mirrors that do scaling:

```{figure} ../Images/L9/CMdynamic.png
:label: CMdynamic
:alt: CMdynamic Cochlear Implant
:align: center
```

### Filter Architecture

Most cochlear implants these days use BPFs, this is because they're easy to implement and they've been proven to work and they have a sharp roll-off due to electrode current spread. They can also be independently reconfigured.

the actual filter of the ear can be seen [on the left](#filterarch), this is called the gamma tone response. We don't try to emulate this because it's actually too difficult and doesn't provide a good trade-off for human use.

```{figure} ../Images/L9/filterarch.png
:label: filterarch
:alt: filterarch Cochlear Implant
:align: center
```

### Stimulation Strategy

The way the stimulator was created is you had a bunch of circuits, each one served a single electrode and then there was an FSM that told the system which electrode is active. Using a token that token would be passed from channel to channel, when the channel had a token (a digital high), it would be active.

**This effectively implemented CIS** - and it allowed for simplistic increasing and decreasing of number of channels.

```{figure} ../Images/L9/stimulationFSM.png
:label: stimulationFSM
:alt: stimulationFSM Cochlear Implant
:align: center
```

```{note} Note!
You could also implement this with a counter and a decoder on each channel
```

### Power and Bio-Communication

So obviously there are no wires exiting the body, so they needed to figure out a wireless means for recharging the circuit, but also for reprogramming it.

An [inductive system](#inductivesystem) was developed by which you could recharge the battery but also, via the carrier wave provided to the inductive system, re-program the device by sending a digital bitstream.

```{figure} ../Images/L9/inductivesystem.png
:label: inductivesystem
:alt: inductivesystem Cochlear Implant
:align: center
```

So [this plot here](#inductiveplot) shows the test signal.

1. Unmodulated carrier
2. Modulated carrier
3. Then insert a bunch of 1s and 0s
4. And then you could come up with an envelope that can detect 1s or 0s

```{figure} ../Images/L9/inductiveplot.png
:label: inductiveplot
:alt: inductiveplot Cochlear Implant
:align: center
```

### Actual Chip

[Here's](#actualchip) what the actual chip looked like. We have the analogue on one side and the digital on the other, to protect the analogue from the digital noise.

```{figure} ../Images/L9/actualchip.png
:label: actualchip
:alt: actualchip Cochlear Implant
:align: center
```

**How long do these last?**

* **Current state-of-the-art cochlear implants consume 7-8mA**
    * Power One Implant Plus Battery: 570mAh => 4.5 days @ 16.h hrs/day

However an implantable battery doesn't have the capacity of these Zinc-air batteries. Zinc-air around 600mAh whereas implantable have around 15mAh.

A typical cochlear implant requires 15-18hr per day use, so with the batteries available, this gives us a very specific power budget limitation.


## Bone Anchored Hearing Aids

It's important to note that cochlear implants assume that the nerve that connects the brain, the **auditory brainstem** is intact, otherwise the cochlear implant isn't going to do anything.

**Cochlear Implants** only addresses problems in your outer ear, middle ear and inner ear by bypassing all these steps entirely.

[This](#boneanchor) is a kind of implant that works when your middle ear is damaged but your cochlear is fine.

* They implant a bolt into your skull
* Then they have an external device that transfers sound as a vibration through your skull
* This vibration reaches the cochlear (which is surrounded by bone) and you can hear again

```{figure} ../Images/L9/boneanchor.png
:label: boneanchor
:alt: boneanchor Cochlear Implant
:align: center
```

## Auditory Brainstem Implants (ABI)

Say somebody has a tumour on that nerve between the cochlea and the brain:

* Typically what will happen is a surgeon will go in and will cut the nerve out
* This means you will lose all your hearing
* To restore hearing the only way is to go directly to the brain!

The devices used are called **ABIs**. These go to the auditory part of the brain and they put electrodes in and stimulate the brain directly.

```{figure} ../Images/L9/ABI.png
:label: ABI
:alt: ABI Cochlear Implant
:align: center
```

## Intra-Neural Implant (INI)

This is one more bit of research, which is a type of implant. Here, instead of connecting to the cochlea it connects to the nerve between the cochlear in the brain.

* The idea behind this is instead of having an electrode array implant in the cochlea you can have an INI into the cochlear nerve
* The hopes of this is that it will create better selectivity as it is a solution to the issue of current spreading
* However the challenge is you're actually damaging the nerve by putting something in it

```{figure} ../Images/L9/INI.png
:label: INI
:alt: INI Cochlear Implant
:align: center
```

```{note} Note!
This isn't clinically available yet and is currently just a field of research
```