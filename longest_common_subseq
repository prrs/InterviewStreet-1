//longest common subsequence

#include <stdio.h>
#include <stdlib.h>
#include <algorithm>
#include <string.h>
using namespace std;
int dd[7+1][8+1];
int lcs(char *x, char *y,int m, int n)
{
	if (m < 0 || n < 0) return 0;
	if (x[m]==y[n])
	  return 1 + lcs(x, y,m-1 , n-1);
	else
	  return max(lcs(x, y, m,n-1), lcs(x, y, m-1,n));
}

int lcsdp(char *x, char *y,int m, int n)
{
	for(int i=1;i<=m;i++){
		for(int j=1;j<=n;j++){
			if(x[i-1]==y[j-1]){
				dd[i][j]=dd[i-1][j-1]+1;
				
			}					
			else
				dd[i][j] = max(dd[i-1][j], dd[i][j-1]);
		}
	}
	return dd[m][n];
}

void init(int row, int col){
	for(int i=0;i<row;i++) dd[i][0] = 0;
	for(int i=0;i<col;i++) dd[0][col] = 0;

}
int main(){
  char X[] = "AGGTAB";
  char Y[] = "GXTXAYB";
  int x_len = strlen(X);
  int y_len = strlen(Y);
  init(x_len, y_len);
 
  printf("%d\n",lcsdp(X,Y,x_len,y_len));
  
 
  return 0;

}

