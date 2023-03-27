---
permalink: /docs/other.html
layout: default
title: Additional information for page editing
pagetype: doc
---

## Main page :

To edit some of the main page features : 
- All available fields that will de displayed in the main page are included in ```index.html```.
- The title of the main page can be edited in ```_includes/masthead.html```.
- The image used as background in the main page can be changed in ```index.html``` by altering the path set in the ```bgimage``` field. The image should be stored in the directory ```assets/images/```.
- To change the color of the navigation bar and the footer, the color is defined in ```_sass/_variables.scss``` where you should look for ```$uw-color:```.
- To set the navigation bar color, search in ```_sass/_variables.scss``` for :
```
@include gradient-x($navbar-dark-active-color, $uw-color, 0%, 100%);
```
(should be in line 251). To change the color of the footer look in file ``` ``` for line :
```
@include gradient-x($navbar-dark-active-color, $uw-color, 0%, 100%);
```
(should be in line 291 inside the .footer-dark field).


## Overview
To edit overview do to file ```pages/about/overview.md```


## To add new event :
 New events shoould be added in the ```_data/events``` directory. The file should be saved in the format ```YYYYMMDD_name.yml```.
Example of format :
```yml
---

 name: TAC-HEP summer workshop
startdate: 2022-05-23
enddate: 2022-05-25
location: 
meetingurl: 
image:
description: >
  - Placeholder for short description
labels:
  - i.e. training
---
```

