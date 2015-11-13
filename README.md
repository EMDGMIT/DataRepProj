# DataRepProj
## Data Representation and Querying Project 2015
### Éanna MacDonough

## Introduction
This project provides the design and documentation for the dataset "Playgrounds County Galway" which is available at [data.gov.ie/dataset/playgrounds-county-galway](https://data.gov.ie/dataset/playgrounds-county-galway). Although the data is only based on information known by Galway County Council, I have suggested to data.gov.ie to upload datasets of all playgrounds known by Galway City Council.

The type of users I'd imagine using the app are parents of children aged 18 months - 12 years old living in Galway who want to find playgrounds (either a specific one or multiple) for their child / children to play at, either locally or while away from home.

### About the data

This dataset was received in Comma Separated Values (CSV) format, and was downloaded from https://data.gov.ie/dataset/playgrounds-county-galway

The CSV file contains 63 rows, the first being a header row with the names of each column. There are sixteen values on each line, which are as follows:

| Field       | Description                                                 |
| ----------- |:-----------------------------------------------------------:|
| X           | UTM x coodrinate?                                           |
| Y           | UTM y coodrinate?                                           |
| FID         | Unique ID of the row, Primary Key                           |
| ID          | Similar to FID, between FID 34 - 57, ID + 1                 |
| Location_o  | Location of playground                                      |
| Area_       | Region playground is located (usually most well known town) |
| Managed_By  | Who owns / manages the playground                           |
| Playground  | Street name of playground                                   |
| AGE_GROUP   | Age range of playground                                     |
| List_of_Eq  | All playground equipment at said playground                 |
| Liosta_Eq   | All playground equipment at said playground in Irish        |
| List_of_00  | Specific playground equipment                               |
| PUBLIC_TOI  | Public toilets at playground                                |
| OPENING_HO  | Times in which playground is open                           |
| PARKING     | Available parking near playground                           |
| PHOTO       | JPG of playground                                           |

## List of Playgrounds
You can get a list of playgroundss in Galway using the GET method at the following URL:
*http://GalwayPlaygrounds.ie/location*

The data will be returned in JSON format, with the following properties for each Tennis Court:

| Field         | Description                                                 |
| ------------- |:-----------------------------------------------------------:|
| Location      | Location of the playground                                  |
   
An example of a response would be:
```JSON
[ {"Location": "Maam", 
   "Location": "Mountbellew",
   "Location": "An Cheatrú Rua",
   "Location": "Tuam (Palace Grounds)"}]
```

You can also get a list of playgroundss in Galway using the GET method at the following URL:
*http://GalwayPlaygrounds.ie/area*

The data will be returned in JSON format, with the following properties for each playground:

| Field         | Description                                                 |
| ------------- |:-----------------------------------------------------------:|
| Area          | Region playground is located                                |
   
An example of a response would be:
```JSON
[ {"Location": "West Galway" / "Conamara", 
   "Location": "East Galway" / "Ballinasloe",
   "Location": "Central Galway" / "Oranmore" / "Athenry",
   "Location": "Corofin"}]
```

## Displaying a specific Playground by Location
You can get data on a specific Playground using a GET method at the following URL:
*http://GalwayPlaygrounds.ie/playground/[location]*
where you replace [location] with the location name of the playground. This is very usefull for people who already know the name of the location but not the coordinates.

Where there is a space and *underscore (_)* is needed.

For example, the URL:
*http://GalwayPlaygrounds.ie/playground/An_Caiseal*
will display the data of the playground in Cashel.
The data will be returned in JSON format, with the following properties for each playground:

| Field      | Description                |
| ---------- |:--------------------------:|
| Location   | An Caiseal                 |
| X          | -1093053                   |
| Y          | 7060998                    |
| Area       | West Galway - Conamara     |
| Playground | The Fair Green, Cashel     |
| Age Group  | 2 - 17 Years               |
| Equipment  | Spring Bowl, Spring Bike, Climber and Slide, Basket Swing and Multi Use Games Goal |

An example of a response would be:
```JSON
[ {"Location": "An Cloigeann",
   "X": -1124629,
   "Y": 7085963,
   "Area": "West Galway - Conamara",
   "Playground": "Cleggan",
   "Age Group": "All",
   "Equipment": "Spring Rocker, 4 Seat Springer, Slide, Spinning Bowl and Basket Swing"}]
```

## Adding new Playgrounds to the Dataset
With the expansion of Galway City and its many surrounding towns and villages, it is very possible that new playgrounds could be built. Because of this we need to make it possible to be able to add new playgrounds to the Dataset. We do this using the POST method.

The POST methods URL would be something similar to:
*http://GalwayPlaygrounds.ie/addPlayground*

An example of the HTTP POST method message:
```HTTP
POST /GalwayPlaygrounds/addPlayground HTTP/1.1
Host: GalwayPlaygrounds.ie
x="-1030040"&y="7054112"&fid="64"&id="64"&location_o="Roscahill"&area_="West_Galway_-_Conamara"&managed_by="Galway_City_Council"&playground="Kilannin_Pitch,_Roscahill"&age_group="1-12_Years"&list_of_eq="Slide,_Spinning_Bowl,_Spring_Seesaw,_Flat_Swings,_Playhouse"&public_toi="Yes"&opening_ho="Daylight_Hours"&parking="YES"
```

## Deleting a Playground from the Dataset
Just like how a playground can be built, they can be knocked down and because of this we should be able to delete playgrounds from the dataset.

With use of the FID and the DELETE method in the URL a tennis court can easily be removed from the dataset

Such a URL would be:
*http://GalwayPlaygrounds.ie/delete/[FID=#]*

(where # is the FID number)

60 - (OK)
64 - (Accepted)
65 - (No Content)

```HTTP
POST /GalwayPlaygrounds/addPlayground HTTP/1.1 64
Host: GalwayPlaygrounds.ie
"Playground Removed"
```

##An example of a URL that would include city####

```markdown
*http://GalwayPlaygrounds.com/[county]/[town/city]/[area]*
For example, the URL:
*http://GalwayPlaygrounds.com/Galway/Galway/Renmore*
will return a list of playgrounds located in Renmore.
```

