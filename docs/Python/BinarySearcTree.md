```python
class BinarySearchTree():
    def __init__(self,data):
      ##############################################
      #every element itself is binary tree,        #  
      # where it has atmost two elements           # 
      # and left element is less than right element#
      ############################################## 
      self.data= data
      self.left=None
      self.right= None
      
    def add_child(self,data):
      ############################
      #add element to left child, check if passed value is 
      #     lesser than current value
      # else add it to right child
      ############################
      if data < self.data:
        if self.left:
          self.left.add_child(data)
        else:
          self.left= BinarySearchTree(data)
      elif data > self.data:
        if self.right:
          self.right.add_child(data)
        else:
          self.right=BinarySearchTree(data)  

      else:      
        print(data,'value alreay exists' ) 
    def inorder(self):
      #########
      # print left, root , right
      # this will print in ascending order
      #########  
      elements= []
      if self.left:
        elements+=self.left.inorder()
      elements.append(self.data)
      if self.right:
        elements+=self.right.inorder()

      return elements    
    def preorder(self):
      elements= []
      elements.append(self.data)
      if self.left:
        elements+=self.left.preorder()
      #elements.append(self.data)
      if self.right:
        elements+=self.right.preorder()

      return elements      
    def postorder(self):
      elements= []
      #elements.append(self.data)
      if self.left:
        elements+=self.left.postorder()
      #elements.append(self.data)
      if self.right:
        elements+=self.right.postorder()
      elements.append(self.data)
      return elements   
    def min(self):
      if self.left:

        return self.left.min()
      else: 
        return self.data  
    def max(self):
      if self.right:

        return self.right.max()
      else: 
        return self.data     
    def search(self,val):
      if val== self.data:
        return True
      elif val<self.data:
        if self.left:
          return self.left.search(val)  
        else:
          return False  
      elif val> self.data:
        if self.right:
          return self.right.search(val)
        else:
          return False  
      else:
        return False
    def sum(self):
      ans=self.data
      if self.left:
        ans=ans+self.left.sum()
      if self.right:
        ans=ans+self.right.sum()
      return ans       
    def delete(self,val):
      if self.data > val :
        if self.left:
          self.left=self.left.delete(val)
      elif val > self.data :
          if self.right:
            self.right=self.right.delete(val) 
      else:
        if self.left == None and self.right==None:
          return None
        if self.right==None:
          return self.left
        if self.left == None:
            return self.right
        rmin=self.right.min()
        self.data=rmin
        self.right = self.right.delete(rmin)
      return self  
```
[Notebook](https://github.com/ankojubhanuprakash/DS_Algo_python/blob/main/BinarySearchTree.ipynb)