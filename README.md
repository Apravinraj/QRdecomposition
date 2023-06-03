# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![image](https://github.com/Apravinraj/QRdecomposition/assets/118707879/40c4491d-0e18-4977-9bcc-a6472ef4b821)

![image](https://github.com/Apravinraj/QRdecomposition/assets/118707879/7f44fc91-30c9-4ad4-a6e4-fd01d0a9830a)

   ![image](https://github.com/Apravinraj/QRdecomposition/assets/118707879/be1dda6f-d0d5-4f50-bd33-2f62d355bd0f)


3.	Obtain the Q matrix   
  
4.	Construct the upper triangular matrix R


## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: Pravin raj.A
RegisterNumber: 212222240079
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    Q= np.empty((n,n))
    u = np.empty((n,n))
    
    u[:, 0]= A[:, 0]
    Q[:, 0]= u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1,n):
        
        u[:, i]=A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
            
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i, m):
            R[i,j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
    
    
    
a = np.array(eval(input()))
QR_Decomposition(a)




```

## Output

![Screenshot 2023-06-03 103444](https://github.com/Apravinraj/QRdecomposition/assets/118707879/75d3860f-323c-4997-a104-d40ed72d580f)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
