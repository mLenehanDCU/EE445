# Blood Pressure Measurement

- Heart consists of two pumps in series
 - smaller right hand pump forces blood through lungs
 - larger more powerful left hand pump force blood through rest of body

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Blood pressure values in various chambers of the heart and in peripheral
  vascular system heko ohysician determine functional integrity of
  cardiovascular system
- measurement of these values can be by direct (invasive) or indirect
  (non-invasive) techniques with different suitability is for particular
  clinical situations

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Heart sound and the correlated electrical and mechanical activity

- Diagram shows schematically:
 - Relationship between heart souds
 - Corresponding electrical activitY that generates muscular contractions
 - mechanical operation od valves
 - resultant blood pressure

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Direct measure of blood pressure - Invasive

- Require contact with blood vessels/heart, using catheter inserted into
  bloodstream
- Internral: micro-tipped manometer (pressure transducer)
 - Pressure strain-gauge on tip of catheter, inserted into circulatory system
   (intra-vascular)
 - smallest form factor and highest freq response for direct measurement but at
   higher cost

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Micro-electro-mechanical system (MEMS)
 - disposable

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- External: external pressure transducer (strain-gauge) on diaphragm with
  fluid-filled catheter to the source
 - Inexpensive and reusable (easy to sterilise)
 - an increaase in pressure at the tup of the catheter causes a flow of liquid
   through the catheter into the sensor, deflecting the catheter
 - Freq response affected by dynamics of fluid and diaphragm - need to be
   modelled
 -
 -
 -

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- External BP Sensor
 - Simplified lumped-parameter analogous circuit shown:
  - Catheter compliance much smaller than diaphragm - ignored
  - Sensor resistance and inertia much smaller than that in catheter - ignored
- Vsource = electrical analogue of pressure (mechanical potential) within blood
  vessel
-
-
-

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Using KVL:
 -
 -
-

- Freq response for catheter-sensor system with/out bubbles:

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Natural freq decreases from 91 to 22Hz and the damping ratio increases
-
-
-

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- System freq bandwifth should at least factor a x10 greater than the base freq
  of signal to give 10th harmonic of BP waveform
- Consider mean blood pressure only
 - Heart rate of 120 bpm = 2Hz so need fn > 20Hz
- For derivatives of blood pressure need greater bandwidth
- Differenctiation of sinusoidal harmonic increases amplitude by factor
  proportional to freq
- Can use Fourier Analysis to determine bandiwfth requirements buut as general
  rule amplitude-vs-freq characteristic of any catheter-manometer system used
  for measurement of ventricular pressures that are subsequently differentiated
  must remain flat to within 5%, up to 20th harmonic
- Important not to oversestimate pressure gradient across stentonic (narrowed)
  heart valve
 -
-

## Indirect measurement of blood pressure - Korotkoff method

- Non-invasive, but less accurate have lower freq response
- Korotkoff method
 - Uses sphygmomanometer - inflatable pressure cuff consisting of rubber bladder
   inside inelastic fabric covering that can be fastened around the upper arm +
   a hand pump with release valve + pressure gauge to measure pressure in the
   cuf
- Arterial blood can only flow past the inflated cuff when the arterial pressure
  exceeds the pressure of the cuff
-

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- When compressive pressure Pc applied to a limb, the pressure is transmitted to
  the underlying blood vessels so the pressure applied to the wall of the artery
  Pc, and the (transmural) pressyre differenec between inside of blood vessel
  and surouding tissue is lowered
- When applied presure equals arterial pressure, there is no radial stress in
  the arterial wall - vessel is said to be unlooaded
- If applied pressure further increased such that Pc>Pa', vessel will collapse
  and flow will be completely occluded
 - Cuff used to achieve this vascular unloading is called an occlusive cuff
- As pressure in cuff reduced from full occlusion, Korotkoff sounds heard
  through

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Korotkoff method of blood prerssure measurement:
 - Inflate pressure cuff on upper arm to a pressure well above the systolic
   pressure
  - blood flow stops and no sound can be heard through the stethoscope
- Slowly release pressure on the cuff
 - As soon as it falls below the systolic pressure the korotkoff souds begin to
   be heard
- As cuff pressure continues to drop Korotkoff sounds continue until cuff
  pressure no longer occludes the vessel during aany part of thhe cycle

## Indirect measures of blood pressure - Oscillometric method

- Volumetric change in blood content in the arm during cardiac cycle generats
  sensed pressure fluctuation in an inflated blood pressure cuff wraooed aroud
  the arm
- With cuff inflated above sysstolic pressure, fluctuations in cuff pressure are
  small
 - Also microphone placd at bend in arm (cubital fossa) will not pick up any
   sound because cuff pressure occludes blood flow
- As cuff pressure lowered, blood begins to flow through artery in spurts
 - turbulence souds will be picked up by microphone
 - amplified, rectified and averaged signal can be used to flag the systolic
   pressure
 - cuff-pressure  oscillations increase in strength in the systolc pressure
   region as cuff pressure  is lowered
- Fluctuations reach a max when the cuff pressure is the mean arterial pressure
  (MAP)
 - MAP = (systolic pressure + 2 * diastolic pressure)

- Pressure sensor needs full scale range of 0-300mmHg and to resolve
  fluctuations with amplitudes of a few mmHg, or about 1% of the FSR.
- Sensor will often be a diaphragm with resistors or strain-gauges arrangef in a
  bridge configuration
- Sensor output will
-

- Two--stage instrumentation amplifier with two-band outputs:
 - Low-pass filter to extract voltage signal corresponding to gross pressure
   change over time (baseline signal vb)
 - Bandpass filter to extract voltage signal corresponding to the (pressure
   oscillations/fluctuations) signal vf
- Both signals need to be digitized, and at same rate to correlate both
  measurements
- Upper limit on heart rate is 5Hz, so 100sps sampling rate should be
  sufficient, as should 8bits per sample, giving dyamic range of 256.
- Gain of low pass filter amp will need to be of order 10-20, while band pass
  filter amp should be in order 800-900 to fill the ADC range of a typical
  microcontroller

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Indirect measures of blood pressure - Doppler (ultrasoud) method

- Doppler technique
 - Piezoelectric crystal incorporated in cuff, emits vibration at usually
   ultrasoud freq. and picks up reflectedd vibrationss shifted in freq.
- Difference in freq (50-500Hz) proportional to velocity of wall motion and
  blood velocity
- While cuff
-
-

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Indirect measures of blood pressure - Other methods

- Blood Pressure Finger Gauge
 - Small pressure cuff in cavity can alternatiely be placed on a finger
 - Light beam obliquely incident on surface of finger opposite to nail is partly
   obsorbed and partly reflected
  - Reflectance is function of total blood content of the finger
 - By sensing reflectance, systolic and diastolic events can be identified and
   correlated with the cuff pressure

- Tonometry
 - Applying pressure needed to flatten curvature of the vessel
 - When circumferentiall stresses in vessel wall are removed, internal and
   external pressures are equal
 - Limitations:
  - Only measure specific peripheral pressures, such as brachial artery
  - is highly sensitive to positionand angle
  - requires calibration for precise measurement
 - Also has been successfully used for occular

## Pulse Transit Time

- Each heart beat generates a pressure wave that propogates along the arteries
- Key factor determining velocity of this pressure wave is the stiffness of the
  arterial walls:
 - Stiffer walls, faster wave propagates
- Walls of arteries are made stiffer by higher pressure blood within arteries
 -

- Commonly used markers on pulse wae at extemityy are 25% or 50% up the rising
  edge of the arrisving pulse wave
- If Pulse Transit Time can be correlated with blood pressure, then beat-by-beat
  (ie. continuous) blood pressure readings are possible
- Note that blood is not ejected from the heart at the peak of the QRS complex,
  actually short time later
- Pre-ejection lag period is neither a constant nnor uniquely correlated with
  blood pressure and presents a confounding factor for estimating blood pressure
  from PTT
- To eliminate pre-ejection period frm calculated PTT, second photoplethysmo...
-

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- Let:
 - T
 -
 -

- Many physical factors influence cardiac output and blood pressure, such as
  blood volume, resistance of blood vessels, and blood thickness
- In practice, each individuals autonomic nervous system responds to and
  regulates all interacting factors.
- When blood pressure decreases, nervous sysstem responsds to increase HR to
  increase cardiac output and arterial walls contract to increase blood pressure
- Blood pressure related to both HR and prevvious blood pressure
- Blood pressure may thus be estimated as:
 - $$
-

- Recent study showed more accurate low-freq tracking when photopplethysmogram
  (PPG) pulse intensity ratio (PIR) is measured
- Diagram shows PPT calculated via peak of first derivative of PPG waveform, and
  PIR is ratio of PPG peak intensity In to PPG vally intensity Il of one cardiac
  cycle
- PIR reflects arterial diameter change \delta d during one cardiac cycle frm
  systole to diastole:
 - $PIR = $
 - where \alpha is a constant related to optical absorption coefficients in the
   PPG light path

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}


