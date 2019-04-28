## Components

The three op-amp connection circuit is known as the instrumentation amplifier.
It is one of  the key parts of the bio-amplifier where the major signal
amplification and cancelling out of noise takes place. The input stage of the
instrumentation amplifier has a very high input impedance and low common mode
gain and hence it can reject all the common mode voltages or noises\cite{BioAmp}.
The gain stage of the amplifier produces the differential gain to the signal
and also has a low input impedance and hence for the overall amplifier system it
amplifies only the differential component and has a very high common mode
rejection ration and for rejection of the common mode voltages we use the driven
right leg circuit as illustrated below. The common mode signal is given as a
reference.

\begin{figure}[H]
\includegraphics{Images/Hardware/DrivenRightLeg.png}
\centering
\caption{Driven Right Leg Circuit for Common Mode Rejection \cite{tweed}}
\label{drivenright}
\end{figure}


As the instrumentation amplifier we use the IC AD620, which is a low cost,
highly accurate instrumentation amplifier that can set a gain of 1 to 10,000.
It has 8 lead SOIC and DIP packing. The diagram and pinout of AD620 is given below.

\begin{figure}[H]
\includegraphics{Images/Hardware/InstrumentationAmplifier.png}
\centering
\caption{AD620 Instrumentation Amplifier Pinout\cite{analog}}
\label{ad620}
\end{figure}

### Operational/Isolation Amplifier

These are also known as the pre-amplification circuits. The main purpose of the
isolation amplifier is to provide electrical insulation to the patient and also
prevents internal cardiac shock, and it increases the input impedance of the
patient monitoring system.

### Band Pass Filter

As for designing the high pass filter a resistance of $22k\Omega$ and a
capacitor of $1\mu F$is used. The high pass filter is used to attenuate a
signal below a certain frequency range.

\begin{figure}[H]
\includegraphics{Images/Hardware/CircuitPhoto.jpg}
\centering
\caption{An Image of the Completed Circuit}
\label{circuitphoto}
\end{figure}
