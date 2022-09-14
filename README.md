
# Chord Detection via Fourier Analysis

This project explores the applications of Fourier analysis and some concepts of digital sound processing.

## Introduction

This project originally used a CNN trained using tensorflow on a dataset of thousands of images of spectrograms for multiple musical chords. However, it was found that collecting large amounts of data and training a neural network is quite a tedious approach to this task. Instead, Fourier analysis can be used on the audio itself.
##   Explanation

Using ``matplotlib`` and ``scipy`` we can import and show exactly what the audio file of a note or a chord looks like as a function of time.
using this graph we can cut the audio file down for processing (I used 8 seconds). ``Note: I am using WAV files``

Next we can use the ``Fast Fourier Transform (FFT)`` algorithm built in to scipy with numpy on the graph of the audio and it returns a new graph
which is the Fourier Transform of the previous graph. To put it simply, the Fourier Transform converts the graph from a function of time to a function of frequency
where the peaks represent the detected sounds. Now we can simply just find the location of the peaks on the x axis and that will give us the frequency of the sound.

Now we can create a ``lookup table of notes and their respective frequencies`` and match the values.
We will have to do a little bit of post processing on the frequencies of the peaks in order to generate accurate results.



![App Screenshot](https://media.discordapp.net/attachments/947249030306607114/947277548818153553/unknown.png?width=1336&height=671)



## Look up table

You might be wondering where I got this lookup table from.
The basic concept of how this is works is that each pitch has a corresponding frequency  and a scientist somewhere  determined that the fixed ratio of a semitone is equal to around 1.059 or 2^(1/12) and since the concert pitch for A4 is set to 440Hz we can derive the following table


![App Screenshot](https://cdn.discordapp.com/attachments/351867028589510656/947667776384929903/unknown.png)


## Conclusion
After using the look up table we can get the top 3 most frequent frequencies and those three notes would be the notes in a chord, With this we could also make another table of chords with their respective notes and do the same process we did with the notes and frequencies to get the chords.

Below we are using a G4 Chord on a piano (G, B, D) and the output is displaying the most matched frequencies
![App Screenshot](https://cdn.discordapp.com/attachments/351867028589510656/947740942662791218/be5f64476ebb4accba7c96bf001c92dd.gif)

## Other info

In the future we can use this tech to make something similar to apps like yousician, We can also use pre processing algorithms to get even more accurate results but for now what we have will work for almost any instruments.

## Acknowledgements

 - [Applications of Fourier Analysis to Audio Signal Processing: An Investigation of Chord Detection Algorithms](https://scholarship.claremont.edu/cgi/viewcontent.cgi?referer=&httpsredir=1&article=1575&context=cmc_theses)
 - [Scipy FFT explanation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.fft.fft.html)
 - [3Blue1Brown Explanation of Fourier Transform](https://www.youtube.com/watch?v=spUNpyF58BY)

## Authors

- [@SippinOnJuiceBox](https://github.com/SippinOnJuiceBox)

