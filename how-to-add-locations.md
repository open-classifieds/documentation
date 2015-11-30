---
title:  "How to add locations?"
date:   2013-08-22 07:00:53
categories: Classifieds
tags: [Classifieds]
permalink: /how-to-add-locations/
---
**Locations** make possible to segregate ads appearing in your classifieds by the place/city. Thanks to this users of the site can narrow their search only for the ads around their geographical territory.

<div class="alert alert-warning">
<strong><i class="glyphicon glyphicon-warning-sign"></i> Warning:</strong> We do not recommend adding more than 1000 locations if you use shared hosting. Otherwise, your website will work very slow.
</div>

## How to add locations

### Geonames

![How to add locations 1]({{site.baseurl}}images/locations-geonames.png)

This is probably the easiest and fastest way to add multiple locations. What you have to do is to choose a location (Continent, Country, State/Province, County/Region or City) and press **Import** to import its sub-locations. <br>
For example, if you choose:<br>
Continent = Europe<br>
Country = Spain<br>
State/Province = Catalonia<br>
and then click Import, it will add Barcelona, Girona, Lleidia and Tarragona to your locations. 

Then, you can add the sub-locations of a location. <br>
If you have added Barcelona in your locations, click **Browse** on the right of this location. <br>
Then choose:<br>
Continent = Europe<br>
Country = Spain<br>
State/Province = Catalonia<br>
County/Region = Barcelona<br>
and click Import to add all the sub-locations of Barcelona.

### Quick method

At the quick location creator add the name of the location, hit **enter** on your keyboard and when you have done, press the '**Send**' button as explained in the following screenshot. 

![How to add locations 1]({{site.baseurl}}images/locations2.0.4-quick.png)

### Manual method

   1\. Go to **Panel**, choose **Classifieds** > **Locations** on the left sidebar <br>
   2\. Press '**New location**' button<br>
   3\. Fill **in the fields:**

  + **Name:** Choose a name of location that will be displayed, eg. city or city quarter. Basically, this field is the most important, rest is more or less optional.<br>
  + **Order:** You can choose the order locations will be displayed within a parent. It's not obligatory - later you can just use drag & drop to change the order.<br>
  + **Parent:** Choose under which one of existing main locations new location will be displayed. Choose **Home Location** while creating main location. Later locations can be easily moved to other parent.<br>
  + **Seoname:** Seoname will be auto-generated based on the name, but you can also type it if you want it to be different.
  + **Description:** You can add few words about the place.


4\. Press **SUBMIT**

![How to add locations 2]({{site.baseurl}}images/locations2.0.4-new.png)

After submitting you should see the information:

_"Success. Item created. Please to see the changes delete the cache"_.

Continue creating new locations if necessary, **delete cache** after finishing to see the changes. To delete cache go to: **Tools** > **Cache** on the left sidebar and press a button **Delete all**.

New locations now will be available to choose in **Publish New Advertisement** form and visible in **'Locations' widget**.

## How to add sub-locations

With our 2.4.0 release you can add sub-locations fast and easy. All you have to do is to click **Browse** next a location to insert sub-locations in that location.

![How to add locations 2]({{site.baseurl}}images/locations2.0.4-browse.png)

## How to manage locations

Like before: go to **Panel**, choose **Classifieds** > **Locations** on the left sidebar. 

Managing them is very easy. If you want to move locations and change their order you just need to drag and drop selected one to the chosen place.

To change something, e.g. name or description of the location, you can click **Edit** button.

To **delete** press red button with trash bin. Note, that when you delete parent locations inside of it will be moved level up - to the parent of the deleted location.

## Locations widget

Additional options to deal with locations are given by special widget. To activate it, go to **Panel** and choose **Apperance** > **Widgets** on the left sidebar. Choose **'Locations' widget** from the list and click **CREATE**. Name the widget's title and select if you want to display it in a sidebar or footer. You can also keep it **Inactive**. Thanks to this widget navigation between locations is easier. List of them will be displayed all the time at the side or in the bottom of the page.

<br>
**Related posts:**

  * [How to add categories and manage them?]({{ site.baseurl }}/how-to-add-categories)
  * [How to use import tool for categories and locations?]({{ site.baseurl }}/use-import-tool-categories-locations)
  
