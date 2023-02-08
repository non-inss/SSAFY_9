# 2028
```
N = int(input())

for _ in range(N):
    num = int(input())
    k = len(str(num)) #주어진 숫자가 몇자리 숫자인지를 확인합니다
    if str(num**2)[-k:] == str(num): #제곱수를 뒤에서 sli만큼만 가져와 num과 동일한지 판단합니다
        print("YES")
    else:
        print("NO")
```

# 2231
```
n = int(input())  # 분해합을 입력값으로 받음

for i in range(1, n+1):   # 해당 분해합의 생성자 찾기
    num = sum((map(int, str(i))))  # i의 각 자릿수를 더함
    num_sum = i + num  # 분해합 = 생성자 + 각 자릿수의 합
    # i가 작은 수부터 차례로 들어가므로 처음으로 분해합과 입력값이 같을때가 가장 작은 생성자를 가짐
    if num_sum == n:
        print(i)
        break
    if i == n:  # 생성자 i와 입력값이 같다는 것은 생성자가 없다는 뜻
        print(0)
```

#5622

```
alpabet_list = ['ABC','DEF','GHI','JKL','MNO','PQRS','TUV','WXYZ']
word = input()

time = 0
for unit in alpabet_list :  
    for i in unit:  # alpabet 리스트에서 각 요소를 꺼내서 한글자씩 분리
        for x in word :  # 입력받은 문자를 하나씩 분리
            if i == x :  # 두 알파벳이 같으면
                time += alpabet_list.index(unit) +3  # time = time + index +3
print(time)
```

# 3040
```
dwarf = [int(input()) for _ in range(9)]
answer = False
    
for i in range(8):
    if answer: #답이 이미 나온 경우
        break
        
    for j in range(i+1, 9):
        if sum(dwarf) - dwarf[i] - dwarf[j] == 100: #2명 뺸 7명의 합이 100인 경우
            dwarf.pop(i)
            dwarf.pop(j-1)
            
            for k in sorted(dwarf):
                print(k)
                
            answer = True #답이 나옴
            break
```

# 5585
```
n = 1000 - int(input()) # 1000 주머니에서 1000엔뺏으니

currency = [500, 100, 50, 10, 5, 1] # 동전의 가치 저장할 리스트 선언
count = 0 # 동전의 개수를 저장할 변수
i = 0 # 동전의 가치 리스트의 인덱스 변수

while n != 0:
  count += n//currency[i] # 동전의 개수를 저장
  n %= currency[i] # 동전의 가치로 나눈 나머지를 저장
  i += 1 # 인덱스를 증가시킨다.

print(count)
```
```
n=1000-int(input())
count=0
coin=[500,100,50,10,5,1]

for i in coin:
    if n>0:
        count+=n//i
        n=n%i
    elif n==0:
        break
print(count)
큰 잔돈을 먼저 제외해주어야 한다.그리디 문제이다.

1000에서 지출할 돈을 빼준다(n)
잔돈의 개수(count), 잔돈 종류의 배열(coin)을 선언한다.
잔돈 종류에 대해 반복문을 돌린다. 만약 n이 0보다 크다면 계속 반복해준다.
n//i로 잔돈의 개수를 구해주고, n=n%i로 잔돈을 제외하고 남은 돈을 초기화해준다.
만약 n이 0이라면 더이상 계산해줄 필요가 없으므로 반복문을 빠져나온다.
```

# 1977
```
x = int(input())
y = int(input())
sum=0

for i in range(101):
    if x <= (i*i) and y>=(i*i):
        if sum==0:
            min = i*i
        sum += i*i

if sum ==0:
    print(-1)
else:
    print(sum)
    
    print(min)
```
