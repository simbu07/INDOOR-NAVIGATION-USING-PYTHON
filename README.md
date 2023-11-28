# Indoor-Naviation
Navigation systems are used to help people find their way from one place to another. They can be used in cars, on foot, or even on public transportation. There are many different types of navigation systems, but they all work by using a map to show the user where they are and where they need to go.

Python is a programming language that can be used to create navigation systems. It is a popular choice for this task because it is easy to learn and use. 

There are many different Python libraries that can be used to create navigation systems, such as the Google Maps API and the Open Street Map API.

## Features
Specify user requirements and features, such as turn-by-turn directions, visual guidance, or point-of-interest information.

Creates a graph representation of the indoor environment.

Integration of navigation instructions and real-time information into the UI.

Collects user feedback for future enhancements.

Keeps the system adaptable to changes in the indoor environment.
## Requirements

- Python 3.x
- geojson.io
- Required Python packages: folium,plugins,pandas,ipywidgets, os,json.

  ## Architecture Diagram/Flow

  ![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/fe00faa8-4ac5-4c32-aeb5-f02e619c29e6)

## Program:
```
import folium
from folium import plugins
import pandas as pd

import ipywidgets
import os
import json

UMMlocation = (13.0262, 80.0163)
map_UMM = folium.Map(location = UMMlocation, width = "75%", zoom_start = 18) # max zoom: 18
print("This is Saveetha University located near Thandalam, Chennai.")

map_UMM


hauseOutline = 'clg.geojson'
display(folium.GeoJson(hauseOutline, name="Haus22").add_to(map_UMM))
print(Saveetha Provides Engineering College,Medical College,Deemed University)

display(map_UMM)

hauseOutline = 'Blocks.geojson'
display(folium.GeoJson(hauseOutline, name="Haus22").add_to(map_UMM))
print("SEC Has 4 Entrances")
print("\nFirst one is CSE")
print("\nThe Second one is ADMIN Which is Main Entrance")
print("\nThird one is ECE")
print("\nFirst one is EEE")
display(map_UMM)

testGeoJson = 'path.geojson'
def switchPosition(coordinate):
  temp = coordinate[0]
  coordinate[0] = coordinate[1]
  coordinate[1] = temp
  return coordinate

with open(testGeoJson) as f:
  testWay = json.load(f)

for feature in testWay['features']:
    path = feature['geometry']['coordinates']
finalPath = list(map(switchPosition,path))
finalPath


path = 'path.geojson'
folium.plugins.AntPath([[13.022299943401109, 80.01663484755176],
 [13.023276221536378, 80.0167478993859],
 [13.023406391663912, 80.01669137346693],
 [13.023466470161182, 80.01680442530102],
 [13.024302561068964, 80.01690719969645],
 [13.025380518842056, 80.01706755091124],
 [13.025972933366589, 80.01719052730999],
 [13.0257402587375, 80.01664465340298],
 [13.025933046302782, 80.01654230204633]]).add_to(map_UMM)
print("")
map_UMM

select_widget=ipywidgets.Select(
    options=['CSE', 'ADMIN'],
    value='CSE',
    description='Select',
    disabled=False)

def selectOption(opt):
    if opt == 'CSE':
        print('CSE')
    if opt == 'ADMIN':
        print('ADMIN')



ipywidgets.interact(selectOption, opt=select_widget)


myNavigator = navigator()
def displayWay(whereTo):
     myNavigator.changeDestination(whereTo)

def changePosition(whereFrom):
    myNavigator.changeStartPoint(whereFrom)



# Destination Selector
selectHouse_widget=ipywidgets.Select(

options=['CSE',
    'ADMIN',
    'ECE',
    'EEE',
    'RECEP',
    'BEEE'],
    value='CSE',
    description='Target',
    disabled=False)

# widget function
def selectHouse(way):
    if way == 'CSE' :
        displayWay('CSE' )
    if way == 'ADMIN':
        displayWay('ADMIN')
    if way == 'ECE':
        displayWay('ECE')
    if way == 'EEE':
        displayWay('EEE')
    if way == 'BEEE':
        displayWay('BEEE')
    if way == 'RECEP':
        displayWay('RECEP')



# Position Selector
selectPosition_widget=ipywidgets.Select(
    options=['CSE', 'ADMIN', 'ECE', 'EEE'],
    value='ADMIN',
    description='Start',
    disabled=False)

def selectPosition(position):
    if position == 'CSE':
        changePosition('a')
    if position == 'ADMIN':
        changePosition('w')
    if position == 'ECE':
        changePosition('o')
    if position == 'EEE':
        changePosition('f')

#Initialization
ipywidgets.interact(selectPosition, position=selectPosition_widget)
ipywidgets.interact(selectHouse, way=selectHouse_widget)
```
## OUTPUT:
![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/58bef9b0-e4d0-4935-ab21-9038b40b294a)

![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/0efe2282-b851-437e-b781-a0d47df26a76)

![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/c17e3cef-7a95-440c-a3a9-9174443a9dfe)

![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/dd6ea1ce-5959-49f3-91ff-0089447f6152)

![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/97ddc98a-ccf7-4288-ab2d-6973f3de844e)


![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/d24de7c7-440e-4182-b188-c4d666aca913)


![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/f631211c-201a-4e0e-b8fe-f6d4b8ca7d46)

![image](https://github.com/Shobika187/Indoor-Naviation/assets/94508142/29b6fd27-c540-4164-8843-563bd3ae5db7)

## Result:
The creation and implementation of an indoor navigation system in Python provide considerable benefits in terms of boosting user experience and efficiency within enclosed environments. 


This project takes advantage of the Python programming language's versatility and ease of use to produce a comprehensive and user-friendly navigation solution.


The system gives precise and real-time navigation information to users via the integration of multiple technologies such as sensors, beacons, and computer vision, allowing them to navigate complicated indoor areas with ease. 
Python enables for efficient data processing, smooth interaction with existing technologies, and the creation of a scalable and adaptive solution.



