- 👋 Hi, I’m @iblis-Oops
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
iblis-Oops/iblis-Oops is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.


<<<<<<-----  Implementation of Tree   ----->>>>>>
--->
class Node:
    def __init__(self,data):
        self.data = data
        self.right = None
        self.left = None 
        
    def insert(self,data):
        if self.data:
            if data<self.data:
                if self.left:
                    self.left.insert(data)
                else:
                    self.left = Node(data)
                    
            elif data>self.data:
                if self.right:
                    self.right.insert(data)
                else:
                    self.right = Node(data)
                    
        else:
            self.data = data 
            
            
    def printTree(self):
        print(self.data,end = ' ')
        if self.left:
            self.left.printTree()
        if self.right:
            self.right.printTree()
            
            
    def LevelOrder(root):   <<<<  Using iterative method >>>>
        if root is None:
            return 
        arr,res = [],[]
        arr.append(root)
        while arr:
            node = arr.pop(0)
            res.append(node.data)
            if node.left:
                arr.append(node.left)
            if node.right:
                arr.append(node.right)
                
        return res
        
    def preOrder(root): <<<< Using iterative method >>>>
        if root is None:
            return 
        arr,res=[],[]
        arr.append(root)
        while arr:
            node = arr.pop()
            res.append(node.data)
            if node.right:
                arr.append(node.right)
            if node.left:
                arr.append(node.left)
                
        return res
        
    def postOrder(root):      <<<< Using iterative method >>>>
        if root is None:
            return 
        arr,res=[],[]
        arr.append(root)
        while arr:
            node = arr.pop()
            res.append(node.data)
            if node.left:
                arr.append(node.left)
            if node.right:
                arr.append(node.right)
            
                
        return res[::-1]
        
        
    def inOrder(root):    <<<< Using iterative method >>>>
        if root is None:
            return 
        arr,res = [],[]
        curr = root 
        while True:
            if curr:
                arr.append(curr)
                curr = curr.left 
            elif arr:
                curr = arr.pop()
                res.append(curr.data)
                curr = curr.right
            else:
                break 
            
        return res
        
        
root = Node(10)
root1 = Node(12)
root2 = Node(13)
root3 = Node(14)
root4 = Node(16)
root.left = root1 
root.right = root2 
root1.left = root3 
root1.right = root4 
root.printTree()
