#include<iostream>
#include<string>
using namespace std;

/* ============================================================
1. Input & Display 1D Array
============================================================ */
int main(){
 int n; cout<<"Size: "; cin>>n;
 int a[n]; cout<<"Enter: ";
 for(int i=0;i<n;i++) cin>>a[i];
 cout<<"Array: ";
 for(int i=0;i<n;i++) cout<<a[i]<<" ";
 return 0;
}
/* Output:
Size: 5
Enter: 1 2 3 4 5
Array: 1 2 3 4 5 
*/
//------------------------

/* ============================================================
2. Sum of All Elements
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n,s=0; cout<<"Size: "; cin>>n;
 int a[n]; cout<<"Enter: ";
 for(int i=0;i<n;i++) cin>>a[i], s+=a[i];
 cout<<"Sum="<<s;
}
/* Output:
Size: 4
Enter: 5 10 15 20
Sum=50
*/
//------------------------

/* ============================================================
3. Max & Min Element
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 int mx=a[0],mn=a[0];
 for(int i=1;i<n;i++){if(a[i]>mx)mx=a[i]; if(a[i]<mn)mn=a[i];}
 cout<<"Max="<<mx<<" Min="<<mn;
}
/* Output:
Size: 5
Enter: 2 9 5 1 7
Max=9 Min=1
*/
//------------------------

/* ============================================================
4. Reverse Array
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 cout<<"Rev: ";
 for(int i=n-1;i>=0;i--) cout<<a[i]<<" ";
}
/* Output:
Size: 5
Enter: 1 2 3 4 5
Rev: 5 4 3 2 1 
*/
//------------------------

/* ============================================================
5. Count Even & Odd
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int a[10],e=0,o=0;
 cout<<"Enter 10 nums: ";
 for(int i=0;i<10;i++) cin>>a[i], (a[i]%2?o++:e++);
 cout<<"Even="<<e<<" Odd="<<o;
}
/* Output:
Enter 10 nums: 1 2 3 4 5 6 7 8 9 10
Even=5 Odd=5
*/
//------------------------

/* ============================================================
6. Search Element (Linear)
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n,x,f=0; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 cout<<"Find: "; cin>>x;
 for(int i=0;i<n;i++) if(a[i]==x){f=1;break;}
 cout<<(f?"Found":"Not Found");
}
/* Output:
Size: 5
Enter: 2 4 6 8 10
Find: 6
Found
*/
//------------------------

/* ============================================================
7. Input & Display 2D Array
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int r,c; cout<<"Rows Cols: "; cin>>r>>c;
 int a[r][c]; for(int i=0;i<r;i++)for(int j=0;j<c;j++) cin>>a[i][j];
 cout<<"Matrix:\n";
 for(int i=0;i<r;i++){for(int j=0;j<c;j++) cout<<a[i][j]<<" "; cout<<"\n";}
}
/* Output:
Rows Cols: 2 3
Enter: 1 2 3 4 5 6
Matrix:
1 2 3 
4 5 6 
*/
//------------------------

/* ============================================================
8. Add Two Matrices
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int r,c; cout<<"Rows Cols: "; cin>>r>>c;
 int a[r][c],b[r][c],s[r][c];
 for(int i=0;i<r;i++)for(int j=0;j<c;j++) cin>>a[i][j];
 for(int i=0;i<r;i++)for(int j=0;j<c;j++) cin>>b[i][j];
 cout<<"Sum:\n";
 for(int i=0;i<r;i++){for(int j=0;j<c;j++){s[i][j]=a[i][j]+b[i][j]; cout<<s[i][j]<<" ";} cout<<"\n";}
}
/* Output:
Rows Cols: 2 2
Enter 1st: 1 2 3 4
Enter 2nd: 5 6 7 8
Sum:
6 8 
10 12 
*/
//------------------------

/* ============================================================
9. Subtract Two Matrices
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int r,c; cout<<"Rows Cols: "; cin>>r>>c;
 int a[r][c],b[r][c];
 for(int i=0;i<r;i++)for(int j=0;j<c;j++) cin>>a[i][j];
 for(int i=0;i<r;i++)for(int j=0;j<c;j++) cin>>b[i][j];
 cout<<"Diff:\n";
 for(int i=0;i<r;i++){for(int j=0;j<c;j++) cout<<a[i][j]-b[i][j]<<" "; cout<<"\n";}
}
/* Output:
Rows Cols: 2 2
Enter 1st: 5 6 7 8
Enter 2nd: 1 2 3 4
Diff:
4 4 
4 4 
*/
//------------------------

/* ============================================================
10. Multiply Two Matrices
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int r1,c1,r2,c2; cout<<"Enter r1 c1 r2 c2: "; cin>>r1>>c1>>r2>>c2;
 if(c1!=r2){cout<<"Not possible"; return 0;}
 int a[r1][c1],b[r2][c2],m[r1][c2]={0};
 for(int i=0;i<r1;i++)for(int j=0;j<c1;j++) cin>>a[i][j];
 for(int i=0;i<r2;i++)for(int j=0;j<c2;j++) cin>>b[i][j];
 for(int i=0;i<r1;i++)for(int j=0;j<c2;j++)for(int k=0;k<c1;k++) m[i][j]+=a[i][k]*b[k][j];
 cout<<"Mul:\n";
 for(int i=0;i<r1;i++){for(int j=0;j<c2;j++) cout<<m[i][j]<<" "; cout<<"\n";}
}
/* Output:
Enter r1 c1 r2 c2: 2 2 2 2
Enter A: 1 2 3 4
Enter B: 5 6 7 8
Mul:
19 22 
43 50 
*/
//------------------------

/* ============================================================
11. Bubble Sort Ascending
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 for(int i=0;i<n-1;i++)for(int j=0;j<n-i-1;j++) if(a[j]>a[j+1]) swap(a[j],a[j+1]);
 cout<<"Sorted: "; for(int i=0;i<n;i++) cout<<a[i]<<" ";
}
/* Output:
Size: 5
Enter: 5 3 1 4 2
Sorted: 1 2 3 4 5 
*/
//------------------------

/* ============================================================
12. Bubble Sort Descending
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 for(int i=0;i<n-1;i++)for(int j=0;j<n-i-1;j++) if(a[j]<a[j+1]) swap(a[j],a[j+1]);
 cout<<"Sorted: "; for(int i=0;i<n;i++) cout<<a[i]<<" ";
}
/* Output:
Size: 5
Enter: 5 3 1 4 2
Sorted: 5 4 3 2 1 
*/
//------------------------

/* ============================================================
13. Sort Names (Bubble Sort)
============================================================ */
#include<iostream>
#include<string>
using namespace std;
int main(){
 int n; cout<<"Count: "; cin>>n;
 string a[n]; for(int i=0;i<n;i++) cin>>a[i];
 for(int i=0;i<n-1;i++)for(int j=0;j<n-i-1;j++) if(a[j]>a[j+1]) swap(a[j],a[j+1]);
 cout<<"Sorted:\n"; for(int i=0;i<n;i++) cout<<a[i]<<"\n";
}
/* Output:
Count: 3
Enter: Raj Amit Vikram
Sorted:
Amit
Raj
Vikram
*/
//------------------------

/* ============================================================
14. Linear Search
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n,x,f=0; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 cout<<"Find: "; cin>>x;
 for(int i=0;i<n;i++) if(a[i]==x){f=1;break;}
 cout<<(f?"Found":"Not Found");
}
/* Output:
Size: 5
Enter: 10 20 30 40 50
Find: 30
Found
*/
//------------------------

/* ============================================================
15. Binary Search
============================================================ */
#include<iostream>
using namespace std;
int main(){
 int n,x,f=0; cout<<"Size: "; cin>>n;
 int a[n]; for(int i=0;i<n;i++) cin>>a[i];
 cout<<"Find: "; cin>>x;
 int l=0,h=n-1,mid;
 while(l<=h){
  mid=(l+h)/2;
  if(a[mid]==x){f=1;break;}
  else if(a[mid]<x) l=mid+1;
  else h=mid-1;
 }
 cout<<(f?"Found":"Not Found");
}
/* Output:
Size: 5
Enter: 10 20 30 40 50
Find: 30
Found
*/
//------------------------
