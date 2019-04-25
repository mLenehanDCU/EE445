## ECG Sampling

The ECG sampling code implementaion, as used within this project, was performed
at a frequecny of 50Hz (one sample every 20ms). This frequency was chosen in
part due to limitations imposed by ThingSpeak, which could not allow for a
higher frequency to be chosen for single data entries.

In order to take measurements from the bioamplifier circuit, an input pin must
first be defined. An integer variable must be defined in order to store the
measured value.

\lstset{
    caption=Analog Input Pin Definition,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.2\textwidth, xrightmargin=.2\textwidth
}
\begin{lstlisting}[language=C]
int AnalogPin = A6; //P4.7
int reading = 0;
\end{lstlisting}

In order to take the reading, the analogRead() method must be called. This
method allows the MSP to read in analog values from 0 to 5V, assigning them a
value between 0 and 1023. An if statement is used to ensure that the readings
are taken at the appropriate timing.

\lstset{
    caption=Analog Read,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
if(millis() - lastReadingTime > updateThingSpeakInterval){
    reading = analogRead(AnalogPin);
}
\end{lstlisting}

