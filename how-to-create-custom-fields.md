---
title:  "How to create Custom Fields?"
date:   2013-10-13 09:56:58
categories: Custom Fields
tags: [Custom Fields]
permalink: /how-to-create-custom-fields/
---
New feature is included in **2.0.7** version, makes it possible to create multiple new custom fields.

Now there are **3 types of fields**, that could be added to advertisements.

  1\. **Standard**: mandatory and not changeable

              Title, Category, Description.

  2\. **Optional**: they are part of open-classifieds, with possibility to turn them on/off

              Phone, Website, Location, Address, Price, Captcha, Upload file.

  3\. **Custom:** Fully customizable.

 

### Create New Field

To create new, go to **Admin Panel**, press **Appearance** select **Custom Fields** option.

Then click **New Field** button on the right corner.

![How to create Custom Field 1](http://open-classifieds.com/wp-content/uploads/2013/10/How-to-create-Custom-Field-1.png)

This is a **New Custom Field** screen. There are 10 options in total.

1. **Name**: give a name to field
2. **Label**: will appear in the form of Post new ad, Edit ad, and Advanced search
3. **Tooltip**: assign a text to the custom field tooltip
4. **Type**:

   1\. _Text 256 chars_ (standard input field, string)<br>
   2\. _Text Long_ (textarea field with bbcode, string)<br>
   3\. _Number_ (small integer number)<br>
   4\. _Number Decimal_ (floating point number)<br>
   5\. _Select_ (select field)<br>
   6\. _Date_ (date picker, with plugin)<br>
   7\. _Radio_ (radio buttons)<br>
   8\. _Checkbox_ (checkbox buttons)<br>
  
5\. **Values**:

   Note: Only appears for select and radio option.

   To create values,write them down followed by comma (e.g. Paris, London, Madrid, Others).

6\. **Categories:** with which category the New Custom Field should be related

   ( see: [How to Integrate Your Custom Fields Into Selected Categories!]({{ site.baseurl }}/how-to-integrate-your-custom-fields-into-selected-categories))

7\. **Required**: this will mark field as required, and validation will be applied

8\. **Searchable**: make field searchable, it will appear in Advanced search

9\. **Admin privileged**: this field can be seen and edited only by admin

10\. **Show listing**: Users will see the custom field in listings view without having to enter the ad 

When all info is filled, click **Create**. New field is created and added to database, and it will appear in Post new ad, Edit ad and Advanced search.

To **Edit**, **Delete** or **Change order** look at the following image.

![How to create Custom Field 2](http://open-classifieds.com/wp-content/uploads/2013/10/How-to-create-Custom-Field-2.png)

### Edit Custom Field

While editing, **Name** and **Type** **fields** will become disabled. In case you want to change them, you will have to delete this custom field and start over. This is to prevent messing up with DataBase.

Just to your information, the rest of options are still open for editing and adding.

![How to create Custom Field 3](http://open-classifieds.com/wp-content/uploads/2013/10/How-to-create-Custom-Field-3.png)

