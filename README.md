## GFG Problem Of The Day

### 🎉 Announcement
I have created a Git Book that contains all previous editorials for my GFG-POTD solutions. You can visit **[here](https://gl01.gitbook.io/gfg-editorials/)** to access it and refer to my previous solutions. In the future, I intend to establish a contribution flow, where others can contribute their solutions to this Git Book. I would appreciate hearing your thoughts and views on this in the [discussion section](https://github.com/getlost01/gfg-potd/discussions).

----
### Today - 31 July 2023
### Que - BFS of graph

The problem can be found at the following link: [Question Link](https://practice.geeksforgeeks.org/problems/bfs-traversal-of-graph/1)

### My Approach

In this problem, we are performing a Breadth-First Search (BFS) on a graph represented using an adjacency list. The algorithm starts from a given root node (node 0 in this case) and visits all the nodes reachable from it in a level-by-level manner.

- Initialize an empty queue `q` to store the nodes during BFS traversal.
- Create a boolean array `vis` of size `V` (the number of vertices) to keep track of visited nodes. Initialize all elements of `vis` to false, as no node has been visited yet.
- Mark the source node (node 0) as visited and enqueue it into the queue `q`.
- While the queue is not empty, repeat the following steps:
   - Dequeue a node `front` from the queue and add it to the output vector `out`.
   - Explore all adjacent nodes of `front` that have not been visited yet. Mark them as visited and enqueue them into the queue.

### Time and Auxiliary Space Complexity

- **Time Complexity**: The BFS algorithm visits each node and each edge exactly once, so the time complexity is `O(V + E)`, where `V` is the number of vertices and `E` is the number of edges in the graph.
- **Auxiliary Space Complexity**: `O(V)` since we use additional space to store the boolean array `vis` and the output vector `out`.

### Code (C++)

```cpp
class Solution {
public:
    vector<int> bfsOfGraph(int V, vector<int> adj[]) {
        queue<int> q;
        vector<int> out;
        vector<bool> vis(V, false);
        vis[0] = true;
        q.push(0);

        while (!q.empty()) {
            int front = q.front();
            q.pop();
            out.push_back(front);

            for (auto node : adj[front]) {
                if (!vis[node]) {
                    vis[node] = true;
                    q.push(node);
                }
            }
        }

        return out;
    }
};
```
### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.


![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
