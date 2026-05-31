---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart: Machine 1
This chart shows the individual measurements for Machine 1, along with the process mean, Upper Control Limit (UCL), and Lower Control Limit (LCL). It helps to monitor if the process is stable and in statistical control.

**Observations:**
- The process appears to be...
- All points are within...
:::

::: {.column width="50%"}
![](media/plots/machine1_control_chart.png)
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Chart: Machine 1
This chart displays the distribution of measurements against the Upper (USL) and Lower (LSL) Specification Limits, along with an overlaid normal distribution curve. It helps to visualize how well the process fits within the acceptable limits.

**Observations:**
- The measurement distribution is...
- The process variation is...
:::

::: {.column width="50%"}
![](media/plots/machine1_capability_chart.png)
:::
::::

---

### Cpk Calculation: Machine 1

For Machine 1 (Pressure = 200kPa, Temperature = 338K):

- **Upper Specification Limit (USL):** 55
- **Lower Specification Limit (LSL):** 45
- **Calculated Cpk:** `3.57`

---

### Capability Assessment: Machine 1

**Conclusion:**
The process is CAPABLE (Cpk = 3.57 >= 1.33).

Machine 1 is operating...

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart: Machine 2
This chart shows the individual measurements for Machine 2, along with the process mean, Upper Control Limit (UCL), and Lower Control Limit (LCL). It helps to monitor if the process is stable and in statistical control.

**Observations:**
- The process appears to be...
- All points are within...
:::

::: {.column width="50%"}
![](media/plots/machine2_control_chart.png)
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Chart: Machine 2
This chart displays the distribution of measurements against the Upper (USL) and Lower (LSL) Specification Limits, along with an overlaid normal distribution curve. It helps to visualize how well the process fits within the acceptable limits.

**Observations:**
- The measurement distribution is...
- The process variation is...
:::

::: {.column width="50%"}
![](media/plots/machine2_capability_chart.png)
:::
::::

---

### Cpk Calculation: Machine 2

For Machine 2 (Pressure = 200kPa, Temperature = 338K):

- **Upper Specification Limit (USL):** 55
- **Lower Specification Limit (LSL):** 45
- **Calculated Cpk:** `1.66`

---

### Capability Assessment: Machine 2

**Conclusion:**
The process is CAPABLE (Cpk = 1.66 >= 1.33).

Machine 2 is operating...

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart: Machine 3
This chart shows the individual measurements for Machine 3, along with the process mean, Upper Control Limit (UCL), and Lower Control Limit (LCL). It helps to monitor if the process is stable and in statistical control.

**Observations:**
- The process appears to be...
- All points are within...
:::

::: {.column width="50%"}
![](media/plots/machine3_control_chart.png)
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability Chart: Machine 3
This chart displays the distribution of measurements against the Upper (USL) and Lower (LSL) Specification Limits, along with an overlaid normal distribution curve. It helps to visualize how well the process fits within the acceptable limits.

**Observations:**
- The measurement distribution is...
- The process variation is...
:::

::: {.column width="50%"}
![](media/plots/machine3_capability_chart.png)
:::
::::

---

### Cpk Calculation: Machine 3

For Machine 3 (Pressure = 200kPa, Temperature = 338K):

- **Upper Specification Limit (USL):** 55
- **Lower Specification Limit (LSL):** 45
- **Calculated Cpk:** `1.09`

---

### Capability Assessment: Machine 3

**Conclusion:**
The process is NOT CAPABLE (Cpk = 1.09 < 1.33).

Machine 3 is operating...

---
# Bibliography
<div id="refs"></div>
