# Light-Novel-LazyReader
A simple python notebook that scrapes light novel websites and converts data into audiobooks.

The program works by using a web crawler that starts on a url of a light novel chapter moving through the links of every succeeding chapters.
For every node (light novel chapter) the crawler travels, if scrapes the contents of the light novel and saves the data into a dictionary.

Chapters collected are then saved into text files.
Converting the text files into audiobooks is done using [Balabolka - Command Line Utility](http://balabolka.site/bconsole.htm) .

## Usage
Download [Balabolka - Command Line Utility](http://balabolka.site/bconsole.htm) and place it within the same directory as the the python notebook. To output .mp3 files instead of .wav (produce smaller files), download [Lame](http://www.rarewares.org/mp3-lame-bundle.php) and place it within the same directory.

Select a light novel from one of the supported sources and copy the url of the first chapter.

Open LN-LazyReader.ipynb and modify the value of `root_url` to the copied url.
The program will attempt to download all chapters starting from the `root_url`.
```
# Root url
root_url = 'https://m.wuxiaworld.co/Reincarnation-Of-The-Strongest-Sword-God/1239956.html'
```

Control the number of chapters to download by modifying the value of `max_chapters`. Set it to None to download all the following chapters.
```
max_chapters = None
```

Run the whole notebook and wait for the crawler to download all the light novel chapters.
The audiobooks will be saved into the `audio_dir` folder.

You can put more light novel sources by adding new filters to `meta_filters`. 
This may require some basic knowledge in regex and python's beautiful soup module.

## Supported sources
- https://m.wuxiaworld.co/
- https://www.royalroad.com/
