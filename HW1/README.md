## MIR - HW #1
Audio Signal Processing & Musical Key Detection
# Question 1.
a. 

<img width="416" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/c85f6a22-b18f-4b0c-ae27-e90a0513c283">
 
This song  is fetched from the theme song of LaLa Land, and it’s 36 seconds long. I find a piano cover, so it should be easier to read off the spectrogram. In this recording, we can clearly see the f0 in light blue line and is playing off the left hand part on the music sheet. However, by listening to the song, we can notice that G3 (196.00 Hz) is detected as G2 (98.00 Hz). As right hand joins around 11s, lower frequency is recognized (around C2).
By simply reading the strong note (highlighted in yellow), we can see the melody of both left and right hands. For example, in bar 6 (around 14s), the note is at E5 (659.25 Hz) and F5 (698.46 Hz).

b. 

c. For x1, the sound is increasing throughout the first 6.5 seconds, and decreasing afterward. As for x2, the sound is like oscillating, increasing and decreasing, and is more observable in the end.
d. Here are the two spectrograms for x1 and x2. The first spectrogram does look like how the audio sound to me, but it didn’t match the idea of keep increasing like a bird’s chirp. The second spectrogram look like how it sound to me. The frequency oscillates throughout that 10 seconds.
<img width="204" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/bf1b8e3f-25c3-4668-b6e7-914e44f0af64">
<img width="205" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/b12dac4c-e2b0-4794-b48d-5b663c1a5c52">

# Question 2.
a. For Global Key detection, I used K-S detection with late fusion. And here is the result I got after the prediction.
<img width="403" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/63c915a0-c883-4e0d-8f40-95a3d9825a55">
<img width="403" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/6defd00e-f4b3-425b-aaa9-97a0d7188ac1">

|          |   stft   |    cqt   |   cens   |
| -------- | -------- | -------- | -------- |
| RA score |  0.6250  |  0.5833  |  0.5417  |
| WA score |  0.6875  |  0.6958  |  0.6458  |

It looks like stft have the best result in general, it has the average of 0.656. The CQT and cens method are interesting, it is likely to detect a chord as something else (relative/perfect-fifth/parallel), and this is why they have a large difference between RA scores and WA scores.

b. For local key detection, I also used the same approach. But for the frames extraction, I use the method as described in the questions with 15 seconds before the detected time and 15 seconds after it, which is 30 seconds in total. 
 
I found that length of y is multiple of sampling rate and the music length. So I cut the y to a smaller duration (30 seconds) tmp_y.

And for the RA and WA score, I decided to check my estimations one by one with the ground truth file. For example, if the estimation at 10th second is within that (start ~ end) range in the csv file, then I check the estimation correspondingly.
<img width="416" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/65cfc9a3-bbcf-42aa-a016-2e27d3850ad4">

By doing so, I can get the index of the correct frame on the csv file.
|          |   stft   |    cqt   |   cens   |
| -------- | -------- | -------- | -------- |
| RA score |  0.4263  |  0.4940  |  0.4741  |
| WA score |  0.5191  |  0.6080  |  0.5880  |

It is interesting that stft performs the best in global key detection while cqt and cens perform better in local key detection. I think they are predicting more accurately on the music with shorter duration.

c. I assume that the small segments with the same chord should be in a same segment, so I combine them into a big one and extract the start and end time.

<img width="204" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/1812e8f4-b725-4b74-869c-a800e36b8239">
<img width="204" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/89966873-de3d-48b8-afe5-3d6710a3033e">
<img width="416" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/e715c163-b7d1-4e2b-b745-6e9d2197f4e4">

It looks like the segmentations I made were not precise, however, over-segmentation still has a satisfying performance overall.
