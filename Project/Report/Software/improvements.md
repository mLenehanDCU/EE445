## Possible Improvements

Due to the limitations imposed by ThingSpeak, the maximum available sampling
rate, when uploading one data sample at a time is 1 sample every 15 seconds.
However, the implementation used, uploading bulk data via a single string causes
a number of functions to be performed on the data structure, in order for it to
be in a usable format for plotting and comparison. An alternative approach would
involve using the JSON message format to send bulk data, along with the
timestamp of each data point\cite{matlabbulk}. Using this, a more simple plot function could be
performed from within the MATLAB code, as only one field within the channel
would be used, with the appropriate data points and timestamps contained within
it.
