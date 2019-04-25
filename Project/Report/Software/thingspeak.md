## ThingSpeak Integration

ThingSpeak integration is performed using the ThingSpeakClient.ino code example
found in the Energia git repository\cite{thingino}. This example works much in
the same way as the Energia WifiWebClient example code, however, it has code
included to update ThingSpeak input fields, in the required format.

In order to correctly utilize this code, the ThingSpeak write API key must be
included in the code, as a String value. An update interval value is used in
order to set how often data is sent to ThingSpeak from the client. For this
implementation, this has been set to 20ms, as this was the lowest accepted
value.

\lstset{
    caption=ThingSpeakClient.ino write API key and update interval,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
String writeAPIkey = ""; //Enter channel's write API key
			 			//between the ""
const int updateThingSpeakInterval = 20; //20ms time interval
\end{lstlisting}

The startWifi() method is called from within the codes setup, and connects to
the network of the input ssid and password, printing a success message to the
serial monitor once connected.


\lstset{
    caption=ThingSpeakClient.ino startWifi(),
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
char ssid[] = ""; // your network SSID (name)
char pass[] = ""; // your network password
WiFiClient client;
void startWiFi(){
    WiFi.disconnect();
    client.stop();
    ...
    if(WiFi.begin(ssid, pass) == 0){
	...
    } else {
	Serial.println("LaunchPad connected to network using DHCP");
	...
    }
}
\end{lstlisting}
