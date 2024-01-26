# RockSniffer
RockSniffer is an application designed for Rocksmith 2014 streamers.
It allows you to display the currently played song and some gameplay stats automatically in realtime.

RockSniffer_PJ is an altered fork of the original RockSniffer with enhanced playtracking status and more robust logging. 
The fork will track whether a song has been paused or restarted, and outputs times-stamped song-details on song start and end. 
The intended use case is to enhance stat tracking and video editing capabilities, as the time-stamps can be used to cut individual song videos from larger recordings.

# ADDITIONAL FEATURES
- Output of 'game_stage.txt', which tracks Rocksmith's internal game state (i.e., whether you are in a song or in menus)
- Output of 'game_state.txt', which tracks Rocksmith's status using Rocksniffer (includes Pause and Restart detection!)
- Logs times with millisecond precision
- Logs song details and player stats on output, stored in 'sniffer.log'. Includes whether the song was ever paused or restarted AND CDLC author!

## Example Log Ouput:
[2024-01-25 20:42:12.409] EVENT=START;artist=Rush;album=A Farewell to Kings;year=1977;song=Closer to the Heart;length=182.345;path=Bass;tuning=E Standard;author=Ubisoft;

[2024-01-25 20:42:16.145] Song Paused!

[2024-01-25 20:42:21.235] Song Resumed!

[2024-01-25 20:42:16.145] Song Paused!

[2024-01-25 20:42:28.608] EVENT=END;completed=False;paused=True;accuracy=100%;totalNotes=0;notesHit=0;highestStreak=0;

[2024-01-25 20:42:28.937] EVENT=START;artist=Rush;album=A Farewell to Kings;year=1977;song=Closer to the Heart;length=182.345;path=Bass;tuning=E Standard;author=Ubisoft;

[2024-01-25 20:45:28.516] EVENT=END;completed=True;paused=False;accuracy=98.2%;totalNotes=451;notesHit=443;highestStreak=157;


Note: This shows the output of a song starting, pausing, resuming, pausing, restarting, then finishing! Note the 'Completed' and 'Paused' status in the EVENT=END status.
Log can be easily parsed into different formats such as CSV or JSON.

Requires custom [RockSnifferLib] fork @: (https://github.com/PoizenJam/RockSnifferLib)

# RockSniffer Setup
Go here for a quick guide how to set up RockSniffer: [RockSniffer Wiki](https://github.com/kokolihapihvi/RockSniffer/wiki/Set-Up)

# NOTE

Please note that this version may increase the overhead and write activity compared to the normal Rocksniffer.
It may also be prone to bugs not present in the main Rocksniffer distribution.
If you do not need the features listed above, please download the main Rocksniffer distro.