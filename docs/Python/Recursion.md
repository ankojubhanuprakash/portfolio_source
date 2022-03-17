# Recursion program
## Roman to integer
```python
def extract(s,ans,current,lookup):
    if s=='':
        #print(ans)
        return ans
    
    a=lookup[current]
    b=lookup[s[-1]]
    if a<=b:
        return extract(s[:-1],ans+b,s[-1],lookup)
    else:
        return extract(s[:-1],ans-b,s[-1],lookup)
        
class Solution:
    #def 
    def romanToInt(self, s: str) -> int:
        #take_two=True
        #sum=0
        lookup={'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000}
        sum=extract(s[:-1],lookup[s[-1]],s[-1],lookup)
        #print(sum)
        return sum
```
## InterLeavings
## Sum of subsets of array 
## open bracket and cloing bracket
## Tic Tac toe
