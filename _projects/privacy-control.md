---
layout: project
title: Privacy Control
meta: A simple dashboard that provides privacy settings for multiple online social networks (OSN) and recommends the best possible configuration. 
category: project
image: pc-cover.jpg
---

Privacy Control is a simple dashboard which combines all the privacy settings of multiple social network (Facebook, Twitter). It provides the user with best possible privacy settings for their accounts.

Users share more than they expected, this disparity is known as “privacy paradox”. Liu et al. studied this and found that only 37% of the time users’ privacy settings match users’ expectation.

The definition of privacy is different for everyone and the person defines whether to disclose or not on the basis of context and environment.

**Features** -  

*   Recommend settings to protect users' privacy on OSN
*   Give privacy score to previous settings
*   One click privacy - set recommended settings to multiple social networks on one click
*   Reduce all the 45+ settings on Facebook on twitter to just **18 settings**

{% include figure.html src='pc-steps.jpg' caption='Privacy control walkthrough' %}

**Architecture -**  
The main challenge in the implementation was that the social networks don’t provide any easy way to alter users’ settings through API calls.  
So, the only possible solution that left was to open the page manually and alter the DOM element. To achieve this we developed a chrome extension and extensively used its functions for manipulating the tabs.

*   Check logged in user using adblockplus.js
*   Open the social network’s settings page
*   XMLHttpRequest to get the page
*   Secure the account from page
*   Extract the page headers
*   Edit the settings on the page to the submitted ones
*   Send AJAX post request along with

*   Extracted headers
*   New settings

#### Results -

The benefit of using this utility is -

{% include figure.html src='pc-result.jpg' caption='Savings' %}


**How?**  
There are 27 settings (16 Facebook and 11 Twitter) that our app recommends to the user. Suppose it takes 11 minutes and 15 seconds to properly understand and tweak these privacy settings.  
Using our extension it merely takes 15 seconds to change settings. Saving 11 minutes per user.  
Now, assuming 10,000 new users use our application daily. Average Indian wage per hour is Rs 40.  
This is how we will be able to save Rs 74,000 per day.

#### Gallery

{% include figure2.html src='pc-playvideo.jpg' link='https://www.youtube.com/watch?v=Bco0eqDKH5g' linktitle='Play privacy control teaser' caption='Click to play video' %}
{% include figure.html src='pc-chrome-ext.jpg' caption='Privacy Control Chrome extension' %}
{% include figure.html src='pc-dashboard.jpg' caption='Dashboard' %}
{% include figure.html src='pc-fb-settings.jpg' caption='Facebook settings' %}