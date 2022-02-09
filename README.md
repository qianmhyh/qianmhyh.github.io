### P5738 洛谷题解
## ->难度：入门
## 题目直达->[P5738 【深基7.例4】歌唱比赛]（https://www.luogu.com.cn/problem/P5738）

###### 第一次写题解，可能有不完善之处，请多多谅解！


------------
### 首先根据题意，有参赛选手 n<=100,评委数 m<=20;

#### 所以可以以此构造二维数组**a[105][100]**;并规定为有变量**i,j**。
#### **i**表示选手编号，即输入顺序;
#### **j**表示第**j**位评委打分。
#### 再用sum数组累计每位选手的积分和（去掉max,min）,再求平均数


------------

# 分析完毕，代码如下：
```cpp
#include<bits/stdc++.h>
using namespace std;

int n,m;
int a[105][100],maxn,minn;
double sum[105],vsum;
int main()
{
	cin>>n>>m;
	for(int i=1;i<=n;i++)//人数 
	{
		maxn=-1;
		minn=1000;
		for(int j=1;j<=m;j++)//评委数 
		{
			cin>>a[i][j];
			sum[i]+=a[i][j];
			maxn=max(maxn,a[i][j]);
			minn=min(minn,a[i][j]); 
		}
		sum[i]-=(maxn+minn);
		sum[i]=sum[i]/(m-2);
		if(sum[i]>vsum)
		{
			vsum=sum[i];
		}
	}
	cout<<fixed<<setprecision(2)<<vsum;
	return 0;
}
```
###  _完结散花_ 
