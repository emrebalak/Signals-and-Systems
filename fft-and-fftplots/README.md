# FFT Calculations and Plots of 2 Different Speeches

You can find two folders containing the audio files of two prestigious historians of Turkish academic community: İlber Ortaylı and Emrah Safa Gürkan(Just few of them added). Each audio file has the same length of nearly 5 seconds (22501 data samples).

I have written a script that calculates fft for these audio files and plots the fft magnitude. Only one of the sound channels is used to make np.fft.fft function work properly, then normalized the signal by dividing it by max(abs(signal)).
