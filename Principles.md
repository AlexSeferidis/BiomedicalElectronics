# Principles

---

- [ ] Have Revised

## Application of Biomedical Electronics

* <span style="color:red"> Monitoring </span> - of biological / physical signals 
    e.g heart rate, glucose, etc...

* <span style="color:red"> Diagnosing </span> - certain conditions
    e.g DNA mutators, cardiac arrhythmia

* <span style="color:red"> Replacing </span> - biological function
    e.g artificial organs, limbs

* <span style="color:red"> Stimulating </span> - certain organs
    e.g deep brain stimulation, pace maker

--- 

## Must-haves:

* <span style="color:red"> Unobtrusive </span> - Small in size and easy to use
* <span style="color:red"> Ultra-low power consumption </span> - Long battery life
* <span style="color:red"> 24/7 monitoring / local processing </span> - Immediate response for critical conditions
* <span style="color:red"> Wireless </span> - Transparent to user, autonomous
* <span style="color:red"> Low cost </span> - Disposable, mass deployment

---

## Biomedical Electronic Systems

Now lets have a look at a general system...

```{figure} \Images\L1\systemdiagram.png
:label: systemd
:alt: General System Diagram
:align: center
```
• <span style="color:red">Measurand</span>
    – The physical quantity, property or condition that the system measures. eg. bi-potentials,
    chemical concentrations, pressure, displacement.

• <span style="color:red">Sensor</span>
    – Transduces energy from one form to another. Conveys physical measurand to an electrical
    output. e.g pH/glucose sensor, accelerometer, ECG instrumentation.

• <span style="color:red">Signal Conditioning</span>
    – Treat the signal for to enhance detection, further processing and communication. e.g
    Amplification, Filtering, Analogue to digital conversion

• <span style="color:red">Auxiliary Elements</span>
    – Calibration signal with the properties of the measurand. Can elicit the measurand, adjust
    sensor and signal conditioning blocks. e.g Dynamic range adjustment, resolution.

• <span style="color:red">Feedback</span>
    – Application of stimulus, electrical/chemical to the body. Can be either a result of a trend in the
    measurand or a time-based therapy. e.g Electrical stimulation, Drug infusion.

• <span style="color:red">Data Transmission</span>
    – Transmit the information from the body/device for further use. e.g Wireless, wired to a
    screen.

---

## Design Considerations for Medical Devices

```{figure} \Images\L1\designcon.png
:label: systemcon
:alt: Design Considerations for Med
:align: center
```

---

## Types of Medical Electronics

<span style="color:red"> Bench Tops </span>:
    
* Diagnose a sample after extraction
* Used in dedicated labs
* e.g DNA sequencing, blood gas analysers, ultrasound

<span style="color:red"> Handheld Electronics </span>:

* Small scale diagnostic / monitoring machine
* Portable
* e.g blood glucose meters, point-of-care diagnostic devices

<span style="color:red"> Lab-On-Chip </span>:

* Typically uses semiconductors integrated with micro-fluidics to analuse samples on the small scale
*  Can achieve mass integration via large scale sensing arrays
*  e.g DNA sequencing

<span style="color:red"> Wearable Electronics </span>:

* Typically worn on body and monitors a specific condition or vital sign
* Needs to be unobtrusive
* e.g heart rate monitor, blood oxygen reader (oximeter), etc


<span style="color:red"> Injestable </span> / <span style="color:red"> Swallowable Electronics </span>:

* Transient implant capable of monitoring, imaging and delivering drugs
* Due to size constraints, power is sent inductively
* e.g Pill cameras, chemical sensors

<span style="color:red"> Implanatable Electronics </span>:

* Typical for long-term to monitor / stimulate for a chronic condition
* Invasive procedure required
* Typically rechargable battery
* e.g pace makers, neural probes, etc...

```{note} Note
:class: dropdown
Should have a battery life cycle of more than 100 years
```


<span style="color:red"> Prosthetics </span>:

* Artificial device extension that replaces a missing body part
* Can be implanted
* Typically coupled with sensory information