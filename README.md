## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: R.Manobala
RegisterNumber: 25016414
'''
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for  j in range(n):
        v=A[:,j]
        
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R

A=np.array(eval(input()))
Q,R=QR_Decomposition(A)
print("The Q Matrix is \n",Q)
print("The R Matrix is\n",R)
    








```

## Output

<img width="1134" height="753" alt="Screenshot 2025-12-04 213659" src="https://github.com/user-attachments/assets/76f38c54-1a70-43de-b653-c0fc9bbcdd0a" />

<img width="1261" height="751" alt="Screenshot 2025-12-04 213717" src="https://github.com/user-attachments/assets/2131ac10-af66-4ccd-a421-ae26fb4dccd6" />





## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
