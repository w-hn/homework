## 实验目的    
1.利用Python将计算机强大的计算功能进行泰勒公式等高数问题的计算   
2.解决线性代数方面的问题。    
        
## 实验工具      
Winpython 64 bits   
        
Sympy Numpy   
     
## 实验流程  
配置实验环境：   
from sympy import *   
x,y,z = symbols(‘a,b,c’)    
init_printing()     
import numpy as np    
                
高数问题计算（sympy）   
1.求极限 limit x->0: (sin(x)-x)/x^3                
实际计算的是  
limit x->0: (sin(x)-x)/x^3      
                
2.泰勒展开式(Taylor series)          
e^x/、sin(x)等等           
在limit x->0时，也称之为麦克劳林展开，后方的o（x）成为拉格朗日余项。     

                
线性代数问题计算（numpy）         
By Ax = b to slove the inverse of A.            
This function is no like the question in 2,by using A^{-1} = IA (I is identity matrix of square matrix in R^n)          
A= [[4,3,9],[2,9,7],[1,1,7]]            
The inverse of A is on the picture.                          

