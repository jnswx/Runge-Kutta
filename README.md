# Runge-Kutta

#include <iostream>  
using namespace std;  
 main()  
{  
 int k;  
 float X[k],Y[k],F[k];  
 float h=0.001;  
 double K1,K2,K3,K4;  
 float f(float,float);  
 X[0]=0.0;  
 Y[0]=1.0;  
 F[0]=f(X[0],Y[0]);  
 for(k=0;k<100;k++)
   { X[k+1]=X[k]+h;
     K1=h*F[k];
     K2=h*f(X[k]+0.5*h,Y[k]+0.5*K1);
     K3=h*f(X[k]+0.5*h,Y[k]+K2);
     K4=h*f(X[k]+h,Y[k]+K3) ;
     Y[k+1]=Y[k]+(K1+2.0*K2+2.0*K3+K4)/6.0;
     F[k+1]=f(X[k+1],Y[k+1]);
     cout<<X[k]<<endl;
     cout<<Y[k]<<endl;
     cout<<F[k]<<endl;
   }
  system("Pause");
  return 0;
}
float f(float a,float b)
{ float c;
  c=b-a*2.0/b;
  return (c);   
}
