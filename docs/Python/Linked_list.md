# Linked List

1. Create Node class with variables data and next_node
2. Create Linked list Class, with variable name header.
3. Create some node object and assign it to linked list head value.  
4. Create following functions.  
   * INsert Node at Head
   * Insert Node at Tail
   * Insert Node at some position
   * Delete Node at head and tail
   * Get length ofLinked List  

```python
class Node:
  def __init__(self,data):
    self.data=data
    self.nxt_node = None


class S_Lnkd_Lst:
   def __init__(self,):
     self.head = None
     
   def __len__(self):
     lcl_len=0
     lcl_node=self.head
     while lcl_node is not None:
       lcl_len+=1
       lcl_node=lcl_node.nxt_node   
     return lcl_len  
   def dsply_lst(self):
     tempnode=self.head
     while tempnode is not None:
       print(tempnode.data)
       tempnode=tempnode.nxt_node

   def add_data(self,position,data):  
     lcl_node=Node(data)
     if position == 'head' : 
       lcl_node.nxt_node = self.head
       self.head=lcl_node  
     elif position == 'tail':
       if self.head is None:
         self.head=lcl_node
         return  
       temp_node=self.head

       while temp_node.nxt_node is not None:
         temp_node=temp_node.nxt_node
       temp_node.nxt_node=lcl_node  
     elif isinstance(position,Node):
       lcl_node.nxt_node=position.nxt_node
       position.nxt_node = lcl_node

     elif isinstance(position,int):# insert at some position
        if position > len(self) :
          print('CAnnot be insterted at {}',position)
        else:
          print('nothing')  
   def rmv_node(self,position):
     if position is 'head':
       self.head=self.head.nxt_node
     if position is 'tail':  
      if self.head is None:
        print('nothing to remove')
        return
      if len(self)==1:
        self.head=None
        return  

      temp_node = self.head
      while temp_node.nxt_node is not None:
        prev=temp_node
        temp_node=temp_node.nxt_node
      prev.nxt_node=None
lcl_list= S_Lnkd_Lst()#instantiate Class
len(lcl_list)
lcl_list.head=Node('Monday')#Add Head node
lcl_list.head.nxt_node=Node('Tuesday')# Add Node to head
lcl_list.head.nxt_node.nxt_node=Node('Thursday')
lcl_list.head.nxt_node.nxt_node.nxt_node=Node('Friday')
# add Node Sunday at head
lcl_list.add_data('head','Sunday')
lcl_list.dsply_lst()
# add Node Saturday at tail
lcl_list.add_data('tail','Saturday')
lcl_list.dsply_lst()
# add node wednesday after tuesday node
lcl_list.add_data(lcl_list.head.nxt_node.nxt_node,'Wednesday')
lcl_list.dsply_lst()
```
