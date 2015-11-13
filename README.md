# DataRepProj
## Data Representation and Querying Project 2015
### Éanna MacDonough

## Introduction
This project provides the design and documentation for the dataset "Playgrounds County Galway" which is available at [data.gov.ie/dataset/playgrounds-county-galway](https://data.gov.ie/dataset/playgrounds-county-galway). Although the data is only based on information known by Galway County Council, I have suggested to data.gov.ie to upload datasets of all playgrounds known by Galway City Council.

The type of users I'd imagine using the app are parents of children aged 18 months - 12 years old living in Galway who want to find playgrounds (either a specific one or multiple) for their child / children to play at, either locally or while away from home.

### About the data

This dataset was received in Comma Separated Values (CSV) format, and was downloaded from https://data.gov.ie/dataset/playgrounds-county-galway

The CSV file contains 63 rows, the first being a header row with the names of each column. There are sixteen values on each line, which are as follows:

>    * X: UTM x coodrinate?
>    * Y: UTM y coodrinate?
>    * FID: the id of the row //primary key?
>    * ID: similar to FID, between FID 34 - 57, ID + 1
>    * location_o: location of playground, all addresses in Conamara in Irish, others in English with Irish in brackets
>    * Area_: general area playground is located, usually most well known town
>    * Managed_By: who owns / manages the playground
>    * Playground: another adddress of playground, sometimes street name
>    * AGE_GROUP: int, range 0 - 99
>    * List_of_Eq: all playground equipment at said playground
>    * Liosta_Eq: all playground equipment at said playground in Irish
>    * List_of_00: specific playground equipment? (Fields listed as yes, none specified, or certain playground equipment)
>    * PUBLIC_TOI: public toilets at playground, true/false
>    * OPENING_HO: times in which playground is open
>    * PARKING: true/false
>    * PHOTO: JPG of playground

##Design Idea##

The app should be user friendly, therefore I am thinking of using only 2 windows. 

###MENU###

Below is a link to a png file of a template I designed:
https://cloud.githubusercontent.com/assets/8780936/10644662/c16f5df0-7821-11e5-9c0c-a085f82fa7a1.png

The app should open straight to the menu, where you have 2 options:
> #####Area######
 
This would consist of a drop down list where you choose what area you are in.
 
> ######Materials#####

This would consist of a drop down list where you choose what materials you want to recycle.

###RESULT###

Below is a link to a png file of a template I designed
https://cloud.githubusercontent.com/assets/8780936/10644566/494ae54c-7821-11e5-8d50-8372affcca19.png

This page will consist of the data including:

>    * Area (String)
>    * Location (String)
>    * Glass: True/False
>    * Cans: True/False
>    * Textiles: True/False

#####MAP#####

The App could also have a map considering that there are co-ordinates in the 'Latitude' and 'Longtitude' column's

###URL's###

####List of bring banks in a given area####
This will give a list of the bring banks in a given area. it will also show what materials the bring bank accepts

```markdown
*http://bringbanks.com/area/[area]*
where you replace [area] with the location.
For example, the URL:
*http://bringbanks.com/area/swords*
will return a list of bring banks located in swords.
```

####List of bring banks that accept glass####
This will give a list of the bring banks that accept glass. It will also show what other matreials are and their locations.

```markdown
*http://bringbanks.com/glass/[glass]*
where you replace [glass] with the glass.
For example, the URL:
*http://bringbanks.com/glass*
will return a list of bring banks that accept glass.
```

####List of bring banks that accept cans####
This will give a list of the bring banks that accept cans. It will also show what other matreials are accepted and their locations.

```markdown
*http://bringbanks.com/cans/[cans]*
where you replace [cans] with the cans.
For example, the URL:
*http://bringbanks.com/cans*
will return a list of bring banks that accept cans.
```

####List of bring banks that accept textiles####
This will give a list of the bring banks that accept textiles. It will also show what other matreials are accepted and their locations.

```markdown
*http://bringbanks.com/textiles/[textiles]*
where you replace [textiles] with the textiles.
For example, the URL:
*http://bringbanks.com/textiles*
will return a list of bring banks that accept textiles.
```

####List of bring banks in a given area that accept glass####
This will give a list of the bring banks in a given area that take glass. It will also show what other matreials are accepted and their locations

```markdown
*http://bringbanks.com/area-glass/[area]glass*
where you replace [area] with the area.
For example, the URL:
*http://bringbanks.com/location-glass/swords-glass*
will return a list of bring banks located in swords that accept glass.
```

####List of bring banks in a given area that accept cans####
This will give a list of the bring banks in a given area that take cans. It will also show what other matreials are accepted and their locations

```markdown
*http://bringbanks.com/area-cans/[area]-cans*
where you replace [area] with the area.
For example, the URL:
*http://bringbanks.com/area-cans/swords-cans*
will return a list of bring banks located in swords that accept cans.
```

####List of bring banks in a given area that accept textiles####
This will give a list of the bring banks in a given area that take textiles. It will also show what other matreials are accepted and their locations

```markdown
*http://bringbanks.com/area-textiltes/[area]-textiltes*
where you replace [area] with the area.
For example, the URL:
*http://bringbanks.com/area-textiles/swords-textiles*
will return a list of bring banks located in swords that accept textiles.
```

####An example of a URL that would be country wide####

```markdown
*http://bringbanks.com/[county]/[town/city]/[area]*
For example, the URL:
*http://bringbanks.com/Galway/Galway/Renmore*
will return a list of bring banks located in Renmore.
```


The clip arts I used in the result window, I found at the following website:
> https://openclipart.org/
