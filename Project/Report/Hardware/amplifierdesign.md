## Amplifier Design

The key function of a biopotential amplifier is the amplify the weak electrical
signals that has  biological origin. Biological signals are received as
potentials, or voltage changes and also as the electrical field strengths
produced by the muscles or nerves. The output signals from these amplifiers
will be of the range $1$ to $100mV$ accompanied with extremely high-level
interference signals and noise and large source impedance. The signal received
from the biological origin is to be amplified and then converted to digital
signal for performing computer manipulations. This amplifier has to provide
selective amplification to the biological signal while detecting and cancelling
all other interference noises and signals and on the other hand should provide
electrical insulation to the subject as well\cite{BioAmp}. Figure
\ref{bioBlock} represents basic model of a bio potential amplifier. It consists
of the following parts:

\begin{enumerate}
\item Preamplifier or the instrumentation amplifier.
\item High pass filters
\item Isolation Amplifier
\item Low-pass filters
\end{enumerate}

\begin{figure}[H]
\includegraphics{Images/Hardware/BioamplifierBlockDiagram.png}
\centering
\caption{Bioamplifier Block Diagram}
\label{bioBlock}
\end{figure}

There are some basic requirements that is to be fulfilled while modelling and
using a biopotential amplifier.
\begin{itemize}
\item The signal received should not have any distortion in it.
\item The signal should achieve best separation between the signal, noise and
interference.
\item The amplifier should provide electrical insulation to the patient
\item The amplifier should also protect itself from the high input voltages from
the defibrillators or electrosurgical instrumentation.
\end{itemize}

\begin{figure}[H]
\includegraphics{Images/Hardware/CircuitDiagram.png}
\centering
\caption{Complete Circuit Diagram}
\label{circuitdiagram}
\end{figure}

