# youtube2spotify
Automate addition of liked videos on youtube to a new playlist on spotify
-------------------------------------------------------------------------

This is a script inspired by The Come Up Code's neat idea: https://github.com/TheComeUpCode/SpotifyGeneratePlaylist
I have adapted some of the code for my use. 

The idea:

1. Access Youtube Data API to get all the liked videos 
2. Use youtube_dl to extract song name and artist if it is a music videos
3. Use spotify api to get matching tracks for given songs and artists
4. Create a new spotify playlist
5. Add the tracks to this playlist
6. Enjoy!

### Steps:

**Getting youtube data api credentials**
Follow along https://developers.google.com/youtube/v3/quickstart/python
We will need an OAuth 2.0 client ID json file that can be downloaded from the Credentials tab of the APIs & Services page of your google project


**Getting Spotify API credentials**
  1. First register an app for personal use here: https://developer.spotify.com/dashboard/login
  Get the client_id, client_secret token values. 
  Set the redirect_url ("http://localhost:7777/callback") in settings tab. 

  2. To get your spotify user_id: On the spotify app, go to your profile page. Click on share your profile button and note the url. The alpha-numeric string after /user/ is your user_id. This is different from username which is the name displayed on your profile. 
  (optional info): There are different types of access tokens that Spotify grants.
  Client credentials give API endpoints that can be used to access all the music and non-user related data. 
  To access user data we need to specify the scope and use authorization code flow. This will generate tokens that expire every hour. 
  Details: https://spotipy.readthedocs.io/en/2.12.0/#authorization-code-flow

**Add your spotify credentials to credentials.py file.**


**Run youtube2spotify.ipynb**
