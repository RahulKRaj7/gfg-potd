# GFG Problem Of The Day

## Today - 23 June 2023
### Que - Task Scheduler

[Question Link](https://practice.geeksforgeeks.org/problems/task-scheduler/1)


### My approach
- Starting with determining the frequency of each task.
- Next, place these tasks frequency into a priority queue.
- Then iterate until all tasks are completed. During each iteration, find the task with the highest frequency from the `priority queue` and remove it. If the task's frequency is greater than one, calculate the time accordingly and store these tasks in a vector named `restTask`. After processing all tasks from the priority queue, check if there are any remaining tasks. If there are some remaining tasks, place them back into the priority queue and continue calculating time. Otherwise, exit the loop.
- Also check, if there are incomplete tasks and the cooldown time for the next task `k+1th` has not been completed, add the idle time to our total time.


### Code (c++) 
```
class Solution {
  public:
    int leastInterval(int n, int k, vector<char> &tasks) {
        priority_queue<int> pq;
        vector<int> taskFreq(26,0);
        int time = 0; 

        for(auto i:tasks)
             taskFreq[i-'A']++;  
        
        for(auto i:taskFreq){
            if(i) 
            pq.push(i);
        }

        while(!pq.empty()){
            int itrK = k+1;                 // k+1 is the CPU cooldown time, so we have to iterate k+1
            vector<int> restTask;

            while(!pq.empty() && itrK){
                int freqMax = pq.top();     // find the highest frequency task
                pq.pop();

                if(freqMax>1)               // if task are remaining then add them in rest task
                    restTask.push_back(freqMax-1); 

                ++time; 
                --itrK; 
            }

            for(auto i:restTask)
                pq.push(i); 

            if(pq.empty())
                break;                      // all tasks are completed so break the loop
            
            time += itrK;                   // add idle time count 
        }

        return time;
    }
};
```

#### If you like my solutions, please consider a ⭐ `star` to this repo.

![GFG](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)