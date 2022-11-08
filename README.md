# <p style="text-align: center;">Movie Dubber</p>

## What does it do?
Movie Dubber allows you to syncronize movie dubs (an audio track) with the movie being dubbed with the help of FFMPEG. Dubbable movies and their options can be selected from the database (Load button). 

## Things you should know
- The database currently only contains dubs from [Jaboody Dubs](https://www.patreon.com/jaboodydubs/posts)
  - More can be added from other dub makers should I find them.
  - Values in the database are from my personal syncings of the dubs. You can adjust them to your liking if they don't feel quite right.
- Some older movies don't like their audio being messed with.
  - If the output file is out of sync, try a different movie file with the same Length, or adjusting delay accordingly.
- Not all movies in the database currently have a delay; they are not usable right now. You must pick a movie with the delay available.

## Screenshots
<details>
  <summary>Screenshots</summary>

  ![Main Screen](https://github.com/f09f9095/Movie-Dubber/blob/main/src/etc/Main%20Screen.png?raw=true)
  ![Main Screen Progress](https://github.com/f09f9095/Movie-Dubber/blob/main/src/etc/Main%20Screen%20Progress.png?raw=true)
  ![Database](https://github.com/f09f9095/Movie-Dubber/blob/main/src/etc/Database.png?raw=true)
</details>


## Instructions
Things you'll need:
- ffmpeg [added to your path](https://www.youtube.com/watch?v=3z9rUl9r2oA) - [Windows](https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-full.7z)
  - You may also take the ffmpeg.exe from ffmpeg-git-full zip and put it in the root folder of the Movie Dubber exe (or same folder where __init__.py is, if running from source).
- A movie file that **_matches the Length_** of the listed movie in the database in format: `mkv, mp4`
  - The only working movies are ones in the database with a Delay listed. The database will be updated when I can.
- An audio track to lay over the movie in format: `mp3, m4a`
- If you want to run the program from source, just have Python 3.8+ installed and run __init__.py

Steps:
>1. Select output folder where movie will be saved
>2. Select input movie file (Should match movie duration (Length) in database for proper sync)
>3. Select input audio track
>4. Select movie to be synced from database (Must have delay)
>5. Adjust volume and ratio options if desired - I recommend using ratio 2.5 usually
>6. Press Encode and wait

Options:
- Delay (ms): In this box you enter how long to delay the added audio track.
  - This option is usually added from the database unless you know how to syncronize the dubs yourself.
- Volume: This box allows you to change the movie file volume level.
  - Entered value should be an (+/-) integer. Value will adjust movie decible level.
  - Example: Value of 5 will raise movie volume 5dB; value of -3 will lower movie volume 3dB.
- Ratio: Ratio allows you to have the added audio track take precidence over the movie.
  - Valid entries: 1 to 9.99
  - Example: Setting Ratio to 2.5 will mean the movie audio will lower itself 2.5x while the added audio track is producing audio (talking).
