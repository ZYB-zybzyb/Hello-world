# #include<bits/stdc++.h>
using namespace std;
vector<int>range;
int num[20];
void fun()
{
    int i;
    num[0] = 1;
    for(i = 1;i <= 19;i ++){
        num[i] = num[i-1] * i;
    }
}
int main()
{
    int n,m,i;
    fun();
    scanf("%d",&n);
    for(i = 0;i < n;i ++){
        scanf("%d",&m);
        range.push_back(m);
    }
    int sum = 0;
    for(i = 0;i < n;i ++){
        int counts = 0;
        for(int j = i + 1;j < n;j ++){
            if(range[i] > range[j]){
                counts  ++;
            }
        }
        sum += counts * num[n-i-1];
    }
    printf("%d\n",sum);
    next_permutation(range.begin(),range.end());
    for(int k : range){
        printf("%d ",k);
    }
    return 0;
}
