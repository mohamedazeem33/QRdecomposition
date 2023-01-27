# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
    
    
![Screenshot (40) new](https://user-images.githubusercontent.com/121040764/215130103-750344b2-b18b-4e55-adc2-90575731f7ea.png)



## Program:
### Gram-Schmidt Method
```python
#Program to QR decomposition using the Gram-Schmidt method
#Developed by: SATHISH R
#RegisterNumber: 22009045

import numpy as np
def QR_Decomposition(A):
 n,m=A.shape
 Q = np.empty((n,n))
 u = np.empty((n,n))
 u[:,0] = A[:,0]
 Q[:,0] = u[:,0]/np.linalg.norm(u[:,0])
 for i in range(1,n):
 u[:,i] = A[:,i]
 for j in range(i):
 u[:,i] -= (A[:,i] @ Q[:,j]) * Q[:,j]
 Q[:,i] = u[:,i]/np.linalg.norm(u[:,i])
 R = np.zeros((n,m))
 for i in range(n):
 for j in range(i,m):
 R[i,j ] = A[:,j] @ Q[:,i]
 print(Q)
 print(R)
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output


![Screenshot (41) new](https://user-images.githubusercontent.com/121040764/215137492-7334a36a-0e1c-4ac0-a0ac-804b6e57c20a.png)


![Screenshot (42) new](https://user-images.githubusercontent.com/121040764/215137601-ec0bb490-577b-4cfb-9a16-373795470484.png)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
