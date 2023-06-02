# MIR Homework 3 Report

Question 1.

Fourier Tempogram

<img width="219" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/f52fcb9f-b9ea-42de-82e2-ad0f651717f2">

Autocorrelation Tempogram

<img width="219" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/d2c0b0f4-09b0-4897-9ae3-39983b686076">

The results obtained by using the autocorrelation tempogram shows a significant improvement from fourier tempogram. Especially on the genre ‘Rumba’, ‘Samba’, both musica often have complex rhythmic patterns with multiple layers of percussion instruments. The autocorrelation method may be better suited for capturing the intricate rhythmic structures and detecting the periodicities within the music, leading to higher accuracy in tempo estimation.

And ChaCha also shows a notable improvement, in my opinion, the ChaCha rhythm may have strong periodic patterns that are better captured by the autocorrelation method. Autocorrelation is particularly effective for detecting repetitive patterns in music, which could explain the higher accuracy in tempo estimation for this genre.

Question 2. 
4 seconds fourier

<img width="186" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/52bfa0e4-8912-4fa7-8ea9-62a6745c022a">

4 seconds autocorrelation

<img width="191" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/695a3aae-b069-4696-a996-ca76e0080677">

8 seconds fourier

<img width="189" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/1c1bac3f-a263-40ca-a975-ca2cbcaf2ec0">

8 seconds autocorrelation

<img width="191" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/a083407a-b601-4ad4-a371-fb50e4c3813b">

12 seconds fourier

<img width="189" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/1d37719a-6c73-4208-858d-85f5ee3c4fdb">

12 seconds autocorrelation

<img width="186" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/c649c357-1d35-4623-bc58-9777484cd8af">

It is interesting that Walts seem to have better performance when the window size is larger, while QuickStep seem to have better performance when the window size is small. So I think the slower songs will be better detected by using larger window size. 

Question 3. 

<img width="248" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/3e097daf-50f2-4237-907a-bd624392915b">

The proposed method computes the tempogram by element-wise multiplication of the Fourier tempogram and the transformed autocorrelation tempogram. The scales of the autocorrelation tempogram are pooled to match the frequency bins of the Fourier tempogram. The maximum values of the pooled autocorrelation tempogram within each bin are extracted and combined with the Fourier tempogram.

From the result, we can see that the badly performed genre back in question 1 & 2 are improved, and now have the similar or better performance like the result from another type of tempogram. For example, Samba has 0.11 from fourier tempogram and 0.37 from autocorrelation tempogram, now it has 0.36.

Question 4.

<img width="278" alt="image" src="https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/b6a4821f-15fb-47a8-bd9f-b8385ade2add">
 
I think the result is affected by the music style, for example, ChaCha’s beats are super easy to follow while Walts usually emphasize on the first beat of a bar which leads to unclear down beat. 

![image](https://github.com/EvelynHung-79/Music_Information_Rechieval/assets/57160523/685ba049-a988-4af5-945a-71e3e2af4885)
