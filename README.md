## API Side: EsoLang
curl -X POST https://www.strava.com/oauth/token \
	-F client_id=$CLIENT_ID\
	-F client_secret=$AUTHSECRET \
	-F code=$AUTHCODE \
	-F grant_type=authorization_code

curl --location 'https://www.strava.com/api/v3/athlete/activities' \
 --header 'Authorization: Bearer $BEARER_ACCESS'

SpeedScript Specification
By Frank Sacco, Lawrence Feng, and Theo Urban

Speedscript is a language based on brainfuck which allows you to write code by performing an activity on Strava, an exercise social media site.  The motivation for this esolang is that doing so would allow users to optimize the time they dedicate to self-care, obtaining an optimal 0% self-care time usage by allowing the time taken by working out to be used for real work like writing code.  
The language is effectively just a brainfuck dialect, but the integration with Strava provides an interesting layer of complexity.  To write in this language, you simply perform a Strava activity (eg. running) which has some pace associated with each lap, recorded by performing an action at write-time like pressing a button on a gps watch.  Then, all you need to do is run a compilation python script which accesses your most recent Strava activity via the Strava API and overwrites your description with the brainfuck code and output of that brainfuck code.  This means that the only setup required is to store your user refresh token and api key as an environment variable before running the code.  This could be improved in a future with such technology as a server which just does the whole thing.  
Practically writing(running) code in this language is very hard, but a good first step is to convert the brainfuck code you want to write to lap times.  To do this, I wrote this code which converts specifically “Hello World!” to Strava paces.  I attempted to run this and failed rather horribly.  However, on the next page, I’ve attached the code for hello world and on the page after that the code for reversing a string. 

Note: One present limitation to this language is the inability to read from an input, which is always assumed to be empty, but this could be easily remedied by applying the brainfuck code to the contents of the Strava activity’s description before the python code is run.


Lap 0: 6:30 // 22.5-24.375
Lap 1: 8:30 // 30-31.875
Lap 2: 7:00 // 24.375-26.25
Lap 3: 7:00 // 24.375-26.25
Lap 4: 5:30 // 20.625
Lap 5: 7:00 // 24.375-26.25
Lap 6: 8:30 // 30-31.875
Lap 7: 5:30 // 20.625
Lap 8: 5:30 // 20.625
Lap 9: 6:30 // 22.5-24.375
Lap 10: 5:30 // 20.625
Lap 11: 7:00 // 24.375-26.25
Lap 12: 7:00 // 24.375-26.25
Lap 13: 7:00 // 24.375-26.25
Lap 14: 7:00 // 24.375-26.25
Lap 15: 7:00 // 24.375-26.25
Lap 16: 6:00 // 20.625-22.5
Lap 17: 6:00 // 20.625-22.5
Lap 18: 9:00 // 31.875-33.75
Lap 19: 6:00 // 20.625-22.5
Lap 20: 7:00 // 24.375-26.25
Lap 21: 7:00 // 24.375-26.25
Lap 22: 6:00 // 20.625-22.5
Lap 23: 7:00 // 24.375-26.25
Lap 24: 7:00 // 24.375-26.25
Lap 25: 7:00 // 24.375-26.25
Lap 26: 9:00 // 31.875-33.75
Lap 27: 5:30 // 20.625
Lap 28: 7:00 // 24.375-26.25
Lap 29: 7:30 // 26.25-28.125
Lap 30: 5:30 // 20.625
Lap 31: 5:30 // 20.625
Lap 32: 5:30 // 20.625
Lap 33: 6:30 // 22.5-24.375
Lap 34: 7:30 // 26.25-28.125
Lap 35: 5:30 // 20.625
Lap 36: 5:30 // 20.625
Lap 37: 7:30 // 26.25-28.125
Lap 38: 7:30 // 26.25-28.125
Lap 39: 6:30 // 22.5-24.375
Lap 40: 6:30 // 22.5-24.375
Lap 41: 6:30 // 22.5-24.375
Lap 42: 8:30 // 30-31.875
Lap 43: 7:30 // 26.25-28.125
Lap 44: 5:30 // 20.625
Lap 45: 9:00 // 31.875-33.75
Lap 46: 6:00 // 20.625-22.5
Lap 47: 6:00 // 20.625-22.5
Lap 48: 6:00 // 20.625-22.5
Lap 49: 6:00 // 20.625-22.5
Lap 50: 7:30 // 26.25-28.125
Lap 51: 6:30 // 22.5-24.375
Lap 52: 6:30 // 22.5-24.375
Lap 53: 6:30 // 22.5-24.375
Lap 54: 7:30 // 26.25-28.125
Lap 55: 7:00 // 24.375-26.25
Lap 56: 7:00 // 24.375-26.25
Lap 57: 7:00 // 24.375-26.25
Lap 58: 7:00 // 24.375-26.25
Lap 59: 7:00 // 24.375-26.25
Lap 60: 7:00 // 24.375-26.25
Lap 61: 7:30 // 26.25-28.125
Lap 62: 6:00 // 20.625-22.5
Lap 63: 6:00 // 20.625-22.5
Lap 64: 7:00 // 24.375-26.25
Lap 65: 7:30 // 26.25-28.125
Lap 66: 5:30 // 20.625
Lap 67: 5:30 // 20.625
Lap 68: 5:30 // 20.625
Lap 69: 5:30 // 20.625
Lap 70: 6:30 // 22.5-24.375
Lap 71: 7:30 // 26.25-28.125

Lap 0: 8:00 // 28.125-30
Lap 1: 8:30 // 30-31.875
Lap 2: 5:30 // 20.625
Lap 3: 8:00 // 28.125-30
Lap 4: 9:00 // 31.875-33.75
Lap 5: 6:00 // 20.625-22.5
Lap 6: 8:30 // 30-31.875
Lap 7: 7:30 // 26.25-28.125
Lap 8: 6:00 // 20.625-22.5
Lap 9: 9:00 // 31.875-33.75