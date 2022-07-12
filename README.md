# <font color=red> 代码库:</font>  -->[代码快传](http://inbox.weiyun.com/4Hbvm59e)

-------------------------------------------------------------------------

<font color=blue>1.高精度模板-></font>
```cpp
#include<bits/stdc++.h>
using namespace std;
struct numplus
{
	int len,f,d[1100];
	numplus() {}
	numplus(char s[])
	{
		len=strlen(s);
		for(int i=0; i<len; i++)
			d[len-i]=s[i]-'0';
	}
	numplus(int a)
	{
		len=0;
		do
			d[++len]=a%10,a/=10;
		while(a);
	}
	void out()
	{
		for(int i=len; i>0; i--)
			printf("%d",d[i]);
	}
	numplus operator +(numplus b)
	{
		numplus t;
		t.len=len;
		if(t.len<b.len) t.len=b.len;
		for(int i=len+1; i<=t.len; i++) d[i]=0;
		for(int i=b.len+1; i<=t.len; i++) b.d[i]=0;
		int w=0;
		for(int i=1; i<=t.len; i++)
		{
			t.d[i]=d[i]+b.d[i]+w,w=t.d[i]/10,t.d[i]%=10;
		}
		if(w>0) t.d[++t.len]=w;
		return t;
	}
} A,B,C;
char str[1100];

int main()
{

	C="0";
	for(int i=1; i<=10000; i++)
		C=C+numplus(i);
	C.out();
	return 0;
}
```
---------------------------------------
# <font color=blue> 访问更多-> </font>
## 1. [serve&cilent](https://share.weiyun.com/vEq4er36)
## 2. [Mini Metro](https://share.weiyun.com/tgcn0H4f)
