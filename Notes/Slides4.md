# Biopotential Electrodes

## Introduction

- Electrode
 - A conductor in electrical contact with biological tissue or chemical
   solution (electrolyte)
- Skin, other body tissue act as electrolytic solutions
- Want to measure voltages (biopotentials)
 - To do this need to conduct currents
- Function of biopotential electrodes:
 - Provide interface between electrical signals of the body and electronic
   instrumentation system
 - i.e. to act as transducers from ionic currents in the body to electrical
   current in the external system
- Choice of electrodes is important for the recording of bioelectronic signals:
 - Should be comfortable for the patient
 - convenient to apply
 - not produce any artifacts
 - None completely achieveable, some compormise in each

## Redox Reaction (an electrochemical reaction)

- Oxidation Reaction: Metal loses electrons and ion goes into solution
 - Called the Anode: $Fe -> Fe^{2+} + 2e^{-}$
- Reduction Reaction: Hydrogen/Hydroxyl ions in solution gain electrons
 - Called the Cathode: $2H^{+} + 2e^{-} -> H_2$
- These reactions need to occur in pairs
 - Rate of reaction = Rate of oxidation
 - Unless current flows from electrode to electrolyte or vice versa
- Assuming Fe is surrounded by weak acid in which H+ ions are abundant
 - Acid called electrolyte
 - Provides home for dissolved $Fe^{2+}$
- Has to be internal movement of electrons through metal
 - Corrosion current

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Half-Cell Potential

- When metal place in electrolyte solution
 - Metal slightly dissolves into solution (same process as corrosion)
 - Accompanied by loss of electrons to atoms that remain with parent metal
 - Leaving parent metal with net negative charge (excess of electrons)
 - And dissolved metal ions with a positive charge
- Resultant electric field draws dissolved positive metal ions back to vicinity
  of metal surface
- Without energy required for recombination ions held close to metal surface
- Form region called electrode double layer, and potential called Half-Cell
  Potential
 - Voltage value depends on
  - metal present
  - electrolyte composition
  - temperature
  - Note: potential varies across electrolyte

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

- To avoid problem of not being able to directly measure an individual half-cell
  potential electrochemists adopt convention that H electrode has half-cell
  potential of 0, others measured relative to this
- Values are for 0 current flowing between cell and electrolyte

\begin{figure}[H]
\includegraphics{}
\centering
\caption{}
\label{}
\end{figure}

## Polarisation

If current is flowing between electrode and electrolyte
 - Three factors - 'polarisaion of electrode' - can affect observed half-cell
   potential
- Difference between observed half-cell potential with current and equilibrium 0
  current half-cell potential known as overpotential
- Polarisation potential $V_P$ of electrode given by: $V_p=E^0+V_r+V_c+V_a$
 - $E^0$ is half-cell potential of electrode
 - $V_r$ is Ohmic overpotential
  - voltage drops due to finite resistivity of electrolyte
  - Non-linear with current
  - More relevant in low concentration electrolytes
 - $V_c$ is Concentration overpotential
  - from changes in distribution of ions near electrode-electrolyte interface
    when current is flowing
  - Oxifation-reduction reaction rates at interface change, altering equilibrium
    concentration of ions
 - $V_a$ is Activation overpotential
  - Due to activation barrier for oxidation or reduction of ions, and will
    depend on direction of current
- Polarizable Electrodes
 - If activation overpotential $v_a$ is very large, no charge can flow
  - No conduction current, which is good for high impedance measurements
  - Electrode behaves like a capacitor
  - Only displacement current flows
- Non-polarizable Electroded
 - If activation overpotential $V_a$ is very small and independant of the
   direction of current
 - Good for both voltage and current measurements and preferred for bio
   insrumentation
 - Electrode behaved like resistor
 - Conduction current flows across interface
- In practice, both mechanisms occur to some extent and the interface impedance
  has components of resistance and capacitance
- Silver/silver chloride electrode:
 - Deposition of (non-soluble) AgCl on Ag makes good non-polarizable electrode
   for any biological tissue or biological tissue or biological electrolyte
   which generally has excess of chlorine ions
- Silver base with attached insulated lead wire is coated with layer of AgCl
 - Only slightly soluble in water
 - Electrode immersed in electrolyte bath in which principal anion of
   electrolyte is $CL^{-}$
-
