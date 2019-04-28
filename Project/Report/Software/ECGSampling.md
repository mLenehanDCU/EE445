## ECG Sampling

The ECG sampling code implementation, as used within this project, was performed
at a frequency of 50Hz (one sample every 20ms). This frequency was chosen as it
allows for the detection of all ECG components\cite{biopacl5}. However, due to limitations
imposed by ThingSpeak, which could not allow for a frequency greater than one
sample every 15 seconds to be chosen for single data entries. As such multiple
data points must be transmit at once.

In order to take measurements from the bioamplifier circuit, an input pin must
first be defined. An String variable must be defined in order to store the
measured value, along with String to store the reading times. The sampling
frequency time is stored as a constant integer value.

\lstset{
    caption=Analog Input Pin Definition,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.2\textwidth, xrightmargin=.2\textwidth
}
\begin{lstlisting}[language=C]
int AnalogPin = A6; //P4.7
String reading;
String readtime;
int index = 0;
const int updateReading = 20;
\end{lstlisting}

In order to take the reading, the analogRead() method must be called. This
method allows the MSP to read in analog values from 0 to 5V, assigning them a
value between 0 and 1023. An if statement is used to ensure that the readings
are taken at the appropriate timing. The time of each reading is stored, along
with the time the reading is taken. The index is incremented on each reading. As
750 readings may be taken at 20ms intervals over a period of 15 seconds, the
index will be reset after the 749th reading.

\lstset{
    caption=Analog Read,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
if(millis() - lastReadingTime > updateReading){
    reading = reading+String(analogRead(AnalogPin))+" ";
    readtime = readtime+String(millis())+" ";
    ...
    lastReadingTime = millis();
    if(index<749){index = index+1;}
    else {
	index=0;
	reading="";
	readtime="";
	}
}
\end{lstlisting}
