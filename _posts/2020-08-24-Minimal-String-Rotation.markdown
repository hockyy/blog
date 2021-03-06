---
title: Minimal Rotation on String
tags: [Competitive Programming]
toc: true
toc_label: "Contents"
author_profile: true
excerpt: A rotation of a string can be generated by moving characters one after another from beginning to end. Your task is to determine the lexicographically minimal rotation of a string. 💯
published: true
---

## Problem Statement

So recently, I checked out CodeForces's Edu. I read the course about suffix array. It's a shame for me not to understand that topic yet. But to start off real, I encounter a similar problem which maybe related to it. Check this one out, you should. [Minimal Rotation](https://cses.fi/problemset/task/1110/) 👍

## Subtask 1 (N <= 1,000)

Easiest one here, just compare every possible string.

```c++
#include <bits/stdc++.h>
using namespace std;

int main(){
    string s; cin >> s;
    int n = s.length();
    // Store the smallest index as ans
    int ans = 0;
    for(int i = 1;i < n;i++){
        // Compare ans with i, which string is smaller
        bool isSmaller = 0;
        for(int j = 0;j < n;j++){
            if(s[(j+i)%n] == s[(j+ans)%n]) continue;
            isSmaller = (s[(j+i)%n] < s[(j+ans)%n]);
            break;
        }
        if(isSmaller) ans = i;
    }
    for(int i = 0;i < n;i++) cout << s[(i+ans)%n];
    cout << endl;
}
```

As you can see, we don't need to store all the string, just compare the index of the shift. we find the first index where it differs, then check whether the first difference is smaller or larger, if it's smaller, we maintain the smaller index. Don't forget to put break after we found the first different character. 💚

Time Complexity: $O(N^2)$

## Subtask 2 (N <= 100,000)

```c++
#include <bits/stdc++.h>
using namespace std;
typedef long long LL;
typedef pair<int, int> PII;
#define fi first
#define se second
const LL MOD = 1000000007;

// My Rolling hash library here
```

```c++
int main(){
    string s; cin >> s;
    int n = s.length();
    // Double the string for easier hash
    s += s;
    rollingHash solver(&s);
    // Store the smallest index as ans
    int ans = 0;
    for(int i = 1;i < n;i++){
        // Compare ans with i, which string is smaller
        // You have to find the longest common prefix
        // Between string starting from i and ans
        // You can use Binary Search and Hashing!
        // Find LCP by binary searching the longest length of common prefix
        // Kiri means left, Kanan means right
        // It's in Bahasa Indonesia HAHAHHAHA
        int kiri = 0; int kanan = n;
        while(kiri < kanan){
            int mid = (kiri+kanan+1)>>1;
            if(solver.isSame({ans, ans+mid-1}, {i, i+mid-1})) kiri = mid;
            else kanan = mid-1;
        }
        // cout << "Comparing " << i << " " << ans << ", LCP is " << kiri << endl;
        // Case where all character on string is the same
        if(kiri == n) break;
        if(s[i+kiri] < s[ans+kiri]) ans = i;
    }
    for(int i = 0;i < n;i++) cout << s[(i+ans)%n];
    cout << endl;
}
```

It basically is the same with the previous solution, the catch is to skip the equal prefix, you can use binary search instead, find the first index where the character is different. 💯

Time Complexity: $O(N \log{N})$


## Subtask 3 (N <= 10,000,000)

$O(N\log{N})$ with large constant would definitely fail here. We need a better solution. 