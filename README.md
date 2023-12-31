# Hashmapper
### Course: ECE297
### Developers: Kenny Cui, Eric Chen, Justin Pang
##### Notable Components: Dijkstra's algorithm, Iterative 2-opt Algorithm, User Interface Design, API Integration, Travelling Salesman Problem 

##### Hashmapper is a mapping software created by a team of three Computer Engineering students. All code was developed in C++ and heavily utilized the C++ Standard Library (STL). Map data is obtained from an OpenStreetMap API provided by the course. 
![](general.png)
##### Note: This repository is only meant to be a showcase of hashmapper, it does not contain any code because we are disallowed from posting it since ECE297 uses the same project every year. For future ECE297 students, feel free to take inspiration from our design choices and features!

# Features

## Main Features

### Searchbar & Autocomplete

![](autocomplete.gif)

##### The main searchbar at the top is used to search streets or intersections. The search system shows autocompleted results for partial string inputs. After hitting enter, the map instantly rezooms to show the desired street/intersection.

##### This feature was implemented by storing street name prefixes (the first three characters of the street name) in a std::map. Up to 7 results are shown for partial searches that match with the prefixes in the std::map. This efficient structure enabled updated autocomplete results after every additional letter typed.

##### The software uses the '&' character to distinguish between searching intersections vs streets

|  | Search format | Example |
| -------- | -------- | -------- |
| Street | "<STREET_NAME\>" | "College Street" |
| Intersection | "<STREET_NAME_1> & <STREET_NAME_2>" | "Bay & Yonge" |

### Navigation Mode

![](directions_path.gif)

##### When navigation mode is activated, the user can click on two locations on the map. The software then uses Dijkstra's algorithm to find the shortest path between them, taking into account legality, speed limit, and turns. The path is then rendered into readable instructions on the popup screen. The geographic data fed into the algorithm is obtained via the OpenStreetMap API.

### Travelling Salesman Problem (NP Hard)

<img src="2-opt.gif" width="700px" height="550px">

##### We tackled the Travelling Salesman Problem using an iterative 2-opt algorithm as well as a multi-destination Dijkstra's algorithm. The quality of our solution was measured via test-cases provided by the ECE297 teaching team. Our team ranked in the top 20 percentile in a class of ~300 students. 

### Zoom/Detail Level

![](zoom_levels.gif)
![](zoomed_out.png)

### Points of Interests Menu

![](points_of_interests_1.png)
![](points_of_interests_2.png)

## Extra Features
### Dark Mode

![](dark_mode.png)

### Local Weather

![](weather.png)
