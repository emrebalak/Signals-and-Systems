# Audio Visualization with Discrete Fourier Transform

In this part, DFT is used for audio visualization. Steps are given below for a basic audio visualizer:

* Select the visualization renewal rate (e.g. 10 FPS). Since you know the sample rate in Hertz (44100 in the given file.), you can select data from the audio array which is matching with renewal time. For example, to visualize at 10 FPS, each visualization interval comes from 4410 values in sampled audio matrix. Pad the audio matrix with zeroes if necessary.

* For each visualization interval;
  - Find FFT of that interval using built-in functions. Since it’s in exponential form, it will give an array of complex numbers. Find the magnitude of each
value.
  - The transformed values have a great range because of the outliers. For a better representation, logarithm operation 10 ∗ log10(xft + c) is used for each value. Here c can be a small number to avoid log10(0).
  - Since the obtained transformation is mirrored (see conjugate symmetry property) you may use:
    * The first half of the array
    * Shifted version of the array using fftshift function
* After obtaining transforms for all visualization intervals, you can plot the transforms using matplotlib’s “bar” function and write the results to a video file.

* To write the audio on the video, you can benefit from moviepy library.

**Note:** To speed-up the figure rendering, you can use ’plot’ function instead of bar
function. However, do not forget to limit the y-axis with constant values.

**I have read left stereo of SilentKnight.wav file by the help of read function of scipy.io.wavfile library. The song was 82,2 seconds, so I have rounded it to 83 and padded the audio array with zeros. I have created 2 dimensional array for visualization(83 x 4410). Selected FPS is 10 and each second contains 10 elements. I calculated plots for every seconds. Necessary comments are added on the code file for this part.**
