

# Getting notified of Firenze releases #
You can subscribe to Firenze releases via this [RSS feed](http://code.google.com/feeds/p/firenze/downloads/basic).

# Reporting defects or Submiting enhancement requests #
Just send me a message [styrand@gmail.com](mailto:styrand@gmail.com)

# Overview #
Firenze is an open-source java command-line podcast aggregator.

Firenze downloads and manages free audio or video content ("podcasts") and articles (news) for you.

List of features :
  * Cross-platform program (Java based)
  * Multiple simultaneous downloads
  * Resume partial downloads
  * Scheduled downloads
  * Simplicity and ease of use
  * Command-line scriptable
  * Small GUI to edit your configuration
  * Conditional download : user-defined download condition
  * Proxy server support
  * Https support
  * Authentication support (Google reader, FeedBurner and BASIC auth)
  * Support for specific protocols : **feed://** , **itms://** , **itpc://** , **pcast://** and **podcast://**
  * User-defined destination file and folder name (support for all rss tags included [itunes](http://www.itunes.com) tags)
  * Highly configurable for advanced users with full support of [JSR-223 java scripting language](https://scripting.dev.java.net/) like [groovy](http://groovy.codehaus.org/).
  * Extracting additional informations from http page with xpath support
  * Importing and exporting your feed subscriptions (support OPML format)
  * Podcast features :
    * Managing ID3 mp3 tags
    * Split mp3 file after download
    * Launching a command after download (convert media content, increase volume, soundstretching)
    * Synchronising podcasts to your mp3 player
    * Creation of playlist (support M3U format)
  * News features :
    * Offline reading mode (download only the text content of the news)
    * Support for google reader : access to your account, retrieve the unread news, use the googe reader caching feature to retrieve an old news
    * Launching a command after download (extract article for offine reading, convert to pdf and to eBook, text to speech, send mail, [jna](https://github.com/twall/jna) support)
    * Ability to extend firenze with customized commands
    * Synchronising articles to your device (eBook, notebook, smartphone, ...)


# News #

  * In Progress : **Firenze 7.3**
    * Thanks to Martin Arends, add [jna](https://github.com/twall/jna) support in firenze to launch command on linux platform. Ability to extend firenze with customized post download action
    * Thanks to Steve Monro, add BASIC authentication feature
    * Thanks to Rob Schlüter, add user agent property in http header

  * 18/10/2012 : **Firenze 7.2 released**
    * Thanks to Ignacio Penafiel, some corrections in the configuration management at startup
  * 13/08/2012 : **Firenze 7.1 released**
    * Thanks to Thierry Rochelet, Firenze manages now the feeds starting with byte order mark (BOF) chars
    * Redefines the rome itunes duration type because some feeds could not be parsed with it.
    * Modification of the import opml window : add a checkbox to select/deselect all feeds, correct the import of the opml files from itunes (Thanks to Delone Rush)
    * Feeds table in the gui : the state column is updated after editing a feed, the published date column has a human-readly format now
    * Better management of default value property in the gui

  * 11/07/2012 : **Firenze 7.0 released**
    * **Add a small GUI to edit your configuration**
    * Correction in the evaluation of the extension variable for redirected links

  * 04/06/2012 : **Firenze 6.7 released**
    * id3 tag management : refactoring and some corrections

  * 29/05/2012 : **Firenze 6.6 released**
    * some corrections in the build of the default configuration
    * improvements of the resume partial download feature
    * fix encoding in the windows console
    * splitmp3 : rename the file with the orignal name if only one part
    * postdownloadaction : add debug attribute to print output into console
    * configuration loading with xstream

  * 18/05/2012 : **Firenze 6.5 released**
    * firenze donwloads only the resources having a url OR a guid not already downloaded
    * id3 tag management : fix tag modification + picture management
    * postdownloadactions : launched after all downloads completed, add a maxdownloads parameter, management of windows console encoding, logs of command are stored on log file only, add pre-defined commands for conversion
    * google reader account : definition in settings, add useGoogleReaderCache flag
    * splitmp3 keeps the id3 tag now

  * 20/04/2012 : **Firenze 6.0 released**
    * fix url file name management
    * simplify postdownloadactions : ability to group actions into the same element
    * add baseName and basePath properties to simplify action
    * the default destination folder is the title of the feed if the id is not set

  * 20/04/2012 : **Firenze 5.9 released**
    * fix encoding management
    * fix enclosureurl management

[older news](http://code.google.com/p/firenze/wiki/OldNews)

# Installing Firenze #
  * For the current version of Firenze, you will need a [JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html) version 6 or higher.
  * download the latest binary distribution of Firenze [here](http://code.google.com/p/firenze/downloads/list) and unpack it into some directory on your local file system. We call `FIRENZE_HOME` the directory you unpacked the distribution
  * set the `JAVA_HOME` environment variable. This should be set to the directory where your JDK is installed
  * Firenze is now installed properly

# Quick start guide #

## Configuring Firenze with the GUI ##

  * Firenze needs a configuration file called `FIRENZE_HOME/firenze-config.xml` to work. A simple Firenze GUI exists in order to create and edit this file
  * Running Firenze GUI is simple : just launch the batch `FIRENZE_HOME/firenzeUI.bat` on Windows platform or `FIRENZE_HOME/firenzeUI.sh` on Linux/Unix platform
  * You will see the Main window of the Firenze UI

### Main window ###

![http://firenze.googlecode.com/files/Feeds.jpg](http://firenze.googlecode.com/files/Feeds.jpg)


The main window consists of the following areas:

  * File menu : you can invoke most commands from the main menu (at the top of the main window) and from the various context (mouse right click) menus.
  * Toolbar : provides shortcut to often used commands : save, settings, history, import feeds from opml, show logs, firenze web site and online help
  * Help menu : displays help topics, information about Firenze, show logs, ...
  * Add feed panel : type the address (url) of the feed you want then click on the Add button : your feed is added in the list of feeds
  * List of feeds : displays your feeds (title, state, location and published date). you can select one feed in the list and edit (by double-clicking or mouse right clicking) or delete it (Del key or mouse right clicking).
  * Save : click on the Save button to save your feeds configuration (in the `FIRENZE_HOME/firenze-config.xml` file)
  * Exit : click on the Exit button or the Escape key to exit the application without saving

### Settings window ###

![http://firenze.googlecode.com/files/Settings.jpg](http://firenze.googlecode.com/files/Settings.jpg)


The settings window consists of the following areas:

  * Download panel : you can specify a directory for your downloads, set the timeout connection and the maximal number of simultaneous downloads
  * Proxy panel : you can specify you proxy configurations if necessary
  * Google Reader Account : you can configure your google reader access if you want to use google reader features (cache or rss feed access)
  * Commands : you can configure the external programs to use like ffmpeg, eSpeak, ... You can set the maximal simultaneous commands
  * Save : click on the Save button to save your settings (in the `FIRENZE_HOME/firenze-config.xml` file)
  * Cancel : click on the Cancel button or the Escape key to abort your changes

### Import from Opml window ###

![http://firenze.googlecode.com/files/ImportOpml.jpg](http://firenze.googlecode.com/files/ImportOpml.jpg)


The import from Opml window consists of the following areas:

  * Opml file : you can specify an opml file to import
  * Feeds to add : you can check the feeds of your opml file you want to add in Firenze, you can use the checkbox to select/deselect all feeds
  * Save : click on the Save button to import the selected feeds
  * Cancel : click on the Cancel button or the Escape key to abort your import


### Edit Feed configuration ###

![http://firenze.googlecode.com/files/Feed.jpg](http://firenze.googlecode.com/files/Feed.jpg)


The feed window consists of the following areas:

  * Image and title of the feed : you can click on the feed title to open the url of the feed in your browser
  * Google reader cache checkbox : check if you want Firenze to use the cache of google reader (useful to retrieve the oldest entries of the feed)
  * Entry checkbox : check if you want Firenze to search only the entry of the feed (and not the enclosure podcast)
  * Destination folder : type the expression for the destination folder by using the properties (you can display the most used properties in the contextual menu by using the Ctrl-Space key or the mouse right click) then click on the Apply button to display an evaluation of your expression.
  * Destination file : type the expression for the destination file by using the properties (you can display the most used properties in the contextual menu by using the Ctrl-Space key or the mouse right click) then click on the Apply button to display an evaluation of your expression (based on the first entry and enclosure).
  * List of commands : you can add commands to process after a download is completed
  * OK : click on the OK button to confirm your modifications
  * Cancel : click on the Cancel button or the Escape key to abort your modifications

### History window ###


![http://firenze.googlecode.com/files/history.jpg](http://firenze.googlecode.com/files/history.jpg)


The history window consists of the following areas:

  * Find in history : if you want to find a string in the history just type it in the input and click on the find button.
  * List of history : displays your history (feed, type and location). you can select one history in the list and delete it (Del key or mouse right clicking).
  * Save : click on the Save button to save your history
  * Cancel : click on the Cancel button or the Escape key to abort your changes

## Running Firenze ##
  * Running Firenze is simple : just launch the batch `FIRENZE_HOME/firenze.bat` on Windows platform or `FIRENZE_HOME/firenze.sh` on Linux/Unix platform  .
  * Firenze loads the configuration found in the `FIRENZE_HOME/firenze-config.xml` file. If you dont have yet created your firenze configuration see [Configuring Firenze with the GUI](#Configuring_Firenze_with_the_GUI.md).

# Advanced user guide #

You can edit by hand the `FIRENZE_HOME/firenze-config.xml` file to better fit your needs.

## Feed declaration attributes ##
  * **url** : url address of the podcast rss feed
  * **id** : unique identifier of the feed : this attribute is optional (but it must be specified if you have two feeds with the same url).

**Example of a simple firenze-config.xml**
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml"/>    
  </feeds>
</firenze-config>
```

You can declare several feeds. **Be careful ! The id attribute you can specify for a feed must be unique**.

**Example of a firenze-config.xml with several feeds**

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
    <feeds>
      <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml"/>    
      <feed id="The Business Week" url="http://www.businessweek.com/search/podcasts/thebusinessweek.rss"/>    
      <feed url="http://www.europe1.fr/rss_export/feed/on-va-s-gener-laurent-ruquier"/>    
    </feeds>
  </firenze-config>
```

## Setting the destination sub-folder ##
The default download folder is `FIRENZE_HOME/downloads`. Set the settings element if you want to change it. See [Setting the download folder](#Setting_the_download_folder_and_the_maximal_simultaneous_downloa.md).

By default, the enclosures of a feed are downloaded in a same subdirectory of name the feed id. If the id of the feed is not specified, the title of the feed is used.

You can set another name for this subfolder by adding a destinationfolder element like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" 
          description="Richard Fidler conversations">    
      <destinationfolder>ABC - $feed.title</destinationfolder>
    </feed>                                     
  </feeds>
</firenze-config>
```

This element contains an expression .

If a name in the expression starts with $ it references a Firenze property.
This property is replaced at runtime by the corresponding value. An expression can contain multiple properties and constant string.

Here is the list of the main properties managed by Firenze. Note that all rss informations (including additional modules like itunes or media tags) are supported :

| **Name** | **Description** | **Type** |
|:---------|:----------------|:---------|
| $enclosure | current enclosure | SyndEnclosure |
| $enclosure.length | enclosure length (in bytes) | long |
| $enclosure.type | enclosure type | String |
| $enclosure.url | enclosure URL | String |
| $enclosureUrl | enclosure URL object | java.net.URL |
| $enclosureIndex | zero-based index of the current enclosure in the entry | int |
| $entry | current entry | SyndEntry |
| $entry.author | entry author | String |
| $entry.description | entry description | String |
| $entry.link | entry link | String |
| $entry.publishedDate | entry published date | java.util.Date |
| $entry.title | entry title | String |
| $entry.updatedDate | entry updated date | java.util.Date |
| $entry.uri | entry uri | String |
| $entryIndex | zero-based index of the current entry in the feed | int |
| $entry\_itunes.author | corresponding to itunes:author tag including in the item element | String |
| $entry\_itunes.keywords | corresponding to itunes:keywords tag including in the item element | String |
| $entry\_itunes.duration | corresponding to itunes:duration tag including in the item element | String |
| $entry\_itunes.subtitle | corresponding to itunes:subtitle tag including in the item element | String |
| $entry\_itunes.summary | corresponding to itunes:summary tag including in the item element | String |
| $ext | extension of the destination file | String |
| $feed | current feed | SyndFeed |
| $feed.author | feed author | String |
| $feed.copyright | feed copyright | String |
| $feed.description | feed description | String |
| $feed.encoding | feed charset encoding | String |
| $feed.feedType | feed type | String |
| $feed.language | feed language | String |
| $feed.link | feed link | String |
| $feed.publishedDate | feed published date | java.util.Date |
| $feed.title | feed title | String |
| $feed.uri | feed uri | String |
| $feedId | feed identifier | String |
| $feed\_itunes.author | corresponding to itunes:author tag including in the channel element | String |
| $feed\_itunes.subtitle | corresponding to itunes:summary tag including in the channel element | String |
| $feed\_itunes.summary | corresponding to itunes:summary tag including in the channel element | String |
| $file | destination java.io.File object | java.io.File |
| $fileName | destination file name | String |
| $filePath | destination file path | String |
| $baseName | the name of the destination file without extension  | String |
| $basePath | the path of the destination file without extension  | String |
| $history | history associated with the current feed | HistoryData |
| $history.lastDownloadDate | last download date for the current feed | java.util.Date |
| $history.lastPubDate | last published date for the current feed | java.util.Date |
| $history.downloadedUrls | list of downloaded urls for the current feed | java.util.List |
| $history.downloadedGuids | list of downloaded guids for the current feed (guid is the unique entry identifier) | java.util.List |
| $urlFileName | enclosure file name based on the last part of the URL | String |


Firenze distribution supports [groovy](http://groovy.codehaus.org/), the most famous java scripting language.

Just add the attribute type to 'groovy' to mean that you want to use it in your expression.

The same example with the groovy syntax :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" 
          description="Richard Fidler conversations">        
      <destinationfolder type="groovy">"ABC - "+$feed.title</destinationfolder>
    </feed>                                     
  </feeds>
</firenze-config>
```

Note : you can use complex expression by invoking method on property like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" 
          description="Richard Fidler conversations">      
      <destinationfolder type="groovy">"ABC - "+$feed.title.substring(0, 5)</destinationfolder>
    </feed>                                     
  </feeds>
</firenze-config>
```

More generally, Firenze accepts all scripting languages supported by [java scripting framework](https://scripting.dev.java.net/).

To use another scripting language [see here](#More_about_Scripting_language.md).

## Setting the destination file ##
By default, the destination file name is the same as on server (last part of the enclosure url).

You can set another file name by adding a destinationfile element like this ($ext references the extension of the enclosure. For example '.mp3') :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" 
          description="Richard Fidler conversations">    
      <destinationfile>$entry_itunes.subtitle$ext</destinationfile>
    </feed>                                     
  </feeds>
</firenze-config>
```

The same example with the groovy syntax :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <destinationfile type="groovy">$entry_itunes.subtitle+$ext</destinationfile>
    </feed>                                     
  </feeds>
</firenze-config>
```

## Setting a download condition ##
By default only the resources not already downloaded are downloaded. It means a resource cannot be downloaded twice. Firenze stores in a history database the list of the url and the list of the guid (unique entry identifier) of the downloaded resources for each feed. Firenze adds a resource to download if the url and the guid is not present in this list.
But you can add a download condition to limit the number of resources to download
For all feeds, Firenze stores the following informations about the already downloaded enclosures in its history database (located in `USER_HOME/firenze/firenze-history.properties` or `FIRENZE_HOME/firenze-history.properties` (where `USER_HOME` is your home directory)) :
  * $history.lastPubDate : the more recent published date of the downloaded enclosures
  * $history.lastDownloadDate : the more recent download (ie the last) date for this feed
  * $history.downloadedUrls : list of the url of the downloaded resources
  * $history.downloadedGuids : list of the guid of the downloaded resources

If you want to download all enclosures you don't have already, there is nothing to add (default behaviour).

If you want to download only the most recent enclosures, add a downloadcondition element like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate)</downloadcondition>   
    </feed>                                     
  </feeds>
</firenze-config>
```

If you want to download only the first (top) enclosure in the feed, add a downloadcondition element like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <downloadcondition type="groovy">$entryIndex == 0</downloadcondition>   
    </feed>                                     
  </feeds>
</firenze-config>
```

If you want to download only the enclosures published on friday, add a downloadcondition element like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <downloadcondition type="groovy" 
         description="download only if published on friday">$entry.publishedDate.isFriday()</downloadcondition>   
    </feed>                                     
  </feeds>
</firenze-config>
```

## Defining a new Firenze property ##
You can define your own Firenze property. Your property can reference other existing properties.

If you use groovy, you can invoke a method to format it.

For example, to format a date, you can invoke the format method with a pattern (accept a [SimpleDateFormat](http://java.sun.com/j2se/1.5.0/docs/api/java/text/SimpleDateFormat.html) expression).

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <setproperty name="myProps">Fidler$entry.title</setproperty>      
      <setproperty name="fmtPubDate" type="groovy">$entry.publishedDate.format('ddMM')</setproperty>      
      <destinationfile>$myProps$fmtPubDate$ext</destinationfile>
    </feed>                   
  </feeds>
</firenze-config>
```

## Managing the ID3 mp3 tags of a downloaded enclosures ##
If the downloaded enclosure is a mp3 file, you can manage its ID3 tags by adding the mp3tags element.

Firenze can manage ID3v1 and ID3v2 tags.

For example you can just display the existing mp3 tags with the debug attribute like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3 debug="true" />
    </feed>                        
  </feeds>
</firenze-config>
```

You can remove all existing ID3 MP3 tags with the remove attribute like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3 remove="true" />
    </feed>                        
  </feeds>
</firenze-config>
```
You can also specify the value of each mp3 tag with a tagmp3 element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3 remove="true">
        <tagmp3 name="album">Richard Fidler</tagmp3>
      </tagsmp3>
    </feed>                        
  </feeds>
</firenze-config>
```

With the configuration above firenze removes all existing tags in the downloaded enclosures of the feed and then adds the album ID3 tag.

Of course you can add expression in the tagmp3 element :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3 remove="true">
        <tagmp3 name="album">Richard Fidler</tagmp3>
        <tagmp3 name="title">Richard Fidler $entryIndex $entry.title</tagmp3>
      </tagsmp3>
    </feed>                        
  </feeds>
</firenze-config>
```

The original values of the tags are stored in the `tags` property. You can use them.
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3 debug="true">
        <tagmp3 name="album">$tags.album Richard Fidler</tagmp3>
        <tagmp3 name="artist"/>
        <tagmp3 name="title">$tags.album $tags.title $entryIndex $entry.title</tagmp3>
      </tagsmp3>
    </feed>                        
  </feeds>
</firenze-config>
```
With the configuration above firenze displays all existing tags, modify the album and the title tags and removes the artist tags (the other tags are unchanged) :

You can also add or modify the cover embedded in the mp3 by specifiying the path of the image in the picture tag :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <tagsmp3>
        <tagmp3 name="picture">./cover/abc.jpg</tagmp3>
      </tagsmp3>
    </feed>                        
  </feeds>
</firenze-config>
```

Here is a complete example with all the available tags :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast09/rss_10217.xml">
      <tagsmp3 debug="true">
        <tagmp3 name="title">$entry.title</tagmp3>
        <tagmp3 name="artist">$entry.author</tagmp3>
        <tagmp3 name="album">$feed.title</tagmp3>
        <tagmp3 name="albumArtist">$feed_itunes.author</tagmp3>
        <tagmp3 name="conductor">$feed_itunes.author</tagmp3>
        <tagmp3 name="duration">$entry_itunes.duration</tagmp3>
        <tagmp3 name="mediaType">audio/mp3</tagmp3>
        <tagmp3 name="year">2012</tagmp3>
        <tagmp3 name="comment">$tags.comment ; $feed_itunes.author</tagmp3>
        <tagmp3 name="genre">Podcast</tagmp3>
        <tagmp3 name="mixArtist">$feed_itunes.author</tagmp3>
        <tagmp3 name="lyricist">$feed_itunes.author</tagmp3>
        <tagmp3 name="picture">./cover/radio_france.jpg</tagmp3>
        <tagmp3 name="encodedBy">Sebou</tagmp3>
        <tagmp3 name="trackNumber">$entryIndex</tagmp3>
        <tagmp3 name="trackTotal">15</tagmp3>
      </tagsmp3>
    </feed>  
  </feeds>
</firenze-config>
```


Of course you can add groovy expression in the tag element by specifying the type attribute.

Here is the list of the available ID3 mp3 tags :

| **Firenze Name** | **id3v1 name** | **id3v2 names** | **Type** | **Description**  |
|:-----------------|:---------------|:----------------|:---------|:-----------------|
| title | title | TITLE (TIT2) | String | title (songname)  |
| artist | artist | ARTIST (TPE1) | String | artist name  |
| album | album | ALBUM (TALB) | String | album (show) name  |
| albumArtist | - | ALBUM\_ARTIST (TPE2) | String | album artist |
| discNumber | - | DISC\_NO (TPOS) | Number |  |
| duration | - | TLEN | Number | duration in seconds  |
| mediaType | - | MEDIA (TMED) | String |  |
| year | year | YEAR (TYER) | Number |  |
| comment | comment | COMMENT (COMM) | String | list of comments : use ; char to separate multiple values  |
| trackNumber | track | TRACK (TRCK) | String | number of the track |
| trackTotal | - | TRACK\_TOTAL (TRCK) | String | total number of tracks |
| genre | genre | GENRE | String |  |
| composer | - | COMPOSER (TCOM) | String |   |
| engineer | - | ENGINEER (TIPL) | String |   |
| publisher | - | RECORD\_LABEL (TPUB) | String |   |
| conductor | - | CONDUCTOR (TPE3) | String |   |
| mixArtist | - | REMIXER (TPE4) | String |   |
| lyricist | - | LYRICIST (TEXT) | String | text writer |
| picture | - | COVER\_ART (APIC) | String | picture path |
| encodedBy | - | ENCODER (TENC) | String | encoded by |


## Splitting a downloaded enclosures ##
If the downloaded enclosures is a mp3 file, you can split it into several parts by adding a splitmp3 element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <splitmp3 deleteOnExit="true" range="00.00 15.00 25.00 35.00 EOF" />
    </feed>                        
  </feeds>
</firenze-config>
```
The range attribute contains all the split points (MM.SS format or EOF to specify the end of file). You can set the attribute deleteOnExit to "true" if you want to delete the original file after splitting.

Instead of range, you can specify the number splitting parts like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <splitmp3 deleteOnExit="true" nbParts="10" />
    </feed>                        
  </feeds>
</firenze-config>
```
You can also specify the preferred size of each part (format MM.SS) like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <splitmp3 deleteOnExit="true" partSize="10.00" />
    </feed>                        
  </feeds>
</firenze-config>
```

If you want to retrieve only the last ten minutes of the feed, add the attribute fromEnd like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <splitmp3 deleteOnExit="true" fromEnd="true" range="00.00 10.00" />
    </feed>                        
  </feeds>
</firenze-config>
```

Note that the splitmp3 action keeps the id3 mp3 tags.

## Setting the download folder and the maximal simultaneous download ##

The download element is optional. You can add it in the settings element if you want to specify :
  * **dir** : the download folder into which podcasts will be downloaded. By default all enclosures are downloaded into the `FIRENZE_HOME/downloads` directory.
  * **maxdownloads** : maximal simultaneous downloads per session (recommended options range between 1 and 50, 5 is the default value). This setting can be very useful in improving download performance.

## Defining a configuration for all feeds ##
These elements can be define for all feeds :
  * setproperty
  * downloadcondition
  * destinationfolder
  * destinationfile
Just add them in a global-feed element like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <download dir="C:/downloads" maxdownloads="5"/>
    <global-feed> 
      <setproperty name="fmtPubDate" type="groovy">$entry.publishedDate.format('ddMM')</setproperty>      
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate)</downloadcondition>   
      <destinationfile type="groovy">$entry.title+$fmtPubDate+".mp3"</destinationfile>             
    </global-feed> 
  </settings> 
  <feeds>
    ...
    ...
  </feeds>
</firenze-config>
```
By default, all feeds use the global feed settings. But each feed can then overridden some of these elements :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <download dir="C:/downloads" maxdownloads="5"/>
    <global-feed> 
      <setproperty name="fmtPubDate" type="groovy">$entry.publishedDate.format('ddMM')</setproperty>      
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate)</downloadcondition>   
      <destinationfile type="groovy">$entry.title+$fmtPubDate+".mp3"</destinationfile>             
    </global-feed> 
  </settings> 
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <destinationfile type="groovy">"Fidler"+$entryIndex+"-"+$fmtPubDate+$ext</destinationfile>             
    </feed>
  </feeds>
</firenze-config>
```

## More about Scripting language ##
By default, Firenze distribution provides [groovy](http://groovy.codehaus.org/), the most famous java scripting language.

Its syntax is very near from java. You can use it to define new property, set a download condition or destination file name and folder.

You can invoke method (such as substring() or replace()) on a firenze property like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <download dir="C:/downloads" maxdownloads="5"/>
    <global-feed> 
      <setproperty name="fmtPubDate" type="groovy">$entry.publishedDate?.format('ddMM')</setproperty>      
      <setproperty name="dayInWeekDate" type="groovy">$entry.publishedDate?.format('EEEEEEEEEE')</setproperty>     
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate)</downloadcondition>   
      <destinationfile type="groovy">$entry.title+$fmtPubDate+".mp3"</destinationfile>             
    </global-feed> 
  </settings> 
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">    
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate) 
           &amp;&amp; $dayInWeekDate == 'friday' &amp;&amp; ($entry.title =~ 'A special .Conversations.').find()
      </downloadcondition>   
      <destinationfile type="groovy">"Fidler"+$entry.title.substring(3)+$ext</destinationfile>             
    </feed>
  </feeds>
</firenze-config>
```

You can use all operators provided by [groovy](http://groovy.codehaus.org/) :
  * Safe navigation operator : ?. to avoid null reference
  * Elvis operator : ?: to simplify ternary operation
  * Regular Expression Operators to find '=~' or to match '==~'

More info about these useful operators [here](http://groovy.codehaus.org/Operators)

Note that the xml entities must be escaped in your scripts : type &amp;&amp; for a logical and.

If your script contains special characters (like quote or &gt; and &lt;) you can use the CDATA notation to protect them :

Firenze distribution provides groovy library. But it is possible to use another JSR-233 scripting languages. To use another scripting language :
  * Copy the library of the language you want to use (for example bsh.jar for beanshell) in the `FIRENZE_HOME/lib` directory
  * Add the extension (or the name) of the language in the attribute type of the xml property element where you want to use this language (for example bsh for beanshell).
Here is the list of the other java scripting languages :

## Extracting information from html page with xpath ##
Informations (for example title or subject of an enclosure) found in the feed is sometimes not enough.

It can be interesting to retrieve this info from another html page.

Firenze provides a mechanism to do that using the powerful [xpath](http://www.w3schools.com/xpath/default.asp) language.

Define a setproperty element and set the following attributes :
  * name : this is the name of the property which stores the extracted info.
  * url : this is the url of the page to parse.
  * default : the default value for the property if the info to extract is not found, this value can contain expression with properties

Then define the text element which contains the xpath expression. This expression can contain others properties.

Example of xpath :

`//td[. = '$entry.title']/td` : this expression finds the contents of the 'td' elements following a 'td' element which contains the value of variable $entry.title

`//li[strong[. = '$slashPubDate']]/a/text()` : this expression finds the contents of the 'a' elements following a 'li' element which contains a strong element with the value of variable $slashPubDate

Note : if the xpath evaluation returns more than one results, firenze takes only the first result.

You can learn more about xpath language [here](http://www.w3schools.com/xpath/default.asp)
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <setproperty name="httpInfo" url="http://www.radiofrance.fr/franceinter/em/2000ansdhistoire/archives.php" 
                     default="$entry.title">   
        //li[strong[. = '$slashPubDate']]/a/text()
      </setproperty>   
      <destinationfile type="groovy">"2000ans-"+$httpInfo+$ext</destinationfile>             
    </feed>
  </feeds>
</firenze-config>
```


## Extracting the url of the enclosure to download from the content of entry ##

To increase the traffic of their sites, it is common that a rss feed does not contain any enclosure element. Sometimes the enclosures are only present in each article and not directly in the rss feed. Firenze can parse the content of each entry to extract the url of the enclosure you want to download.

Here is an example of rss feed without enclosure elements :

```
...
<item>
  <title>my title</title>
  <description>my description</description>
  <link>http://www.example.fr/page.html</link>
  <pubDate>Thu, 26 Jan 2012 19:00:00 +0000</pubDate>
</item>
...
```

The url of the desired content to download is present in the page of the article (here http://www.example.fr/page.html) :

```
...
<param name="movie" value="http://www.example.fr/player.swf?loadmp3=true&urlmp3=http:/www.example.fr/media/content.mp3" />
...
```


Firenze can extract the url of the desired content by adding an xpath property. Then define an enclosureurl element to specify the desired url you want to download :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
<feed url="http://www.example.fr/rss">
  <setproperty name="newurl" url="$entry.link">
    //param[@name='movie']/@value
  </setproperty>   
  <enclosureurl type="groovy">$newurl?.substringAfter('urlmp3=')</enclosureurl> 
</feed>
```

## Having multiple configurations ##
Several users can share the same computer and each can use firenze with its personal configuration.

Just move your firenze-config.xml in `USER_HOME/firenze` (where `USER_HOME` is your home directory, create sub-folder firenze if it does not exist).

First Firenze looks for a firenze-config.xml file in your home directory.

If not found, firenze looks for the default firenze-config.xml (located in `FIRENZE_HOME` directory).

## Downloading articles ##

Firenze can be used not only to download podcasts but also your feed articles.
If you want to download articles from a feed just set the `type` attribute to `entry` like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" type="entry"/> 
  </feeds>
</firenze-config>
```

Firenze downloads and manages the articles like the podcasts (ie download condition, destination file, folder, ...)

## Connecting to Google Reader Account to download news ##

Firenze can connect to your Google Reader account to retrieve your reading list (ie list of unread news) :

  * set the `google-reader` element in the `settings`
  * set the `mail` and the `password` attribute of your google reader account

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <google-reader mail="xxx@gmail.com" password="xxx" useGoogleReaderCache="false"/>
  <feeds>
    <feed url="http://www.google.com/reader/atom/user/-/state/com.google/reading-list" type="entry">
      <destinationfile>${entry.title}.html</destinationfile>
    </feed>
  </feeds>
</firenze-config>
```

Firenze will use the google reader authentication if the url of the feed contains the google reader domain.

**Note :** Google provides an API to customize the url of your reading list (see [GoogleReaderAPI](http://code.google.com/p/pyrfeed/wiki/GoogleReaderAPI|)).

## Using Google Reader Caching feature to retrieve an old news ##

Google Reader is more than a feed reader: it's also a platform for feed caching and archiving. That means Google Reader stores all the posts from the subscribed feeds and they're available if you keep scrolling down in the interface. It can be very useful if you want to retrieve an older news that is no more available in the original rss feed.

Just enter this URL in the address bar of your browser :
http://www.google.com/reader/atom/feed/FEED_URL?n=NUMBER_OF_ITEMS
and replace FEED\_URL with the address of your feed and NUMBER\_OF\_ITEMS with the maximal number of historical posts from the feed.

For example, you can compare the result in your browser between this original feed :

```
http://www.abc.net.au/queensland/conversations/conversationspodcast.xml
```

and the google reader version :

```
http://www.google.com/reader/atom/feed/http://www.abc.net.au/queensland/conversations/conversationspodcast.xml?n=5000
```

You will notice that the original feed contains more less entries than the google reader feed.
So you can use google reader to retrieve your news, particularly if the news you want have disapperead from the original feed.

If you want to use the great google reader caching feature for all your feeds, just set `useGoogleReaderCache` to true :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
 <feeds>
  <google-reader mail="xxx@gmail.com" password="xxx" useGoogleReaderCache="true"/>
  <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml">
     <destinationfile>${entry.title}.html</destinationfile>
  </feed>
 </feeds>
</firenze-config>
```

You can also just enable it for one feed like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
 <feeds>
  <google-reader mail="xxx@gmail.com" password="xxx" useGoogleReaderCache="false"/>
  <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" useGoogleReaderCache="true">
     <destinationfile>${entry.title}.html</destinationfile>
  </feed>
 </feeds>
</firenze-config>
```

By default the google reader caching feature is not enabled.
Note that it is not necessary you subscribe in google reader the feeds you want to cache.

## Accessing protected feeds ##

Some platforms like [FeedBurner](http://www.feedburner.com) can protect your feed with a required username and password using HTTP authentication. Any requests for your burned feed will require readers to enter a username and password to retrieve it.
Firenze can access these protected feeds : just add `authUser` and `authPass` attributes in your feed definition :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  ...
  ...
  <feeds>
    <feed url="http://feedburner.com/rss.xml" authUser="username" authPass="password"> 
      ...
      ...
    </feed>
  </feeds>
</firenze-config>
```


If you dont want to store the username and the password of your protected feed in clear in your configuration file, you can encode it in base 64 on this site [Base64 encoder](http://www.motobit.com/util/base64-decoder-encoder.asp) :
- combine username and password into a string "username:password" and click to Convert
- paste the result value in the `authToken` attribute :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  ...
  ...
  <feeds>
    <feed url="http://feedburner.com/rss.xml" authToken="dXNlcm5hbWU6cGFzc3dvcmQ="> 
      ...
      ...
    </feed>
  </feeds>
</firenze-config>
```


## Launching a command after download for media files ##

Firenze can execute some arbitrary scripts after a download has finished.

There are some pre-defined commands :

  * convert a video to an audio file (using ffmpeg)
  * reencode an audio file (using ffmpeg)
  * time stretching (using soundstretch)
  * increase the volume of an audio file (using ffmpeg)
  * convert an article to an eBook file (using kindlegen)
  * convert an article for offline reading
  * convert an article to pdf (using wkhtmltopdf)
  * convert an article to audio file (using eSpeak)

These pre-defined commands deletes the original file and the temparory crated files. They keeps the original id3 mp3 tags too.
We advise you to use [ffmpeg](http://ffmpeg.org/), [soundstretch](http://www.surina.net/soundtouch/soundstretch.html), [wkhtmltopdf](http://code.google.com/p/wkhtmltopdf/) , [kindlegen](http://www.amazon.com/kindleformat/kindlepreviewer) to process your files.

First of all, add the `command` element in the `settings` to configure the path of the executables you want to use.

Note the `maxcommands` attribute to configure the maximal simultaneous command to launch (default : 1). The commands are launched when all downloads are completed.

For example if you want to convert a video to an audio file, add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" ffmpeg="C:/app/ffmpeg/bin/ffmpeg" />
  </settings>
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction ref="convert2mp3"/>
    </feed>                   
  </feeds>
</firenze-config>
```

Note you have to install [ffmpeg](http://ffmpeg.org/) before. The command deletes the original file.

If you want to increase the volume of an audio mp3 file, add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" ffmpeg="C:/app/ffmpeg/bin/ffmpeg" />
  </settings>
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction ref="increaseVolume"/>
    </feed>                   
  </feeds>
</firenze-config>
```
Note you have to install [ffmpeg](http://ffmpeg.org/) before.

If you want to process an audio file for faster playback (soundstretching), add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" ffmpeg="C:/app/ffmpeg/bin/ffmpeg" soundstretch="C:/app/soundstretch/soundstretch" />
  </settings>
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction ref="soundstretch"/>
    </feed>                   
  </feeds>
</firenze-config>
```

Note you have to install [soundstretch](http://www.surina.net/soundtouch/soundstretch.html) and  [ffmpeg](http://ffmpeg.org/) before.

If you want to read your articles without internet connection, just add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://www.oezratty.net/wordpress/feed/atom/" type="entry">
      <destinationfile>${entry.title}.html</destinationfile>
      <postdownloadaction ref="offlineReading"/>
    </feed>
  </feeds>
</firenze-config>
```

Firenze will extract the articles and save only the text with a minimalist stylesheet.

If you want to convert an html article to pdf, just add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" wkhtmltopdf="C:/app/wkhtmltopdf/wkhtmltopdf" />
  </settings>
  <feeds>
    <feed url="http://www.oezratty.net/wordpress/feed/atom/" type="entry">
      <destinationfile>${entry.title}.html</destinationfile>
      <postdownloadaction ref="html2pdf"/>
    </feed>
  </feeds>
</firenze-config>
```

You can also extract text and then convert to pdf like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" wkhtmltopdf="C:/app/wkhtmltopdf/wkhtmltopdf" />
  </settings>
  <feeds>
    <feed url="http://www.oezratty.net/wordpress/feed/atom/" type="entry">
      <destinationfile>${entry.title}.html</destinationfile>
      <postdownloadaction ref="offlineReading"/>
      <postdownloadaction ref="html2pdf"/>
    </feed>
  </feeds>
</firenze-config>
```


Note you have to install [wkhtmltopdf](http://code.google.com/p/wkhtmltopdf/) before.

If you want to convert an html article to audio mp3 file, just add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" ffmpeg="C:/app/ffmpeg/bin/ffmpeg" espeak="C:/app/espeak/espeak.exe" />
  </settings>
  <feeds>
    <feed url="http://www.oezratty.net/wordpress/feed/atom/" type="entry">
      <destinationfile>${entry.title}.html</destinationfile>
      <postdownloadaction ref="text2speech"/>
    </feed>
  </feeds>
</firenze-config>
```

Note you have to install [eSpeak](http://espeak.sourceforge.net/) and  [ffmpeg](http://ffmpeg.org/) before.

If you want to read your articles on eBook, just add a postdownloadaction element to convert the format like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <command maxcommands="1" kindlegen="C:/app/kindlegen/kindlegen" />
  </settings>
  <feeds>
    <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" type="entry"> 
      <postdownloadaction ref="html2mobi"/>
    </feed>                   
  </feeds>
</firenze-config>
```

Note : you have to install the [kindlegen](http://www.amazon.com/kindleformat/kindlepreviewer) tool before.

## Launching a cutom script after download for media files ##

Firenze can execute your own script after a download has finished.

If you want to manage your own commands, add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction description="my own soundstretch command">
        C:\app\ffmpeg\bin\ffmpeg -i "${filePath}" "${basePath}.wav"
        C:\app\soundstretch\soundstretch "${basePath}.wav" "${basePath}-fast.wav" -tempo=+50 -speech
        del "${filePath}"
        del "${basePath}.wav" 
        C:\app\ffmpeg\bin\ffmpeg -i "${basePath}-fast.wav" -acodec libmp3lame -ab 96k "${filePath}"
        del "${basePath}-fast.wav"  
      </postdownloadaction>      
    </feed>                   
  </feeds>
</firenze-config>
```

The property `$filePath` contains the path of the current downloaded enclosure. The properties `$basePath` and `$baseName` can be useful to easily change the extension of the file.

If your custom command does not work on your platform (it can happen on linux platform  for example), you can use the jna (java native access) support. Just set the ref attribute to 'jna' like this :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction description="my own soundstretch command" ref="jna">
        php notify.php
        jabber ...
      </postdownloadaction>      
  </feeds>
</firenze-config>
```

## Extending Firenze : create your own service ! ##

It is possible to create your own command directly in java !

Firenze support the [Service-Provider](http://docs.oracle.com/javase/6/docs/api/java/util/ServiceLoader.html) loading facility.

Suppose you want to send an email after a download finished.

First create your own class, called MailService .

This class extends org.firenze.command.Service and implements the two abstract methods :

  * getId() : returns the unique identifier for this service
  * process() : which contains your command :

```
package my.firenze.service;

import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;
import javax.activation.*;

public class MailService extends Service {
  /**
   * Unique identifier for the service. Must be the same as the 'ref' attribute in the firenze config file
   */
  public String getId() {
    return "mail";
  }
  @Override
  public void process(FirenzeContext context, ExpressionConfig command) throws Exception {
      // get the recipient in the config file (postdownloadaction element)
      String to = command.getExpression().trim();

      // Sender's email ID needs to be mentioned
      String from = "web@gmail.com";

      // Assuming you are sending email from localhost
      String host = "smtp.google.com";

      // Get system properties
      Properties properties = System.getProperties();

      // Setup mail server
      properties.setProperty("mail.smtp.host", host);

      // Get the default Session object.
      Session session = Session.getDefaultInstance(properties);

      try{
         // Create a default MimeMessage object.
         MimeMessage message = new MimeMessage(session);

         // Set From: header field of the header.
         message.setFrom(new InternetAddress(from));

         // Set To: header field of the header.
         message.addRecipient(Message.RecipientType.TO,
                                  new InternetAddress(to));

         // Set Subject: header field
         message.setSubject("Download completed for "+context.getFeed().getTitle());

         // Now set the actual message
         message.setText("Enclosure downloaded : "+context.getEnclosure().getUrl()+" from entry : "+context.getEntry().getTitle());

         // Send message
         Transport.send(message);
         LOG.info("Sent message successfully....");
      }catch (MessagingException mex) {
         LOG.error("Error while sending message",mex);
      }
   }    
  }

}
```

Then create a service-configuration file called org.firenze.command.Service in the resource directory META-INF/services. This file contains a list of fully-qualified names of concrete service classes, one per line. In our case, the file contains only one line :

```
my.firenze.service.MailService
```

Package your service : create a jar containing your Service class and your service-configuration org.firenze.command.Service file.

Deploy your service : copy your jar (and all dependencies like mail.jar ...) in the FIRENZE\_HOME/lib directory

Firenze can now execute your own service after a download has finished, add a postdownloadaction element like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://radiofrance-podcast.net/podcast/rss_14864.xml"> 
      <postdownloadaction ref="mail">
        bob.clinton@gmail.com
      </postdownloadaction>      
    </feed>                   
  </feeds>
</firenze-config>
```

## Disabling a feed ##
You can temporarily disable a feed.

Firenze will not check this feed but your configuration will not be lost. Set the enabled feed attribute to "false".

If you want then to re-enable this feed, set this attribute to "true" :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <feeds>
    <feed url="http://podcast.rtl.fr/onrefaitlematch.xml" enabled="false"/>    
  </feeds>
</firenze-config>
```

## Setting a download timeout / Setting a proxy ##
It can be useful to abort very long download.

You can add a download timeout (in seconds).

If you have a proxy, you can add the proxy host and port like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <download maxdownloads="10" timeout="1"/>
    <proxy host="host.myproxy" port="2525"/>        
  </settings> 
  ...
</firenze-config>
```

You can use the system proxy configuration like this :
```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <proxy useSystemProxies="true"/> 
  </settings> 
  ...
</firenze-config>
```

## Synchronizing podcasts to MP3 player ##
You can easily synchronize your podcasts from your desktop to your MP3 player.

  * Edit your firenze configuration to add the `sync` element in the `settings` :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">
  <settings>
    <sync extension=".mp3, .mp4" dest="G:/MP3 Player/Music, H:/MP3 Player/Music" backup="true" overriddenFile="true">
      <playlist path="./playlist/playlist.m3u" overriddenFile="true"/>
    </sync>
  </settings>   
  ...
</firenze-config>
```

The `extension` and the `dest` attributes are mandatory. They contain respectively the list (comma-separated) of accepted extension and the list (comma-separated) of destination directories. You can specify more than one destination directory because it is not always the same disk assigned when you connect your MP3 player on your computer. Firenze will take the first available destination directory.

If `overriddenFile` is set to false, Firenze will not replace the podcasts with the same name on your MP3 player. By default, `overriddenFile` is set to true.

If `backup` is set to true, Firenze will move the podcasts on your computer in a `transferred` sub-folder. By default, `backup` is set to true.

You can add a playlist if you want to create a playlist on your MP3 player. This playlist will contain all your podcasts copied to your player.

  * When your configuration is complete and saved, launch the batch `FIRENZE_HOME/firenzeSync.bat` on Windows platform or `FIRENZE_HOME/firenzeSync.sh` on Linux/Unix platform .

## Synchronizing articles to eBook or device ##
You can easily synchronize your articles from your desktop to your device (eBook, smartphone, laptop, ....)

  * Edit your firenze configuration to add the `sync` element in the `settings` :

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">
  <settings>
    <sync extension=".pdf, .mobi" dest="G:/eBook/News, H:/eBook/News" backup="true" overriddenFile="true"/>
  </settings>   
  ...
</firenze-config>
```

The `extension` and the `dest` attributes are mandatory. They contain respectively the list (comma-separated) of accepted extension and the list (comma-separated) of destination directories. You can specify more than one destination directory because it is not always the same disk assigned when you connect your device on your computer. Firenze will take the first available destination directory.

If `overriddenFile` is set to false, Firenze will not replace the files with the same name on your device. By default, `overriddenFile` is set to true.

If `backup` is set to true, Firenze will move the file on your computer in a `transferred` sub-folder. By default, `backup` is set to true.

  * When your configuration is complete and saved, launch the batch `FIRENZE_HOME/firenzeSync.bat` on Windows platform or `FIRENZE_HOME/firenzeSync.sh` on Linux/Unix platform .


## Scheduling Firenze ##
Firenze is a command line utility, just add it in your preferred schedule service (at, crontab, etc ...) !

# Examples #

This [firenze-config.xml](http://code.google.com/p/firenze/wiki/SimplestExampleOfFirenzeConfigXml) contains the minimal configuration for firenze.

This [firenze-config.xml](http://code.google.com/p/firenze/wiki/SimpleExampleOfFirenzeConfigXml) contains a simple configuration for firenze.


# Why Firenze ? #

Because Firenze is a great town and this software uses [ROME](http://rometools.org/), the famous RSS and Atom Utilities java library.
