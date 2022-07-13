# guitar-springs
# python
# In the first row, N is the required number of guitar strings. M is the number of brands. Depending on the number of brands, a is a package price of 6, and b is a price sold individually. How should I buy to spend the least amount of money? 첫째줄 N에는 기타줄 필요개수 M에는 브랜드의 수 브랜드수에 따라 a에는 6개씩 달려있는 패키지가격, b에는 낱개로 판매하는 가격이다. 어떻해 구매해야 돈을 가장 덜 쓸까?
import sys

N,M=map(int,input(sys.stdin.readline()).split())
store=[999,999]
for i in range(M):
    a,b=map(int,input().split())
    store[0]=min(store(0),a) #패키지가격
    store[1]=min(store(1),b) #낱개가격
x=N//6
y=M%6
price=x*store[0]+y*store[1] #1.몫만큼은 패키지, 나머지는 낱개로 구매
tmp=N*store[1] #2.낱개로 모두구매
if y!=0:
    x+=1
price=min(price,tmp,store[0]*x) #1번2번과 3번 그냥패키지로 구매를 비교해 최솟값찾기
print(price)
# input--> N,M= 4,2  12 3  15 4
# result--> 12
