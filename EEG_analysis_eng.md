<style>
	.reveal {
		font-size: 1.75em
	}
</style>

Dissertation on the topic:

#### Investigation of the dynamics of psychophysiological states of the human brain, which identify its relaxation and concentration, using electroencephalograms.

Supervisor: Bilozorov V. E.

---

#### Research Objectives

1. Verification of data validity and real-time data processing, including consideration of scenarios involving partial data absence.
2. Development and implementation of methods for processing and filtering artifacts during EEG data collection using filters.
3. Utilization of nonlinear dynamics methods to analyze the behavior of chaotic time series of EEG data in cases of relaxation and concentration.
4. Development of a system capable of computing the level of brain relaxation and concentration based on EEG time series data.

---

#### Relevance of the Topic

In the modern world, there are available devices for obtaining EEG data in real-time mode, but there is a lack of developed and optimized approaches to analyze this data and implement corresponding algorithms. This raises questions for researchers and developers about how to effectively process EEG data depending on the specific task. One of the key areas of research in this context is the determination of psychophysiological states of the brain, particularly relaxation and concentration. Understanding and better utilization of these states are crucial for further development of EEG technology applications in medicine, psychology, sports, education, and other fields of human activity.

---

#### Biophysical model

![[Pasted image 20240402203352.png]]

---

![[EEG_10-10_system_with_additional_information.svg|1000]]

---

![[Pasted image 20240402204920.png|1000]]

---

#### Medical EEG reading device

![[Pasted image 20240402205938.png]]

---

#### EEG reading device - Muse 2

![[Pasted image 20240402210018.png|900]]

---

#### Mathematical models

- **Recurrent analysis** is a method of investigating dynamic systems based on studying their behavior over time through the iterative application of mathematical expressions. This analysis allows identifying the structure and properties of the system, including determining stability, endpoints, and chaos.
- **Frequency analysis** is a method of investigating signals and systems used to study their structure and properties in the frequency domain. This allows identifying the main components of the signal and their amplitudes. Frequency analysis helps in understanding the dynamics of signals, detecting patterns and dependencies between them, as well as in the development of signal filtering and processing methods for further use in various applications.

---

#### Recurrent diagrams

![[RQA_diagrams.png]]


---

#### Recurrent parameters

- Determinism (DET)

	$\displaystyle\text{DET} = \frac{\sum_{\ell=\ell_\min}^N \ell\, P(\ell)}{\sum_{\ell=1}^{N}\ell P(\ell)}$, where $P(\ell)$ - frequency distribution of the lengths $\ell$ of diagonal lines (i.e., it accounts for how many instances have length $\ell$).
- Average diagonal line length (L)

	$\displaystyle\text{L} = \frac{\sum_{\ell=\ell_\min}^N \ell\, P(\ell)}{\sum_{\ell=\ell_\min}^N P(\ell)}$
	
- Trapping time (TT)

	$\displaystyle\text{TT} = \frac{\sum_{v=v_\min}^{N} v P(v)} {\sum_{v=v_\min}^{N} P(v)}$,	where $P(v)$ - This is the frequency distribution of the lengths $v$ of vertical lines that have at least length $v_\min$. 

---

#### Frequency analysis and brain bands

![[Welch_demo.png]]

---

#### #### Fourier Transform

The Fourier transform of a function $f(t)$ is mathematically defined as the complex-valued function $ F(\omega) \,$, given by the integral:

$ \displaystyle F(\omega) = \int_{-\infty}^\infty f(t) e^{-i\omega t} dt  $

The **inverse Fourier transform** is defined by the expression:

$$ \displaystyle \dfrac{1}{2\pi}\int_{-\infty}^\infty F(\omega) e^{i\omega t} d\omega = f(t) $$

---

#### Brain bands

|Rhythm|Frequency Range (Hz)|Description|
|---|---|---|
|Delta|0.5 - 4|Deep sleep or unconsciousness|
|Theta|4 - 8|Relaxation, meditation, focus|
|Alpha|8 - 13|Calmness, relaxation with closed eyes|
|Beta|13 - 30|Alertness, concentration, high brain activity|
|Gamma|30 - 100|High concentration, cognitive processes, attention|

---
#### Frequency Noise

|Noise Type|Frequency Range (Hz)|Description|
|---|---|---|
|Low-Frequency Noise (LFN)|0.1 - 1|Noise with low frequency, may be associated with muscle movements or cardiac artifacts|
|High-Frequency Noise (HFN)|> 30|Noise with high frequency, may arise due to electrical activity of the skin or electromagnetic sources|
|Power Line Interference|50/60|Noise resulting from interference from the power grid|
|Motion Artifacts|Delta - Beta|Artifacts caused by patient movement|
|Biological Artifacts|-|Artifacts related to skin conductance, eye movements, or facial muscles|

---

#### Brain bands of several signals

![[Band_waves.png]]

---

#### Alpha channel, as a sign of relaxation with closed eyes

![[Alpha_power.png]]

---

#### Independent component analysis

![[ICA_demo.png]]

---

# Thank you for your attention!
