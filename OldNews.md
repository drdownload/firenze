# Older news #
  * 06/04/2012 : **Firenze 5.8 released**
    * add news aggregator feature : you can retrieve articles from a feed.
    * add offline reading feature : you can extract the text content of an article to read offline
    * add google reader support : you can access to your google reader account

  * 23/03/2012 : **Firenze 5.7 released**
    * attribute overriddenFile of download element is removed : in conflict with resume partial download feature
    * attribute id of feed element becomes optional : by default identifier for a feed is the url. But the feed id must be unique : an error is thrown if two feeds without id have the same url.
    * prompt the user for the creation of the configuration at the first launch
    * migration of the history data file : from properties to the more readable and editable xml format (the properties file is saved after the migration).

  * 19/03/2012 : **Firenze 5.6 released**
    * Add a tool to synchronize podcasts to mp3 player. You can create and add a m3u playlist. See [Synchronizing podcasts to MP3 player](#Synchronizing_podcasts_to_MP3_player.md).
  * 19/03/2012 : **Firenze 5.5.1 released**
    * Correction on resume partial downloads : some rss servers don t support this option (header field 'bytes'). Firenze tries to resume download and if it is not working downloads without resume
    * Add support for Opml : you can import feed declaration from an opml file into your firenze configuration or export the feeds declared in your firenze configuration into an opml file. See [Import OPML](#Importing_subscriptions_from_an_OPML_File.md) and  [Export OPML](#Exporting_subscriptions_to_an_OPML_File.md).
    * Add description attribute for setproperty and feed elements
  * 15/03/2012 : **Firenze 5.4.1 released**
    * Add download condition on query parameter. See [Setting a download condition](#Setting_a_download_condition.md)
    * Add enclosureurl element : this element allows you to redefine the url of the enclosure to download : useful if the rss does not contain the url of the enclosures but only the links to the pages containing the content. See [(Re)Defining the url of the enclosure](#(Re)Defining_the_url_of_the_enclosure.md).
    * Add resume partial downloads support.
    * Add support for specific protocols : more particularly now firenze can manage the `itunes` protocols like **itpc** and **itms**. List of protocols supported :
      * **feed://**
      * **itms://**
      * **itpc://**
      * **pcast://**
      * **podcast://**
    * Simplification of the minimal configuration : the settings and the download elements become optional.
    * Some performance enhancements in the evaluation of properties.
    * **Modification of the configuration : xpathproperty is no longer used and replaced by setproperty.**<font color='red'>Please rename the xpathproperty elements into setproperty in your firenze configuration file : </font>

```
<xpathproperty name="httpInfo" url="http://www.radiofrance.fr/franceinter/em/2000ansdhistoire/archives.php" 
               default="$entry.title">   
   //li[strong[. = '$slashPubDate']]/a/text()
</xpathproperty>   
```

becomes

```
<setproperty name="httpInfo" url="http://www.radiofrance.fr/franceinter/em/2000ansdhistoire/archives.php" 
               default="$entry.title">   
   //li[strong[. = '$slashPubDate']]/a/text()
</setproperty>   
```

  * 28/02/2012 : **Firenze 5.3 released**
    * Add https support, thanks to **Radu Mitrea** : now firenze can download enclosures hosted on a https server.

  * 20/02/2012 : **Firenze 5.2 released**
    * Update library dependencies.
    * Some performance enhancements.

  * 18/10/2011 : **Firenze 5.1 released**
    * Some minor bug fixes and log enhancements.

  * 07/10/2011 : **Firenze 5.0 released**
    * **Modification of the namespace :**<font color='red'>Please modify the root element in your firenze configuration file : </font>

```
<firenze-config xmlns="http://code.google.com/p/firenze/ns/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
```

instead of

```
<firenze-config xmlns="http://berlios.de/ns/firenze/" 
                       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                       xsi:schemaLocation="http://berlios.de/ns/firenze/ firenze-config.xsd ">  
```

  * Migration from berlios to google source code hosting.
  * attribute logged renamed to debug in configuration
  * conditional download change : by default all feed enclosures not already downloaded are downloaded (instead of by default all feed enclosures are downloaded). It means by default an enclosure cannot be downloaded twice now
  * 05/11/2010 : **Firenze 4.5 released**
    * add ID3 mp3 tags management with the great [MyID3 library](http://www.fightingquaker.com/myid3/) : you can now update any tags of your mp3 enclosures automatically after download !
    * correction in encoding management
    * modification : splitaction element becomes splitmp3
  * 30/10/2010 : **Firenze 4.2 released**
    * correction thanks to **Tanel Alumäe** : firenze command works now on linux and unix platform
  * 05/10/2010 : **Firenze 4.1 released**
    * correction thanks to **Daniel Schien** : firenze includes now itunes-0.4-tafix2.jar (instead of itunes-0.4.jar) to fix a problem of duration element
  * 30/09/2010 : **Firenze 4.0 released**
    * migration to JDK 6.0
    * htmlproperty is no longer used and replaced by xpathproperty
    * pattern attribute is no longer used for property element. Use groovy expression instead.
  * 15/01/2010 : **Firenze 3.2 released**
    * support for Groovy and more generally all JSR-223 scripting language
  * 19/06/2009 : **Firenze 3.1 released**
    * support for BSF (Bean Scripting Framework)
    * some improvements in the multithreading download tasks
  * 27/02/2008 : **Firenze 3.0 released**
    * support for xpath expression
  * 05/09/2007 : **Firenze 2.2 released**
    * most reported bugs fixed
    * some numerous small improvements
    * new logo at startup and copy utils.
  * 31/07/2007 : **Firenze 2.1 released**
  * 16/07/2007 : **Firenze 2.0 released**
    * migration to JDK 5 and Rome 0.9 API