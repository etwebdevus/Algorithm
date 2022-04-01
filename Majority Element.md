# Majority Element

**Problem Description**  

Given an array of size  **n**, find the majority element. The majority element is the element that appears more than  **floor(n/2)**  times.

You may assume that the array is non-empty and the majority element always exist in the array.

Example :

```
Input : [2, 1, 2]
Return  : 2 which occurs 2 times which is greater than 3/2.
```
**Solution**  
```
int Solution::majorityElement(const vector<int> &A) {
    int c=0;
    int m;
    for(int i=0;i<A.size();i++)
    {
        if(c==0)
        {
           m=A[i];
           c=1;
        }
        else if(m!=A[i])
        {
            c-=1;
        }
        else if(m==A[i])
        {
            c+=1;
        }
    }
    return m;
    
}
```
```
module.exports =  {
	//param A : array of integers
	//return an integer
	majorityElement :  function(A){
		let count =  {};
		for(let i =  0; i <  A.length; i++)  {
			if(count[A[i]])
				count[A[i]]++;
			else
				count[A[i]]  =  1;
		}

		let val =  -1;
		Object.keys(count).forEach(v =>  {
			if(count[v]  >  Math.floor(A.length /  2))  {
				val = v;
			}
		});
		return val;
	}
};
```
