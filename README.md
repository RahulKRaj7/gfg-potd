## GFG Problem Of The Day

### Today - 23 December 2023
### Que - Count More than n/k Occurrences
The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/count-element-occurences/1)

![](https://badgen.net/badge/Level/Easy/green)

### My Approach
To solve this problem, I use a `map` to store the frequency of each element. I then iterate through the map and count the elements that occur more than `n/k` times.

### Time and Auxiliary Space Complexity

- **Time Complexity** : O(n), where n is the size of the array.
- **Auxiliary Space Complexity** : O(n), for the map.

### Code (C++)
```cpp
class Solution
{
    public:
    int countOccurence(int arr[], int n, int k) {
        map<int,int> mp;
        int minCnt = n/k;
        for(int i = 0 ; i < n; ++i)
            ++mp[arr[i]];
        
        int out = 0;
        for(auto i: mp)
            if(i.second > minCnt)
                ++out;
                
        return out;
    }
};
```
### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.

![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
![](https://hit.yhype.me/github/profile?user_id=79409258)

