## ThingSpeak Integration

ThingSpeak integration is performed using the ThingSpeakClient.ino code example
found in the Energia git repository\cite{thingino}. This example works much in
the same way as the Energia WifiWebClient example code, however, it has code
included to update ThingSpeak input fields, in the required format.

In order to correctly utilize this code, the ThingSpeak write API key must be
included in the code, as a String value. An update interval value is used in
order to set how often data is sent to ThingSpeak from the client. For this
implementation, this has been set to 15 seconds, as this was the lowest accepted
value.

\lstset{
    caption=ThingSpeakClient.ino write API key and update interval,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
String writeAPIkey = ""; //Enter channel's write API key
			 			//between the ""
const int updateThingSpeakInterval = 15*1000; //20ms time interval
\end{lstlisting}

The startWiFi() method is called from within the codes setup, and connects to
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

Within the loop function, an if statement checks for connection to the client,
and reads any incoming response. If no client is connected, a disconnection
notification is printed to the serial monitor.

Another if statement checks if the update interval has been exceeded, and, if
so, writes data via HTTP POST message to ThingSpeak, using the
updateThingSpeak() method.


\lstset{
    caption=ThingSpeakClient.ino Loop Function,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
long lastConnectionTime = 0;
boolean lastConnected = false;
void loopThingSpeakClient(){
    if(client.available()){
	char c = client.read();
	Serial.println(c);
    }
    if(!client.connected() && lastConnected){
	Serial.println("...disconnected");
	...
	client.stop();
    }
    if(!client.connected() && (millis() - lastConnectionTime >
	updateThingSpeakInterval)) {
	String updateVal = "field1="+reading+",field2="+readtime;
	updateThingSpeak(updateVal);
    }
    ...
    lastConnected = client.connected();
}
\end{lstlisting}

The updateThingSpeak() method ensures that the device is correctly connected to
the website, and transmits the ECG readings via HTTP POST message. If the
transfer fails, the client disconnects.

\lstset{
    caption=ThingSpeakClient.ino updateThingSpeak Function,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
void updateThingSpeak(String tsData){
    if(clinet.connect(thingSpeakAddress, 80)){
	...
	client.print("POST /update HTTP/1.1\n");
	client.print("Host: api.thingspeak.com\n");
	client.print("Connection: close\n");
	client.print("X-THINGSPEAKAPIKEY: " + writeAPIkey + "\n");
	client.print("Content-Type: application/x-www-form-urlencoded\n");
	client.print("Content-Length: ");
	client.print(tsData.length());
	client.print("\n\n");
	client.print(tsData);
	...
	failedCounter = 0;
    } else {
	failedCounter++;
	client.stop();
	...
    }
    lastConnectionTime = millis();
}
\end{lstlisting}
