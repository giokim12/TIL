# 파이썬으로 만든 UP DOWN GAME

```import random

is_playing = True

while is_playing:
    print('================================')
    print('        Up and Down Game        ')
    print('================================')

    answer = random.randint(1, 10000)  # 1이상 10000이하의 난수
    counts = 0  # 몇 번만에 정답을 맞혔는지 담는 변수

    # 여기부터 코드를 작성하세요.
```    
맨 위에서 이미 정답은 랜덤변수로 정해짐  
맨 위에 while문으로 새로 게임이 시작되면, up and down game 그림이 출력되고 새 답이 설정되는 것을 확인할 수 있음.

    
```    
    while is_playing:
        number = int(input("1 이상 10000 이하의 숫자를 입력하세요. :"))
        if number>10000 or number<1:
            print("잘못된 범위의 숫자를 입력하셨습니다. 다시 입력해주세요.")
            continue

```

1. number변수: 나의 guess. 내가 틀리는 답을 말하는 한 계속 다시 값을 받아서 실행되어야 하는 변수

* __continue를 쓰면 while 처음으로 돌아간다.__  
number 변수를 while 문 안에 넣어줘야 계속 숫자를 물어볼 수 있다.



```
        else:
            if number > answer:
                print("Down!!!")
                counts += 1
                continue
            elif number < answer:
                print("Up!!!")
                counts += 1
                continue
            else:
                print(f"Correct! {counts}번 만에 맞히셨습니다.")
                break
```

if문으로  
1. 아예 범위에 없는 값을 입력했을 때,  
2. 내가 추측한 숫자가 답보다 큰 숫자일 때,  
3. 내가 추측한 숫자가 답보다 작은 숫자일 때,  
4. 내가 추측한 숫자가 답이랑 같을 때  
의 경우를 나눠서 코드를 짰음

아까 언급했듯,  
continue에 도달하면 다시 while문 처음으로 가서 새로운 number 변수를 입력받는 코드가 실행됨.  
break에 도달하면 다음줄으로 넘어감.


```                
    cont = input("게임을 재시작 하시려면 y, 종료하려면 n을 입력하세요:")
    if cont == 'y':
        continue
    elif cont == 'n':
        print("이용해주셔서 감사합니다. 게임을 종료합니다.")
        break
    else:
        print("잘못된 값을 입력하셨습니다. 게임을 종료합니다.")
        break        

```
__이 코드는 이제 while 문에서 빠져나온 상태이기 때문에, tab을 while이랑 같은선상에 놔야됨.__


___


### 전체 코드
``` 
 import random

is_playing = True

while is_playing:
    print('================================')
    print('        Up and Down Game        ')
    print('================================')

    answer = random.randint(1, 10000)  # 1이상 10000이하의 난수
    counts = 0  # 몇 번만에 정답을 맞혔는지 담는 변수

    # 여기부터 코드를 작성하세요.
    
    
   ``` 
    while is_playing:
        number = int(input("1 이상 10000 이하의 숫자를 입력하세요. :"))
        if number>10000 or number<1:
            print("잘못된 범위의 숫자를 입력하셨습니다. 다시 입력해주세요.")
            continue
        else:
            if number > answer:
                print("Down!!!")
                counts += 1
                continue
            elif number < answer:
                print("Up!!!")
                counts += 1
                continue
            else:
                print(f"Correct! {counts}번 만에 맞히셨습니다.")
                break
                
    cont = input("게임을 재시작 하시려면 y, 종료하려면 n을 입력하세요:")
    if cont == 'y':
        continue
    elif cont == 'n':
        print("이용해주셔서 감사합니다. 게임을 종료합니다.")
        break
    else:
        print("잘못된 값을 입력하셨습니다. 게임을 종료합니다.")
        break        

```