# First-and-Last-Position-of-an-Element-In-Sorted-Array
Code Studo Problem
#include <bits/stdc++.h> 
#include<vector>
using namespace std;
int firstoccurence(vector<int>& arr, int n, int k) 
{
    int start=0;
    int end=n-1;
    int mid=start+(end-start)/2;
    int ans=-1;
    while(start<=end)
    {
        if(arr[mid]==k)
        {
          ans=mid;
          end=mid-1;
        }
        else if(arr[mid]<k)
        {
            start=mid+1;
        }
        else
        {
            end=mid-1;
        }
        mid=start+(end-start)/2;
    }
    return ans;
    
}
int lastoccurence(vector<int>& arr, int n, int k) 
{
    int start=0;
    int end=n-1;
    int mid=start+(end-start)/2;
    int ans=-1;
    while(start<=end)
    {
        if(arr[mid]==k)
        {
          ans=mid;
          start=mid+1;
        }
        else if(arr[mid]<k)
        {
            start=mid+1;
        }
        else
        {
            end=mid-1;
        }
        mid=start+(end-start)/2;
    }
    return ans;
}
pair<int, int> firstAndLastPosition(vector<int>& arr, int n, int k)
{
    // Write your code here
    pair<int,int>p;
    p.first =firstoccurence(arr,n,k ) ;
    p.second=lastoccurence(arr,n,k );
    return p;
    
    
       
    
}
