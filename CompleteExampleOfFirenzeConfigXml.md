
```
<!-- A more complex Firenze configuration file -->
<firenze-config xmlns="http://code.google.com/p/firenze/ns/"
                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <!-- set attribute dir : root directory to store downloaded enclosures et max simultaneous downloads -->
    <download dir="C:/app/firenze" maxdownloads="1" />
    <!-- proxy settings (optional) -->
    <proxy useSystemProxies="true"/>
    <global-feed>
      <!-- define for all feeds : properties : published date with different format -->
      <setproperty name="slashPubDate" type="groovy">$entry.publishedDate?.format('dd/MM/yyyy')</setproperty>     
      <setproperty name="shortPubDate" type="groovy">$entry.publishedDate?.format('ddMM')</setproperty>     
      <!-- define destination sub-folder -->     
      <destinationfolder>$feed.title</destinationfolder>      
      <!-- define destination file -->     
      <destinationfile>$entry.title$ext</destinationfile>      
    </global-feed>
  </settings> 
  <feeds>
   <!-- define feeds configuration : each feed have a unique id --> 
   <!-- this feed is disabled and contains only default property --> 
   <feed id="Richard Fidler" url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" enabled="false"/>
   <!-- this feed is enabled and redefines download condition and destination file with groovy expression --> 
   <feed id="The Business Week" url="http://www.businessweek.com/search/podcasts/thebusinessweek.rss" enabled="false">
      <!-- define download condition : only enclosure urls not already downloaded and published friday -->     
      <downloadcondition type="groovy">$entry.publishedDate.isFriday()</downloadcondition>   
      <!-- redefine dest file with a complex groovy expression  : use subtitle itune tag is not null and title otherwise -->
      <destinationfile type="groovy">$entry_itunes.subtitle ? "BusinessWeek-"+$entry_itunes.subtitle+$ext : "BusinessWeek-"+$entry.title+$ext</destinationfile>      
   </feed>
   <feed id="Ruquier" url="http://www.europe1.fr/rss_export/feed/on-va-s-gener-laurent-ruquier" enabled="false">
      <!-- define download condition : only enclosure urls not already downloaded published friday and with entry title containing a defined string -->     
      <downloadcondition type="groovy">$dayInWeekDate == 'vendredi' &amp;&amp; ($entry.title =~ 'On va s.gêner..').find()</downloadcondition>   
      <!-- redefine dest file with a complex groovy expression  : use subtitle itune tag is not null and title otherwise -->
      <destinationfile>tmp_$entry_itunes.subtitle$ext</destinationfile>      
      <postdownloadaction>del /Q "$file.parent\$entry_itunes.subtitle$ext"</postdownloadaction>
      <postdownloadaction>C:\app\ffmpeg\bin\ffmpeg -i "$filePath" -acodec libmp3lame -ab 96k "$file.parent\$entry_itunes.subtitle$ext"</postdownloadaction>
      <postdownloadaction>del /Q "$filePath"</postdownloadaction>
   </feed>
    <feed id="masque" url="http://radiofrance-podcast.net/podcast09/rss_14007.xml" enabled="true">
      <setproperty name="httpInfo" url="http://www.radiofrance.fr/franceinter/em/lemasqueetlaplume/archives.php" default="$entry.title">
        //li[strong[. = '$slashPubDate']]/a/text()
      </setproperty>
      <destinationfile type="groovy">"Masque"+$httpInfo+$shortPubDate+$ext</destinationfile>
    </feed>     
  </feeds>
</firenze-config>

```