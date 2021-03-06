# spotifydl

Spotify downloader

## Example

![](imgs/example.gif)

## Setup

1.Create an app: https://developer.spotify.com/dashboard/applications

![](imgs/setup.png)

2.Copy the Client id and client secret

![](imgs/copy.png)

3.Set redirect uri to http://localhost:8888/callback

![](imgs/redirecturi.png)

### Setting Environment Variables (Windows)

`set SPOTIFY_USER_ID <your_user_id>`  
`set SPOTIFY_CLIENT_ID <your_client_id>`  
`set SPOTIFY_CLIENT_SECRET <your_client_secret>`  
`set SPOTIFY_REDIRECT_URI 'http://localhost:8888/callback'`

## Dependencies

To install all modules run `pip install -r requirements.txt`  
Download ffmpeg from here https://github.com/BtbN/FFmpeg-Builds/releases and add it to Environment PATH.

## Usage

`python main.py`

## Sample Output

```
? What do you want to do?  (Use arrow keys)
 ❯ 1.Download your liked songs
   2.Download a playlist
   3.Download a particular song
   4.Exit

? What do you want to do?  1.Download your liked songs
? You have 70 liked songs.
 ❯ 1.Download all
   2.Enter a custom value:
   3.Exit

? Where do you want to download the song?  (Use arrow keys)
 ❯ 1.Current folder
   2.Create a new folder here and download
   3.Enter a custom download path
   4.Exit
```

## Result

![](imgs/songs.png)

## How it works

```
* Program Gets the deatils of the songs from spotify api.
* It then searches the song on youtube and extracts the youtube song url
* The song is then downloaded as mp4 from youtube using Pytube module
* mp4 is converted to mp3 using ffmpeg
* Tags are added to the mp3 song (Artist, title, album, album art image)
```
