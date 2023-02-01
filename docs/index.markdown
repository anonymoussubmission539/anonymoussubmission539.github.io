<!-- ---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
--- -->

<!-- <audio src="midi_4_4_4_4.mp3" controls autoplay loop></audio> -->

# Abstract

Deep learning techniques have successfully been used to generate music in a wide variety of musical styles and forms. However, the inner workings of most generative music models are not understandable to people. One approach to making more understandable generative models of music is to employ latent space regularisation in a Variational Auto-Encoder (VAE). A key example of this approach is MeasureVAE which has been demonstrated using an Irish folk melody dataset. This paper examines how MeasureVAE performs with different latent vector sizes, different numbers of regularised dimensions, and on a wider range of training datasets and genres including classical, pop, rock, jazz, R\&B, and folk music. Results indicate that MeasureVAE is able to generate music in these genres and that 32 and 64 dimension latent vector models are optimal as they generate lower loss, and have higher accuracy and interpretability scores than 4, 8, 16, 128, and 256 dimensions.

# Measure VAE Architecture and the Latent Regularisation Loss

# Muse Dataset (Classical, Bach)

<!-- <audio ref='themeSong' src="/midi_4_4_4_4.mp3"></audio> -->

<!-- <audio ><source src='midi_4_4_4_4.mp3' type='audio/mpeg'></audio> -->

L = Low, H = High

| RC    | AIJ   | ND    | NR    | Audio                                                                        | Pianoroll                                                               |
|-------|-------|-------|-------|------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| L     | L     | L     | L     | <audio src="/Bach/MP3s/midi_4_4_4_4.mp3" controls autoplay loop></audio>     | <img src = "/Bach/Piano_rolls/midi_4_4_4_4.png" alt = "Piano Roll">     |
| L     | L     | L     | **H** | <audio src="/Bach/MP3s/midi_4_4_4_10.mp3" controls autoplay loop></audio>    | <img src = "/Bach/Piano_rolls/midi_4_4_4_10.png" alt = "Piano Roll">    |
| L     | L     | **H** | L     | <audio src="/Bach/MP3s/midi_4_4_10_4.mp3" controls autoplay loop></audio>    | <img src = "/Bach/Piano_rolls/midi_4_4_10_4.png" alt = "Piano Roll">    |
| L     | **H** | L     | L     | <audio src="/Bach/MP3s/midi_4_10_4_4.mp3" controls autoplay loop></audio>    | <img src = "/Bach/Piano_rolls/midi_4_10_4_4.png" alt = "Piano Roll">    |
| **H** | L     | L     | L     | <audio src="/Bach/MP3s/midi_10_4_4_4.mp3" controls autoplay loop></audio>    | <img src = "/Bach/Piano_rolls/midi_10_4_4_4.png" alt = "Piano Roll">    |
| L     | L     | **H** | **H** | <audio src="/Bach/MP3s/midi_4_4_10_10.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_4_4_10_10.png" alt = "Piano Roll">   |
| L     | **H** | **H** | L     | <audio src="/Bach/MP3s/midi_4_10_10_4.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_4_10_10_4.png" alt = "Piano Roll">   |
| **H** | **H** | L     | L     | <audio src="/Bach/MP3s/midi_10_10_4_4.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_10_10_4_4.png" alt = "Piano Roll">   |
| L     | **H** | L     | **H** | <audio src="/Bach/MP3s/midi_4_10_4_10.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_4_10_4_10.png" alt = "Piano Roll">   |
| **H** | L     | **H** | L     | <audio src="/Bach/MP3s/midi_10_4_10_4.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_10_4_10_4.png" alt = "Piano Roll">   |
| **H** | L     | L     | **H** | <audio src="/Bach/MP3s/midi_10_4_4_10.mp3" controls autoplay loop></audio>   | <img src = "/Bach/Piano_rolls/midi_10_4_4_10.png" alt = "Piano Roll">   |
| L     | **H** | **H** | **H** | <audio src="/Bach/MP3s/midi_4_10_10_10.mp3" controls autoplay loop></audio>  | <img src = "/Bach/Piano_rolls/midi_4_10_10_10.png" alt = "Piano Roll">  |
| **H** | **H** | **H** | L     | <audio src="/Bach/MP3s/midi_10_10_10_4.mp3" controls autoplay loop></audio>  | <img src = "/Bach/Piano_rolls/midi_10_10_10_4.png" alt = "Piano Roll">  |
| **H** | **H** | L     | **H** | <audio src="/Bach/MP3s/midi_10_10_4_10.mp3" controls autoplay loop></audio>  | <img src = "/Bach/Piano_rolls/midi_10_10_4_10.png" alt = "Piano Roll">  |
| **H** | L     | **H** | **H** | <audio src="/Bach/MP3s/midi_10_4_10_10.mp3" controls autoplay loop></audio>  | <img src = "/Bach/Piano_rolls/midi_10_4_10_10.png" alt = "Piano Roll">  |
| **H** | **H** | **H** | **H** | <audio src="/Bach/MP3s/midi_10_10_10_10.mp3" controls autoplay loop></audio> | <img src = "/Bach/Piano_rolls/midi_10_10_10_10.png" alt = "Piano Roll"> |


# Lakh Dataset (Jazz and Popular music)

L = Low, H = High

| RC    | AIJ   | ND    | NR    | Audio                                                                    | Pianoroll                                                           |
|-------|-------|-------|-------|--------------------------------------------------------------------------|---------------------------------------------------------------------|
| L     | L     | L     | L     | <audio src="/Lakh/MP3s/midi_4_4_4_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_4_4_4.png" alt = "Piano Roll"> |
| L     | L     | L     | **H** | <audio src="/Lakh/MP3s/midi_4_4_4_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_4_4_9.png" alt = "Piano Roll"> |
| L     | L     | **H** | L     | <audio src="/Lakh/MP3s/midi_4_4_9_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_4_9_4.png" alt = "Piano Roll"> |
| L     | **H** | L     | L     | <audio src="/Lakh/MP3s/midi_4_9_4_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_9_4_4.png" alt = "Piano Roll"> |
| **H** | L     | L     | L     | <audio src="/Lakh/MP3s/midi_9_4_4_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_4_4_4.png" alt = "Piano Roll"> |
| L     | L     | **H** | **H** | <audio src="/Lakh/MP3s/midi_4_4_9_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_4_9_9.png" alt = "Piano Roll"> |
| L     | **H** | **H** | L     | <audio src="/Lakh/MP3s/midi_4_9_9_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_9_9_4.png" alt = "Piano Roll"> |
| **H** | **H** | L     | L     | <audio src="/Lakh/MP3s/midi_9_9_4_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_9_4_4.png" alt = "Piano Roll"> |
| L     | **H** | L     | **H** | <audio src="/Lakh/MP3s/midi_4_9_4_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_9_4_9.png" alt = "Piano Roll"> |
| **H** | L     | **H** | L     | <audio src="/Lakh/MP3s/midi_9_4_9_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_4_9_4.png" alt = "Piano Roll"> |
| **H** | L     | L     | **H** | <audio src="/Lakh/MP3s/midi_9_4_4_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_4_4_9.png" alt = "Piano Roll"> |
| L     | **H** | **H** | **H** | <audio src="/Lakh/MP3s/midi_4_9_9_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_4_9_9_9.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | L     | <audio src="/Lakh/MP3s/midi_9_9_9_4.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_9_9_4.png" alt = "Piano Roll"> |
| **H** | **H** | L     | **H** | <audio src="/Lakh/MP3s/midi_9_9_4_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_9_4_9.png" alt = "Piano Roll"> |
| **H** | L     | **H** | **H** | <audio src="/Lakh/MP3s/midi_9_4_9_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_4_9_9.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | **H** | <audio src="/Lakh/MP3s/midi_9_9_9_9.mp3" controls autoplay loop></audio> | <img src = "/Lakh/Piano_rolls/midi_9_9_9_9.png" alt = "Piano Roll"> |

# Turkish Makam Dataset

L = Low, H = High

| RC    | AIJ   | ND    | NR    | Audio                                                                       | Pianoroll                                                              |
|-------|-------|-------|-------|-----------------------------------------------------------------------------|------------------------------------------------------------------------|
| L     | L     | L     | L     | <audio src="/Turkish/MP3s/midi_3_3_3_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_3_3_3.png" alt = "Piano Roll"> |
| L     | L     | L     | **H** | <audio src="/Turkish/MP3s/midi_3_3_3_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_3_3_8.png" alt = "Piano Roll"> |
| L     | L     | **H** | L     | <audio src="/Turkish/MP3s/midi_3_3_8_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_3_8_3.png" alt = "Piano Roll"> |
| L     | **H** | L     | L     | <audio src="/Turkish/MP3s/midi_3_8_3_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_8_3_3.png" alt = "Piano Roll"> |
| **H** | L     | L     | L     | <audio src="/Turkish/MP3s/midi_8_3_3_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_3_3_3.png" alt = "Piano Roll"> |
| L     | L     | **H** | **H** | <audio src="/Turkish/MP3s/midi_3_3_8_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_3_8_8.png" alt = "Piano Roll"> |
| L     | **H** | **H** | L     | <audio src="/Turkish/MP3s/midi_3_8_8_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_8_8_3.png" alt = "Piano Roll"> |
| **H** | **H** | L     | L     | <audio src="/Turkish/MP3s/midi_8_8_3_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_8_3_3.png" alt = "Piano Roll"> |
| L     | **H** | L     | **H** | <audio src="/Turkish/MP3s/midi_3_8_3_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_8_3_8.png" alt = "Piano Roll"> |
| **H** | L     | **H** | L     | <audio src="/Turkish/MP3s/midi_8_3_8_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_3_8_3.png" alt = "Piano Roll"> |
| **H** | L     | L     | **H** | <audio src="/Turkish/MP3s/midi_8_3_3_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_3_3_8.png" alt = "Piano Roll"> |
| L     | **H** | **H** | **H** | <audio src="/Turkish/MP3s/midi_3_8_8_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_3_8_8_8.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | L     | <audio src="/Turkish/MP3s/midi_8_8_8_3.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_8_8_3.png" alt = "Piano Roll"> |
| **H** | **H** | L     | **H** | <audio src="/Turkish/MP3s/midi_8_8_3_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_8_3_8.png" alt = "Piano Roll"> |
| **H** | L     | **H** | **H** | <audio src="/Turkish/MP3s/midi_8_3_8_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_3_8_8.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | **H** | <audio src="/Turkish/MP3s/midi_8_8_8_8.mp3" controls autoplay loop></audio> | <img src = "/Turkish/Piano_rolls/midi_8_8_8_8.png" alt = "Piano Roll"> |

# Irish Folk Song Dataset

L = Low, H = High

| RC    | AIJ   | ND    | NR    | Audio                                                                    | Pianoroll                                                           |
|-------|-------|-------|-------|--------------------------------------------------------------------------|---------------------------------------------------------------------|
| L     | L     | L     | L     | <audio src="/Folk/MP3s/midi_3_3_3_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_3_3_3.png" alt = "Piano Roll"> |
| L     | L     | L     | **H** | <audio src="/Folk/MP3s/midi_3_3_3_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_3_3_9.png" alt = "Piano Roll"> |
| L     | L     | **H** | L     | <audio src="/Folk/MP3s/midi_3_3_9_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_3_9_3.png" alt = "Piano Roll"> |
| L     | **H** | L     | L     | <audio src="/Folk/MP3s/midi_3_9_3_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_9_3_3.png" alt = "Piano Roll"> |
| **H** | L     | L     | L     | <audio src="/Folk/MP3s/midi_9_3_3_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_3_3_3.png" alt = "Piano Roll"> |
| L     | L     | **H** | **H** | <audio src="/Folk/MP3s/midi_3_3_9_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_3_9_9.png" alt = "Piano Roll"> |
| L     | **H** | **H** | L     | <audio src="/Folk/MP3s/midi_3_9_9_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_9_9_3.png" alt = "Piano Roll"> |
| **H** | **H** | L     | L     | <audio src="/Folk/MP3s/midi_9_9_3_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_9_3_3.png" alt = "Piano Roll"> |
| L     | **H** | L     | **H** | <audio src="/Folk/MP3s/midi_3_9_3_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_9_3_9.png" alt = "Piano Roll"> |
| **H** | L     | **H** | L     | <audio src="/Folk/MP3s/midi_9_3_9_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_3_9_3.png" alt = "Piano Roll"> |
| **H** | L     | L     | **H** | <audio src="/Folk/MP3s/midi_9_3_3_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_3_3_9.png" alt = "Piano Roll"> |
| L     | **H** | **H** | **H** | <audio src="/Folk/MP3s/midi_3_9_9_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_3_9_9_9.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | L     | <audio src="/Folk/MP3s/midi_9_9_9_3.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_9_9_3.png" alt = "Piano Roll"> |
| **H** | **H** | L     | **H** | <audio src="/Folk/MP3s/midi_9_9_3_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_9_3_9.png" alt = "Piano Roll"> |
| **H** | L     | **H** | **H** | <audio src="/Folk/MP3s/midi_9_3_9_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_3_9_9.png" alt = "Piano Roll"> |
| **H** | **H** | **H** | **H** | <audio src="/Folk/MP3s/midi_9_9_9_9.mp3" controls autoplay loop></audio> | <img src = "/Folk/Piano_rolls/midi_9_9_9_9.png" alt = "Piano Roll"> |
