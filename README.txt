Street Maping Project

Synposis:

This project is a rudimentary mapping java program that reads the given formatted data of intersections and roads in a specific geographic region. This program uses the given data set to plot a map of the data, provide the shortest path directions between any random intersections using Dijkstra's algorithm, and calculate the minimum weight spanning tree for the whole map. The final graph representation used is a HashMap of Strings to LinkedLists,  where the Strings are IntersectionIDs and the LinkedList have a node Head, that stores the Intersection object, and a pointer to an Edge, which stores a Road that the intersection is a part of. To display the entire Graph, every Road is added to an ArrayList of Roads and a 2D line is painted with the same endpoints as the road.


List of all files submitted:
1. Intersection.java
 Intersection objects have an IntersectionID, a Longitude and Latitude, are either known or unknown, and a distance and a path (for Dijkstra's).

2. LinkedList.java
 This contains a constructor and helper methods for inserting a new Intersection into the List, for inserting an Edge into the List, and for 
 calculating the cost between the Intersection in the head of the list and an intersection it connects to.

3. Map.java
 This contains the constructor for the Map, and methods to insert Intersections and Edges. It also contains menthods that calculate the 
 minimum weight spanning tree and the shortest path between two intersections. 

4. MapGUI.java
 This has the constructor and a paint method, that paints all the roads in the Graph. When asked by the user, it also paints the shortest path 
 between two intersections and the minimum weight spanning tree in the Graph

5. Node.java
 This is used for the head of all the LinkedLists. Node objects have an Intersection and a pointer to an Edge.

6. Road.java
 This contains the constructor for the Road. Road objects have a RoadID, and the IDs for the intersections if connects.

7. Edge.java
 Edges have a Road and a pointer to the next Edge, and Edges.java is used for everything but the head of LinkedLists.

8. Main.java
 This contains the main method that reads from file the data on the intersections and roads. After that, the command line arguments are read, 
 and the user can make their specifications.

9. nys.txt
 This contains the formatted data for New York State and was provided in the assignment.

10. monroe.txt
 This contains the formatted data for Monroe County and was provided in the assignment.

11. ur.txt
This contains the formatted data for University of Rochester's campus and was provided in the assignment.

12. OUTPUT.txt
 This contains contact informations, and the compile and run steps of my code.

13. README.txt
 This is this file.

Notable obstacles:
A major obstactle I faced was Dijkstra's and Kruskal's Algorithm runtime because at first was trying to iterate through all the 
remaining unknown intersections to search for the smallest intersection, but then I used a priorityQueue which was much faster.

Runtime analysis:
I think the runtime for displaying the Graph is O(N) where N is the number of roads in the Graph. This is because all the roads are added 
to an ArrayList of Roads. In addition, other calculations such as finding the maximum and minimum longitude and latitude can be ignored 
because they have constant time which is why I believe the runtime for displaying the Graph is O(n).

I believe the runtime for calculating the shortest path between two intersections is the total runtime for Dijkstra's algorithm which 
is O(E*|N|), where E is the number of intersections in the Graph and |N| is the average number of Edges in each Linked List. Also, the runtime of 
the shortest path is O(N) where N is the number of intersections that make up the path. 

The runtime for calculating the minimum weight spanning tree is the runtime for Kruskal's algorithm is O(N) where N is the number of Roads in the graph, 
because every Road is checked in my implementation of the algorithm. Also, the runtime for displaying the minimum weight spanning tree is the runtime
for displaying the Meridian map which is O(N) where E is all the roads in the tree.

So, as the data size increases, I believe the overall runtime of the entire program will grow linearly. This is becayse none of the calculations have a 
slower or quadratic runtime.



