
```
<!-- A very simple Firenze configuration file -->
<firenze-config xmlns="http://code.google.com/p/firenze/ns/"
                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                xsi:schemaLocation="http://code.google.com/p/firenze/ns/ firenze-config.xsd ">  
  <settings>
    <!-- set attribute dir : root directory to store downloaded enclosures -->
    <download dir="C:/app/firenze" maxdownloads="10" />
    <!-- proxy settings (optional) -->
    <proxy useSystemProxies="true"/>
    <global-feed>    
      <setproperty name="slashPubDate" type="groovy">$entry.publishedDate.format('dd/MM/yyyy')</setproperty>     
      <downloadcondition type="groovy">$entry.publishedDate.after($history.lastPubDate)</downloadcondition>
      <destinationfile>$entry.title$ext</destinationfile>      
    </global-feed>
  </settings> 
  <feeds>
   <!-- set url feed -->
   <feed url="http://www.abc.net.au/queensland/conversations/conversationspodcast.xml" />
  </feeds>
</firenze-config>

```