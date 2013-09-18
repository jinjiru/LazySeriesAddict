Lazy Series Addict
===========

* Author: [Lyubov Berezina](http://allthatbuzz.com/)
* Version 0.8 September 18th 2013

### Description
There're almost 30 TV shows in my regular watchlist (here's my [watchlist]|http://trakt.tv/user/jinjiru/lists/favs) so I was in a desperate need of some system to download, organize and track the episodes. As I could not find anything that suited me I've come up with a system of my own. This system is not perfect and it has some issues to be solved in the future but it's really wirking for me so I decided to share.

The system consists of several parts:

1. Download episodes (not covered here)
2. Download subtitles (I watch my shows in English with English subtitles as I'm not a native speaker)
3. Organize everything with Hazel
4. Keep track of downloaded episodes

The Lazy Series Addict script was born to solve the problems #2-4. This system does not cover the episodes downloading.

##### Download subtitles
After quite a long search I've found a subtitles [website]|http://www.bierdopje.com with an API which allows to get the subtitles download links. In order to use it you will need an API key which is easy to get (please see below). In order not to flood the API DB with the requests I'm using a local config file to store the shows ids. Sometimes it won't find the show or the needed subtitles files so in that cases I download them manually. But in 98% of cases it finds everything ok and there're no problems with that.

##### Organize subtitles with Hazel

##### Keep track of downloaded and watched episodes
I often miss some episodes here and there so I needed to track the downloaded episodes so I could know if I miss something. I decided that if I've downloaded an episode AND susbtitles for this episodes then I can consider it "not missed". So I've decided to use Trakt to track my downloaded episodes. 

Using Trakt requires using imdbid's for the search so I'm using the unofficial IMDB API http://mymovieapi.com and I'm still working on the refining the search mechanism and errors reporting.

Using Trakt requires an API key wich is free and easy to get (please see below).

### Assumptions:
1. The new episodes are downloaded into the ~/Downloads folder
2. All the episodes are stored in the ~/Downloads/TVShows folder without any inner structure (as I do not store the episodes and remove them from my hard drive right after I transfer them to my iPad or watch them on my MBP.
3. All the subtitles are downloaded and stored the same way the episodes are.
4. All the Hazel rules are set up for these folders so if you're using any other folder you will need to change the Hazel rules to reflect your environment.
5. In addition to the Hazel rules I'm using a simple Automator workflow so you will need to have it installed (it comes with all the current MacOS X versions AFAIK). No need to understand any Applescript or Automator itself, the workflow is ready to use (except for a small checkbox you will need to tick while installing LZA (more on this below).

### Requirements and optionals: 
* Bierdopje account + API key
* Trakt account and API key
* curl
* wget
* sed
* awk
* Automator
* Hazel

I give no guarantees that this script will work on your system. It works on mine (Apple MacOS X 10.8.4 Mountain Lion). YMMV.

### Disclaimer
I'm not a programmer of any kind and I have no programming skills. This project is a work in progress and I'm 100% sure it contains bugs. I'm sure there're much more elegant ways of achieving my goals and the code is not optimal at all. But it really works for me and it does not ruin my system :) so I hope you will not judge me :) Any crituque and suggestions on the improving my code are welcome.

### Pre-setup


#### Bierdopje account and API key:

1. Visit http://www.bierdopje.com/ and press Registreren in the upper right corner of the page:

![Bierdopje Registration](http://farm2.static.flickr.com/1098/5128232682_efbdc4022b.jpg)

2. Fill a registration form:

![Registration form](http://farm2.static.flickr.com/1351/5128232638_dfa6b27a57.jpg)

3. Visit you account settings by pressing “instellingen” in the upper right corner:

![Bierdopje Registration](http://farm2.static.flickr.com/1115/5128232278_a48fdb26ba.jpg)

Here's the profile view:

![Bierdopje Registration](http://farm5.static.flickr.com/4052/5128232356_9a5c85256a.jpg)

4. Choose API:

![Bierdopje Registration](http://farm2.static.flickr.com/1106/5127627909_c39824101c_m.jpg)

5. Fill a simple form:

![Bierdopje Registration](http://farm5.static.flickr.com/4071/5127627951_028a039a3b.jpg)

6. Get an API key:

![Bierdopje Registration](http://farm2.static.flickr.com/1088/5127689407_02fcb98aca.jpg)


#### Trakt account and API key

1. Visit http://trakt.tv and press Join Trakt button at the upper right corner:
![Bierdopje Registration](http://farm4.staticflickr.com/3824/9797462873_1216cc782a_o.png)

2. Fill a simple form:

![Bierdopje Registration](http://farm4.staticflickr.com/3714/9797383005_64a379cf45_o.png)

3. Choose Settings from the account dropdown list at the upper right corner:

![Bierdopje Registration](http://farm6.staticflickr.com/5524/9797461973_04fa8bcedc_o.png)

4. Choose API:

![Bierdopje Registration](http://farm8.staticflickr.com/7430/9797396914_708aeee1b4_o.png)

5. Get your API key.

#### Installing wget if needed:
```sh
$> ftp ftр://ftp.gnu.org/gnu/wget/wget-latest.tar.gz 
$> tar -xvzf wget-latest.tar.gz
$> cd wget-{version}
$> ./configure
$> make
$> sudo make install
```


#### Installing curl if needed:
```sh
$> wget -с httр://www.hmug.org/pub/MacOS_X/BSD/Applications/Internet/curl/curl+ssl-7.21.2-1-osx6-x86.tar.gz
$> tar -xvzf curl+ssl-7.21.2-1-osx6-x86.tar.gz
$> cd curl-7.21.2
$> sudo make install
```


### LZA Installation and usage

To install LZA, doubleclick install file in Finder or launch it via terminal. Follow the install script progress as it will ask several questions along the way.

### Todo list

- [ ] install.sh: remove the trakt part if not using trakt at all (based on user's input)
- [x] switch to Trakt for tracking downloads
