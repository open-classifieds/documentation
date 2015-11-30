---
title:  PayPal email for sellers
date:   2015-06-26 16:23:51
categories: Custom Fields
tags: [Custom Fields]
permalink: /paypal-email-for-sellers/
---
<div class="alert alert-warning">
<strong><i class="glyphicon glyphicon-warning-sign"></i> </strong> This feature is available on our 2.5.0 release.
</div>

Open Classifieds allows your users to accept PayPal payments from their ads. For that, the user's email is used as PayPal email address. 

The news is that you have the option to specify the PayPal email address for sellers. There are two ways to do that:

1. [Add an extra field]({{ site.baseurl }}/how-to-create-custom-fields) on the Publish New form.
2. [Add an extra field]({{ site.baseurl }}/users-custom-fields) on the Users Registration form.

### How it works

- If you don't use any of the above ways, then user's email will be used as PayPal email address.
- If you add an extra field on the Publish New form, this email address will be used as PayPal email address.
- If you add an extra field on the Users Registration form, this email address will be used as PayPal email address.
- If you use both ways, then email address on Publish New will be used as PayPal email address.

### Add an extra field on the Publish New form.

**Steps:**

1. Go on Panel, **Users** -> **Custom Fields**, click on **New Field**
2. (Important!) On the field _Name_ enter **paypalaccount**.
3. Fill the other fields.
4. Click **Create**.

Remember, it's very important to name this field **paypalaccount**!

Now, when users are publishing a new ad, they will see this new field to enter the PayPal email address that will be used to get paid from this ad.

### Add an extra field on the users registration form.

**Steps:**

1. Go on Panel, **Settings** -> **Custom Fields**, click on **New Field**
2. (Important!) On the field _Name_ enter **paypalaccount**.
3. Fill the other fields.
4. Click **Create**.

Remember, it's very important to name this field **paypalaccount**!

On the user registration form, users will see this new field to enter their PayPal email address that will be used to get paid from their ads.

![paypalemail](http://docs.yclas.com/images/paypalemail.png)

<br>
**Related posts:**

+ [How to publish an ad with a different contact email?]({{ site.baseurl }}/how-to-publish-different-contact-email)
+ [How to use shipping custom field]({{ site.baseurl }}/use-shipping-custom-field)