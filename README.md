Lazy Series Addict
===========

* Author: [Lyubov Berezina](http://allthatbuzz.com/)
* Version 0.8 September 18th 2013

### Description


### Requirements: 
* Bierdopje account + API key
* (Optional) Trakt account and API key
* curl
* wget
* sed
* awk
* Automator

I give no guarantees that this script will work on your system. It works on mine (Apple MacOS X 10.8.4 Mountain Lion). YMMV.


Pre-setup
-----
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


Install
-------

To install LZA, doubleclick install file in Finder or launch it via terminal. Follow the install script progress as it will ask several questions along the way.

Todo list
---
- [ ] install.sh: remove the trakt part if not using trakt at all (based on user's input)
- [x] switch to Trakt for tracking downloads
