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

# Bibliography
<div id="refs"></div>

---

:::: {.columns}
::: {.column width="50%"}
### Math Score Distribution
Here's the distribution of Math scores:
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/math_score_histogram.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::

---
## Distribution of Math Scores

<div class="columns">
  <div class="left">
    <p>This histogram visualizes the distribution of Math scores from the <code>bigclass</code> dataset. We can observe the frequency of different score ranges. The scores appear to range from approximately 200 to 800, with a notable concentration around the mid-range.</p>
    <p>The histogram uses a bin width of 50 to group the scores, providing a clear overview of where most students fall within the Math score spectrum.</p>
  </div>
  <div class="right">
    <iframe data-src='media/plots/math_histogram.html' width='100%' height='500px' style='border:none;'></iframe>
  </div>
</div>

---
## Bar Chart of Math Scores

<div class="columns">
  <div class="left">
    <p>This bar chart displays the distribution of Math scores, grouped into 50-point bins. Each bar represents the frequency (count) of students whose Math scores fall within that specific range.</p>
    <p>This visualization allows for an understanding of score concentrations across different intervals, providing an alternative perspective to the histogram and highlighting the counts per score bracket.</p>
  </div>
  <div class="right">
    <iframe data-src='media/plots/math_barchart.html' width='100%' height='500px' style='border:none;'></iframe>
  </div>
</div>

---
## Bar Chart of Math Scores

<div class="columns">
  <div class="left">
    <p>This bar chart displays the distribution of Math scores, grouped into 50-point bins. Each bar represents the frequency (count) of students whose Math scores fall within that specific range.</p>
    <p>This visualization allows for an understanding of score concentrations across different intervals, providing an alternative perspective to the histogram and highlighting the counts per score bracket.</p>
  </div>
  <div class="right">
    <iframe data-src='media/plots/math_barchart.html' width='100%' height='500px' style='border:none;'></iframe>
  </div>
</div>

---

:::: {.columns}
::: {.column width="50%"}
### Distribution of Age
This histogram visualizes the distribution of ages within the `bigclass` dataset. Each bar represents the frequency of individuals within a one-year age bin.

This plot helps us understand the age composition of the dataset, showing where the majority of individuals are concentrated and the overall spread of ages.
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/age_histogram.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Average Math Score by Sex
This bar chart illustrates the average Math scores for male and female students in the `bigclass` dataset. Each bar represents the mean Math score for that particular sex.

This visualization helps to quickly identify any potential differences in average Math performance between the sexes.
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/avg_math_by_sex_barchart.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Weight Distribution by Sex
This boxplot displays the distribution of weight for each sex in the `bigclass` dataset. Boxplots are effective for showing the median, quartiles, and potential outliers of a numerical distribution for different groups.

This plot allows for a visual comparison of weight characteristics between male and female students.
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/weight_boxplot_by_sex.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Height vs. Weight by Sex
This scatterplot visualizes the relationship between height and weight, with points colored according to the individual's sex in the `bigclass` dataset. Each point represents a student, showing their height on the x-axis and weight on the y-axis.

This plot allows us to observe trends and correlations between height and weight, and how these relationships might differ between sexes.
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/height_weight_scatterplot.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Xbar Chart: Part Resistance (Machine 1)
This Xbar chart monitors the `PartResistance` for `Machine 1` operating at `Temperature 303` and `Pressure 100`. The chart helps identify if the process is in statistical control by displaying individual observations relative to a center line (process mean) and control limits (Upper Control Limit - UCL, Lower Control Limit - LCL).

**Key Statistics for Part Resistance:**
- **Mean:** 6.6744
- **Median:** 6.6852
- **Standard Deviation:** 0.2525

Analyze the plot for any points outside the control limits or non-random patterns, which could indicate special cause variation.
:::

::: {.column width="50%"}
<iframe
  data-src='media/plots/xbar_partresistance_machine1.html'
  width='100%'
  height='500px'
  style='border:none;'
  scrolling="no">
</iframe>
:::
::::
