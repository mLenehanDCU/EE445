## MATLAB Script

The MATLAB script used for data visualisation within ThingSpeak is required to
read in data from two strings, convert them from the "table" format in which they
are sent from the client device, and split the string by whitespace, and plot
the data from the time string against the ECG data string.

\lstset{
    caption=ThingSpeak MATLAB Code,
    basicstyle=\footnotesize, frame=tb,
    xleftmargin=.1\textwidth, xrightmargin=.1\textwidth
}
\begin{lstlisting}[language=C]
readChannelID = 767748;
fieldID1 = 1;
fieldID2 = 2;
readAPIKey = ''; %Enter Read API Key between ''

[data, dataTime time] = thingSpeakRead(readChannelID, 'Field', fieldID1,
'Field', fieldID2, 'NumPoints', 1, 'ReadKey', readAPIKey, 'OutputFormat',
'table')

%% Data must be modified to a matrix of integer values.
%% This requires the data to be made into a table using:

dataTable = table(data.ECGData);
dataTimeTable = table(data.ECGTimes);

%% Table must be converted to array

dataArray = table2array(dataTable);
dataTimeArray = table2array(dataTimeTable);

%% Cell Array must be converted to matrix

dataMat = cell2mat(dataArray);
dataTimeMat = cell2mat(dataTimeArray);

%% Each Value of the String must be split by a whitespace delimiter

dataSplit = strsplit(dataMat(1,1:end));
dataTimeSplit = strsplit(dataTimeMat(1,1:end));

%% Split Cells must be converted to matrix

dataSplitMat = [dataSplit(:)];
dataTimeSplitMat = [dataTimeSplit(:)];

%% Convert String values to Double

dataFinalMat = cellfun(@str2double, dataSplitMat);
dataTimeFinalMat = cellfun(@str2double, dataTimeSplitMat);

%% Plot Time values versus Data values

plot(dataTimeFinalMat, dataFinalMat);
\end{lstlisting}

In order to acquire data from another groups channel, for comparison, the
channel ID and read API key would be required. The comparison could be made by
taking the difference of both "dataFinalMat" variables, assuming each group has
uploaded their value in the same manner. Unfortunately, this implementation was
not completed.
