### Adjacency List Implementation using Array of LinkedList
```java
import java.util.*;

public class AdjacencyListGraph {
    //adjacency list is an array of Linked List

    private LinkedList<Integer> adj[];
    private int v;
    public AdjacencyListGraph(int v){
        this.v=v;
        adj=new LinkedList[v];
        for(int i=0;i<v;i++){
            adj[i]=new LinkedList<>();
        }
    }
    public void addEdge(int source, int destination){
        adj[source].add(destination);
        adj[destination].add(source);
    }
    public void printGraph(){
        for (int i = 0; i <v ; i++) {
            if(adj[i].size()>0) {
                System.out.print("Vertex " + i + " is connected to: ");
                for (int j = 0; j < adj[i].size(); j++) {
                    System.out.print(adj[i].get(j) + " ");
                }
                System.out.println();
            }
        }
    }

    public static void main(String args[]){
        Scanner sc=new Scanner(System.in);
        int v=sc.nextInt();
        int e=sc.nextInt();

        AdjacencyListGraph graph=new AdjacencyListGraph(v);

        for(int i=0;i<e;i++){
            int source=sc.nextInt();
            int destination=sc.nextInt();
            graph.addEdge(source, destination);
        }
        graph.printGraph();
    }
}
```
#### Input <br>
5 <br>
6 <br>
0 4 <br>
0 3 <br>
2 1 <br>
1 4 <br>
3 4 <br>
#### Output 
Vertex 0 is connected to: 4 3 <br>
Vertex 1 is connected to: 2 4 <br>
Vertex 2 is connected to: 3 1 <br>
Vertex 3 is connected to: 0 2 4 <br>
Vertex 4 is connected to: 0 1 3 <br>
### BFT on Graph
```java
```
### DFT on Graph
```java
```
### DFT on Graph using backtracking

## Do graph theory from hackerearth


## BFS To do
Question | Topic/Hints | Difficulty
| :--- | ---: | :---:
Given source and destination in a grid with obstacles find shortest path (Dungeon game)
Shortest Path in a Binary Matrix (Leetcode)
No. of islands
No. of distinct islands
Is Graph Bipartite
Restore the array from adjacent pairs
