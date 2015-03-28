# Tut4-MyStack

#include <iostream>
#include "Fraction.h"

using namespace std;

class Fraction 
{
      private:
              int m_n, m_d;
      public:
             Fraction(){
                       m_n = 0;
                       m_d = 1;
             }
             
             Fraction(int n, int d){
                          m_n = n;
                          m_d = d;
             }
             
             int GetNum(){return m_n;}
             
             int GetDom(){return m_d;}
             
             void SetFrac(int n, int d){
                 m_n = n;
                 m_d = d;
             }
             
             Fraction &operator=(const Fraction &);
             Fraction &operator*(const Fraction&);
             Fraction &operator/(const Fraction&);
             Fraction &operator+(const Fraction&);
             Fraction &operator-(const Fraction&);
             
             friend ostream& operator<<(ostream& os, const Fraction& f);
             friend istream& operator>>(istream& is, Fraction& f);
             
             
};

Fraction & Fraction::operator=(const Fraction& f){
         m_n = f.m_n;
         m_d = f.m_d;
         return *this;
}

Fraction & Fraction::operator*(const Fraction& f){
         m_n *=f.m_n;
         m_d*=f.m_d;
         return *this;         
}

Fraction & Fraction::operator/(const Fraction& f){
         m_n *=f.m_d;
         m_d*=f.m_n;
         return *this;         
}

Fraction & Fraction::operator+(const Fraction& f){
         m_n +=f.m_n;
         m_d+=f.m_d;
         return *this;         
}

Fraction & Fraction::operator-(const Fraction& f){
         m_n +=(f.m_n*-1); 
         m_d +=(f.m_d*-1);
         return *this;         
}
 
ostream& operator<<(ostream &os, const Fraction& f){
         os << f.m_n << " / " << f.m_d<<endl;
         return os;
}

istream& operator>>(istream &is, Fraction& f) {
         is>>f.m_n>>f.m_d;
         return is;
}


         

int main()
{
    Fraction tmp;
    Fraction f1;
    Fraction f2;
    
    cout << "Please Enter Fraction 1 : "<<endl;
    cin >> f1;
    cout <<endl;
    cout << "Please Enter Fraction 2 : "<<endl;
    cin >> f2;
    cout <<endl;
    cout << " Addition : "<<endl;
    tmp = f1 + f2;
    cout << tmp<< endl;
    cout << " Subtraction : "<<endl;
    tmp = f1 - f2;
    cout << tmp<< endl;
    cout << " Multiplication : "<<endl;
    tmp = f1 * f2;
    cout << tmp<< endl;
    cout << " Division : "<<endl;
    tmp = f1 / f2;
    cout << tmp<< endl;
    
    
    
    int t;
    cin >> t;
    return 0;
}








 

















 
                 
                          
