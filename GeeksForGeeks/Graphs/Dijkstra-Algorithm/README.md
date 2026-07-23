<div align="center">

# 🟢 Dijkstra Algorithm

![GeeksForGeeks](https://img.shields.io/badge/GeeksForGeeks-2F8D46?style=flat-square) ![Graphs](https://img.shields.io/badge/Graphs-6c63ff?style=flat-square) ![N/A](https://img.shields.io/badge/N%2FA-8a8a8a?style=flat-square) ![class solution {
    class graph implements comparable<graph>{
        int node;
        int dis;
        graph(int node, int dis){
            this.node = node;
            this.dis = dis;
        }
        public int compareto(graph o){
            return this.dis < o.dis ? -1 : this.dis > o.dis ? 1 : this.node - o.node;
        }
    }
    
    
    public int[] dijkstra(int v, int[][] edges, int src) {
        // code here
        int dis[] = new int[v];
        arrays.fill(dis, integer.max_value);
        
        list<list<graph>> adj = new arraylist<>();
        for(int i = 0; i < v; i++)adj.add(new arraylist<>());
        
        for(int edg[]: edges){
            adj.get(edg[0]).add(new graph(edg[1], edg[2]));
            adj.get(edg[1]).add(new graph(edg[0], edg[2]));
        }
        
        treeset<graph> set = new treeset<>();
        dis[src] = 0;
        set.add(new graph(src, 0));
        
        while(set.size() != 0){
            graph g = set.pollfirst();
            int node = g.node;
            int dist = g.dis;
            
            for(graph nbn: adj.get(node)){
            
                int newdis = nbn.dis + dist;
                if(dis[nbn.node] > newdis){
                    dis[nbn.node] = newdis;
                    set.add(new graph(nbn.node, newdis));
                }
            }
        }
        
        return dis;
    }
}](https://img.shields.io/badge/class_solution_%7B%0A____class_graph_implements_comparable%3Cgraph%3E%7B%0A________int_node%3B%0A________int_dis%3B%0A________graph(int_node%2C_int_dis)%7B%0A____________this.node_%3D_node%3B%0A____________this.dis_%3D_dis%3B%0A________%7D%0A________public_int_compareto(graph_o)%7B%0A____________return_this.dis_%3C_o.dis_%3F_--1_%3A_this.dis_%3E_o.dis_%3F_1_%3A_this.node_--_o.node%3B%0A________%7D%0A____%7D%0A____%0A____%0A____public_int%5B%5D_dijkstra(int_v%2C_int%5B%5D%5B%5D_edges%2C_int_src)_%7B%0A________%2F%2F_code_here%0A________int_dis%5B%5D_%3D_new_int%5Bv%5D%3B%0A________arrays.fill(dis%2C_integer.max_value)%3B%0A________%0A________list%3Clist%3Cgraph%3E%3E_adj_%3D_new_arraylist%3C%3E()%3B%0A________for(int_i_%3D_0%3B_i_%3C_v%3B_i%2B%2B)adj.add(new_arraylist%3C%3E())%3B%0A________%0A________for(int_edg%5B%5D%3A_edges)%7B%0A____________adj.get(edg%5B0%5D).add(new_graph(edg%5B1%5D%2C_edg%5B2%5D))%3B%0A____________adj.get(edg%5B1%5D).add(new_graph(edg%5B0%5D%2C_edg%5B2%5D))%3B%0A________%7D%0A________%0A________treeset%3Cgraph%3E_set_%3D_new_treeset%3C%3E()%3B%0A________dis%5Bsrc%5D_%3D_0%3B%0A________set.add(new_graph(src%2C_0))%3B%0A________%0A________while(set.size()_!%3D_0)%7B%0A____________graph_g_%3D_set.pollfirst()%3B%0A____________int_node_%3D_g.node%3B%0A____________int_dist_%3D_g.dis%3B%0A____________%0A____________for(graph_nbn%3A_adj.get(node))%7B%0A____________%0A________________int_newdis_%3D_nbn.dis_%2B_dist%3B%0A________________if(dis%5Bnbn.node%5D_%3E_newdis)%7B%0A____________________dis%5Bnbn.node%5D_%3D_newdis%3B%0A____________________set.add(new_graph(nbn.node%2C_newdis))%3B%0A________________%7D%0A____________%7D%0A________%7D%0A________%0A________return_dis%3B%0A____%7D%0A%7D-0f9d58?style=flat-square)

[![Problem Link](https://img.shields.io/badge/Open%20Problem-grey?style=flat&logo=link)](https://www.geeksforgeeks.org/problems/implementing-dijkstra-set-1-adjacency-matrix/1)

</div>

---

## 📋 Problem Statement

Given an undirected, weighted graph with V vertices numbered from 0 to V-1 and E edges, represented by 2d array edges[][], where edges[i]=[u, v, w] represents the edge between the nodes u and v having w edge weight.
You have to find the shortest distance of all the vertices from the source vertex src, and return an array of integers where the ith element denotes the shortest distance between ith node and source vertex src.

Note: The Graph is connected and doesn't contain any negative weight edge.
It is guaranteed that all the shortest distance will fit in a 32-bit integer.

Examples:

Input: V = 3, edges[][] = [[0, 1, 1], [1, 2, 3], [0, 2, 6]], src = 2
Output: [4, 3, 0]
Explanation:

Shortest Paths:
For 2 to 0 minimum distance will be 4. By following path 2 -> 1 -> 0
For 2 to 1 minimum distance will be 3. By following path 2 -> 1
For 2 to 2 minimum distance will be 0. By following path 2 -> 2

Input: V = 5, edges[][] = [[0, 1, 4], [0, 2, 8], [1, 4, 6], [2, 3, 2], [3, 4, 10]], src = 0
Output: [0, 4, 8, 10, 10]
Explanation: 

Shortest Paths: 
For 0 to 1 minimum distance will be 4. By following path 0 -> 1
For 0 to 2 minimum distance will be 8. By following path 0 -> 2
For 0 to 3 minimum distance will be 10. By following path 0 -> 2 -> 3 
For 0 to 4 minimum distance will be 10. By following path 0 -> 1 -> 4
Constraints:
1 ≤ V ≤ 106
1 ≤ E = edges.size() ≤ 106
0 ≤ edges[i][0], edges[i][1] ≤ V-1
0 ≤ edges[i][2] ≤ 104
0 ≤ src < V



**Constraints:
1 ≤ V ≤ 106
1 ≤ E = edges.size() ≤ 106
0 ≤ edges[i][0], edges[i][1] ≤ V-1
0 ≤ edges[i][2] ≤ 104
0 ≤ src < V
Try more examples
Expected Complexities
Company Tags
FlipkartMicrosoft
Topic Tags
Related Interview Experiences
Related Articles
Report An Issue
If you are facing any issue on this page. Please let us know.
C++ (17)
Start Timer
1
2
3
4
5
6
7
class Solution {
  public:
    vector<int> dijkstra(int V, vector<vector<int>> &edges, int src) {
        // Code here
        
    }
};
Custom InputCompile & RunSubmit**

---

## 🤖 AI Topic Classification

| Field | Value |
|-------|-------|
| **Topic** | Graphs |
| **Confidence** | High |
| **Reasoning** | The problem involves finding shortest distances in a weighted graph, which is a classic graph problem. |
| **Native Tags** | — |

---

## 💡 Approach — Dijkstra's Algorithm with Priority Queue

> 🧠 *Generated by UniCode AI*

**Key Insight:** The code implements Dijkstra's algorithm using a priority queue to efficiently select the node with the minimum distance, and updates the distances of its neighbors.

### Algorithm Walkthrough

1. The code initializes an array `dis` to store the minimum distances from the source node to all other nodes, and sets all distances to `Integer.MAX_VALUE`.
2. It creates an adjacency list `adj` to represent the graph, and populates it with edges from the input `edges` array.
3. The code then uses a priority queue `set` to select the node with the minimum distance, and iteratively updates the distances of its neighbors until all nodes have been processed.

### Complexity Analysis

| | Complexity | Notes |
|--|------------|-------|
| ⏱️ **Time** | `O(E + V log V)` | The time complexity is dominated by the priority queue operations (insertion and extraction), which take O(log V) time each, and the number of edges and nodes (E + V). The space complexity is O(V + E) due to the adjacency list and priority queue. |
| 🗄️ **Space** | `O(V + E)` | |

---

## ✅ Accepted Solution 

```class solution {
    class graph implements comparable<graph>{
        int node;
        int dis;
        graph(int node, int dis){
            this.node = node;
            this.dis = dis;
        }
        public int compareto(graph o){
            return this.dis < o.dis ? -1 : this.dis > o.dis ? 1 : this.node - o.node;
        }
    }
    
    
    public int[] dijkstra(int v, int[][] edges, int src) {
        // code here
        int dis[] = new int[v];
        arrays.fill(dis, integer.max_value);
        
        list<list<graph>> adj = new arraylist<>();
        for(int i = 0; i < v; i++)adj.add(new arraylist<>());
        
        for(int edg[]: edges){
            adj.get(edg[0]).add(new graph(edg[1], edg[2]));
            adj.get(edg[1]).add(new graph(edg[0], edg[2]));
        }
        
        treeset<graph> set = new treeset<>();
        dis[src] = 0;
        set.add(new graph(src, 0));
        
        while(set.size() != 0){
            graph g = set.pollfirst();
            int node = g.node;
            int dist = g.dis;
            
            for(graph nbn: adj.get(node)){
            
                int newdis = nbn.dis + dist;
                if(dis[nbn.node] > newdis){
                    dis[nbn.node] = newdis;
                    set.add(new graph(nbn.node, newdis));
                }
            }
        }
        
        return dis;
    }
}
class Solution {
  public:
    vector<int> dijkstra(int V, vector<vector<int>> &edges, int src) {
        // Code here
        
    }
};
```

<div align="center">

*Submitted: Jul 23, 2026, 04:17 PM · Platform: GeeksForGeeks · Auto-archived by [UniCode](https://github.com/UniCode-ext/unicode)*

</div>
