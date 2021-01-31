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
### BFS on Graph
```java
```
### DFS on Graph
```java
```
