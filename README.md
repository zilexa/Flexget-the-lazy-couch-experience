INTRO:
To get a "Netflix-like" experience, please use [AUTOSETUP.SH](https://github.com/zilexa/autosetup "AUTOSETUP.SH") to install and configure the required tools. It will include this config.yml for Flexget. 
The way it works: on http://trakt.tv you can create a free account, add TV Shows you like to follow to a list and add the Trakt.tv addon to your Kodi device. Kodi will sync your watched status with Trakt.tv (privately). Flexget will use this information to get the content you need and organise everything in such a way to deliver the NETFLIX experience! See requirements below before you install this.

NOTE:
This Flexget config is fully based on Jonybat's config.yml. See the CHANGELOG for a full list of changes made to his config.yml. 

In non-Flexget/non-technical terms, this config will allow Flexget to do the following on a daily basis **AUTOMATICALLY**, some tasks are performed more often:

_TVshows:_
- Cleanup (purge) your Trakt account by removing fully watched series that have ended (or are cancelled).
- Gets the series titles you follow on Trakt.
- Finds the next episode you need based on your Watched Status in Trakt.
- Looks for these series on your own drive. 
- Looks for any manually .torrent files in your Downloads\tempmedia folder.
- Looks for the latest episodes on RSS feeds.
- Looks for your old series season packs and single episodes by discovering them on several websites.
- Downloads if they match your requirements to prevent low quality files or language specific versions from being downloaded. 
- Download regular HDTV quality to save space, this is an acceptable quality. If not found, accept 720p/1080p HD quality on the next run.
- Save to /TVDB seriesname/seasonnumber/ folders so that 1) Kodi will recognise the correct tvshow and to make it easy to cleanup your drive (simply delete the season folders). 
- Download the main file only, no other clutter that is usually present. 

_Subtitles:_
- Find subtitles when the download is finished.
- Add downloaded files without subs to the subtitle queue, Flexget will continue searching subs even after the files have been moved/renamed to the proper location.

_Movies:_
- Cleanup (purge) your Trakt account by removing movies you already have from the Trakt watchlist.
- Gets the movies you would like to see from your Trakt "watchlist".
- Looks for movies on your drive and removes them from your Trakt "watchlist". 
- Looks for any manually downloaded .torrent file in your Downloads\tempmedia folder.
- Looks for movies by discovering them on several websites. 
- Downloads them but the main file only and only if there is a match with quality requirement: no prereleases or cinema recordings. Only Bluray rips. 

_Organising everything:_
- Searches and downloads matching subtitles for all downloads.
- Moves & renames files to organise them properly in your folders (Movies\movie name\..., TVshows\series name\...). The series/movies title, episode or year, quality. This allows you to easily search and find subtitles in the future using your TV remote during playblack in Kodi. Note that Flexget is much better at this task so chance is very slim you ever need to do this.
- Keeps Transmission, which is used for downloading, clean. 

_And last, but not least: _
- Triggers an update of your Kodi library after files have been processed! They will appear in your Kodi library automatically!


**REQUIREMENTS**
1. The first basic requirement: a device running Kodi, like a Raspberry Pi 3 (highly recommended!), preferrably on Debian, connected to the internet (wired preferred). Forget about OpenElec, you cannot install anything on OpenElec. If you have no clue what all of this means, get a Raspberry Pi 3 and go to: http://osmc.tv to create your own personal mediacenter.

2. A (free, private) account on Trakt.tv. Create a list called "tvshows" and add the shows you would like to see. Also mark episodes/seasons you have already seen as watched otherwise they will be downloaded. 

3. If you need subtitles, create an account on and on, make sure the user/pw are the same for both sites. 

4. Use [AUTOSETUP.SH](https://github.com/zilexa/autosetup "AUTOSETUP.SH") to install. All you have to do is add your Trakt account, subtitles account, Transmission login and the location of your harddrive. Then you can run the file and sit back while it installs. More information via the link. 

5. When finished, make sure you authorise trakt and run Flexget once via these two commands:
Authorize Flexget to access Trakt: ~/flexget/bin/flexget trakt auth YOURTRAKTUSERNAME
Run Flexget once fully: ~/flexget/bin/flexget execute --now



