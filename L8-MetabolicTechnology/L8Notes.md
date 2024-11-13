# Lecture Notes

---

- [ ] Have Revised

## Introduction

This lecture we'll look at metabolic technology and why it's important. Primarily it's used for the management and treatment of **diabetes**.

### Diabetes

So what is diabetes?

Diabetes is a metabolic disease resulting in high blood sugar. It is a result of a **lack of or ineffectual insulin**. This is the hormone made from the **pancreas** that is responsible for glucose absorption - glucose being what fuels our whole body. In effect, glycolysis, the function of cells breaking down glucose, can not be performed without insulin.

We classify diabetes in **2 types**:

1. **Type 1**

    * An autoimmune disease which destroys insulin secreting cells called beta particles in the pancreas
    * Normally occurs at a young age and is referred to as juvenile diabetes

2. **Type 2**

    * Characterised by insulin resistance, which may be combined with relatively reduced insulin secretion
    * Normally occurs at an older age and can brought about by a poor diet and lack of exercise.

Diabetes is huge, it roughly effects 3% of the world's population, and is estimated to reach 6% soon. It is the leading cause of blindness, kidney failure and heart disease in the developed world.

### The Human Metabolic System

[Here](#metabolic) is a diagram of the human metabolic system.

```{figure} ..\Images\L8\metabolic.png
:label: metabolic
:alt: Human Metabolic System Diagram
:align: center
```

Let's look at the very basics of what this does:

* When we eat **food**, it is broken down into **glucose**
* This is responsible for producing **energy** in our cells through a process called **glycolysis**
* Glucose is absorbed by the cells using a hormone called **insulin**
* Insulin is produced by the beta cells of the **pancreas**


#### The Pancreas

So the pancreas is responsible for releasing this hormone called insulin. It consists of clusters of cells called Islets of Langherans. Insulin is produced by specific cells called beta cells. 

* **Beta Cells** - These have sensors which sense the glucose concentration in our blood, and then they release insulin into the blood to make sure it's absorbed by all our cells. Insulin looks to decrease blood glucose.

* **Alpha Cells** - We also have alpha cells, they are responsible for the secretion of glucagon, which looks to increase blood glucose levels.

```{figure} ..\Images\L8\pancreas.png
:label: pancreas
:alt: Pancreas Diagram
:align: center
```

#### Typical Blood Glucose Profile

Blood glucose should be kept between **4-8mM (milli molars)** in a healthy individual.

* For breakfast lunch and dinner, glucose levels go up
* Your body secretes insulin and it brings it back down
* Through all that time, you need to stay in this range

```{figure} ..\Images\L8\glucoseprofile.png
:label: glucoseprof
:alt: Glucose Profile Graph
:align: center
```

The pancreas acts as the body's control system by secreting insulin and glucagon to ensure that the blood glucose levels stay within a safe range.

## Treatment of Type 1 Diabetes

Initially there was no cure for type 1 diabetes, it's autoimmune nature was characterised by the **destruction** of $\beta$ cells of the pancreas - this resulted in **absolute insulin deficiency**. It was likely induced by genetic susceptibility and or a diabetogenic trigger (Genetic, enviormental, viral, diet, etc). It normally expresses itself at a young age.

The current treatment is as follows:

* We use a glucometer and you give it a drop of blood
* Inside is an electrochemical sensor, which tells us the concentration of glucose
* We now have insulin which we can store at room temperature
* If the person sees the blood glucose and performs mental arithmetic to determine whether they need an injection of insulin

```{figure} ..\Images\L8\currentdiabetes.png
:label: currdiabetes
:alt: Current Diabetes
:align: center
```

It should be clear that this is **sub-optimal**, it requires a lot of guesswork and arithmetic:

* **Insulin injection** solves the problem **short-term**
* Diabetics still spend a large amount of time in **hyper-glyceamia**
    * This results in the release of Ketone bodies resulting in ketoacidosis causing destruction of blood capillaries
    * Leading cause of blindness, kidney failure, heart disease, nuerogenic disease
* Through over dosing of insulin, diabetics increase incidence of **hypo-glyceamia**
    * Results in low-glucose to the brain resulting in **coma** and in sever cases death

```{figure} ..\Images\L8\glucoselevels.png
:label: glucoselevels
:alt: Glucose Levels Graph
:align: center
```

### Glucose Sensing Technology

What we currently have in terms of modern technology:

1. Finger Strip **Glucometers**
    * As seen [here](#currdiabetes)
    * These offer a single spot measurement of blood glucose

2. Continuous Glucose Monitoring Systems (CGMS)

    * These offer real time measurement of glucose, of subcutaneous glucose (not directly the blood but fatty tissue)
    * They can communicate wirelessly to a handheld meter or pimp
    * Minimally invasive
    * Need constant calibration and suffers from delays due of up to 5-10 mins

### CGMS

So for this to work we use amperometry with a 3 cell (WE, RE, CE) electrochemical system.

* The working electrode is coated with an enzyme called **Glucose oxidase** (GoX)
* Hydrogen peroxide ($H_2 O_2$) is produced by the reaction of Glucose and GoX
* $H_2 O_2$ is oxidised at $0.7V$
* Therefore the cell potential is given by $V_{WE}-V_{RE} = 0.7$

```{figure} ..\Images\L8\CGMS.png
:label: CGMS
:alt: CGMS
:align: center
```

We have seen [a typical glucose operating curve](#doseresponse), you calculate it and then get your calibration curve. So you know how much glucose you have simply by measuring the current using the [transimpedance amplifiers in L4](#transimpedance)

#### Insulin Pumps

We also have insulin pumps, which hold a reservoir of insulin.

* You infuse insulin subcutaneously through a tube
* And you can program what's called the **'basel rate** of insulin (U/hr) to give you drip units per hour
* You can also press a button to give sudden boluses of insulin, similar to the pen, which you would do before you eat a meal.

```{figure} ..\Images\L8\insulinpump.png
:label: insulinpump
:alt: insulin pump
:align: center
```

### Artificial Pancreas

So with all these technologies we can start to think about a closed loop system. We can call this an **artificial pancreas**

* It's an **artificial** substitute to the biological pancreas
* A **closed loop system** consisting of a glucose sensor, control algorithm and insulin pump
* It offers **automatic glucose control**
* should minimise hyper and hypoglycemia
* Keeps blood glucose in target range **4-8mM**

```{figure} ..\Images\L8\artificialpancreas.png
:label: artificialpancreas
:alt: Artificial Pancreas 
:align: center
```
```{warning} Challenges!
The main hurdles of this is the **CGM accuracy** and **delays** due to the **subcutaneous route**
```

We have a number of different control schemes which have been used for automatic glucose control:

* PID control (Steil 2004)
* MPC control (Hovorka 2004)
* Fuzzy logic (Atlas 2010)
* Sliding mode control (García 2008)
* Neural networks (Takahashi 2008)
* Adaptive control (Takahashi 2008)
* Bio-inspired control (Georgiou 2008)

```{figure} ..\Images\L8\control.png
:label: control
:alt: Control System 
:align: center
```

So the bio-inspired artificial pancreas, trained on human computational models called Silico subjects was able to account for the many challenges faced in creating an artificial pancreas.

```{figure} ..\Images\L8\artpanctrail.png
:label: artpanctrail
:alt: art panc trail 
:align: center
```
Not only that but it also was able to supply glucagon as well, which was tested in an exercise trial.

```{figure} ..\Images\L8\exercisetrial.png
:label: exercisetrial
:alt: exercise trial
:align: center
```
the latest iteration is a handheld controller system that can be connected to an apple watch.

```{figure} ..\Images\L8\latestpanc.png
:label: latestpanc
:alt: Latest Artificial Pancreas
:align: center
```

It has the following components:

1. **BiAP handheld controller**
    * Dedicated medical device 
    * Low power – 3 days use 
    * Small form factor 
    * Bio-inspired Controller 
    * Sensor/pump agnostic 
    * Proven in over 1000 hours of clinical trials 
    * Improved control 
    * No hypoglycaemia

2. **CGM Sensors:**
    * Dexcom G5 
    * Medtronic Enlite
3. **Pumps:**
    * Roche Accuchek 
    * Cellnovo Patch pump 
    * Tandem 