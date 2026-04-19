# DSA-day-119   
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int mirrorDistance(int n) {
        // Step 1: Convert to string
        string s = to_string(n);

        // Step 2: Reverse the string
        reverse(s.begin(), s.end());

        // Step 3: Convert back to integer
        int rev = stoi(s); y

        // Step 4: Return absolute difference
        return abs(n - rev);
    }
};


gfg
2 #include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int maxOnes(vector<int>& arr) {
        int n = arr.size();
        int originalOnes = 0;

        // Step 1: Count original 1s
        for (int x : arr) {
            if (x == 1) originalOnes++;
        }

        // Step 2: Build gain array and apply Kadane’s Algorithm
        int maxGain = INT_MIN, currentGain = 0;
        for (int x : arr) {
            int gain = (x == 0 ? 1 : -1);
            currentGain = max(gain, currentGain + gain);
            maxGain = max(maxGain, currentGain);
        }

        // Step 3: Add max gain to original 1s, but only if gain is positive
        return originalOnes + max(0, maxGain);
    }
};
