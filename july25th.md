# Data Structure

## intro
데이터 저장: 변수, 컨테이너  
데이터처리: for문, if 문, 함수, 연산자

컨테이너= 자료구조  
활용= 메서드 = 함수  
오늘 배우는건 함수의 연장선임

데이터 구조를 활용하기 위해서는 메서드 활용  
__메서드__   
클래스 내부에 정의한 함수. 그냥 함수랑 똑같음  
데이터구조.메서드() 형태로 활용됨.  
주어.동사() 느낌쓰  
ex) list.append(), string.split()  

함수를 지금 다 외우진 말고 문제 주어졌을때마다 검색해보기  
하다보면 자연스럽게 외워짐

***

## 순서가 있는 데이터 구조
### 문자열, 리스트, 튜플

### 1. 문자열  
모든 문자는 str 타입 (변경불가능한 immutable)  

```python
word = 'ssafy'
print(word)
print(id(word))
word = 'test'
print(word)
print(id(word))
#이거는 변경된게 아니고 걍 덮어씌운거임
```
find:조회. 첫번째 위치 반환. 없으면 -1 반환 (오류 안남)  
```python
print('apple'.find('p')) #1
print('apple'.find('z')) #-1
```
index: 조회. 첫번째 위치 반환. 없으면 오류생김  
isalpha:알파벳 문자여부  
isupper, islower: 대소문자여부  
```python
print('abc'.isalpha()) #True
print('ㄱㄴㅇ'.isalpha()) #True
print('abc'.islower()) #True
```
isdecimal(), isdigit(), isnumeric(): 뒤로 갈수록 더 범위 넓음  
istitle: 타이틀형식여부


#### 문자열 변경 메서드
s.replace(예전꺼, 바꿀꺼[,횟수])  
```python
print('wooooowoo'.replace('o','!',2)) #w!!ooowoo 
#앞에 두개만 바꿈
```
s.strip(빼고싶은문자)   
    -strip(양쪽제거), lstrip(왼쪽제거), rstrip(오른쪽제거)  
s.split(특정 문자 기준 분리)
```python
print('a,b,c'.split(',')) #['a','b','c']
```
'문자'.join([합칠거]) :특정 문자 기준으로 합침
```python
print('!'.join('ssafy')) #'s!s!a!f!y'
```  
capitalize: 첫글자 대문자  
title: 각 단어 첫글자 대문자  
upper, lower
swapcase: 대소문자 서로 변경

### 2. 리스트  
어떠한 자료형도 저장 가능, 가변자료형  
list.append(x): 마지막항목 x 추가  
list.insert(i, x): 인덱스 i에 x 삽입  
remove(x): 리스트 가장 왼쪽에 있는 x 제거  
pop():리스트 가장 오른쪽에 있는 항목 반환 후 제거  
pop(x):리스트의 인덱스 i 에 있는 항목 반환 후 제거
extend(x): 순회형 m의 모든 항목 리스트 끝에 추가 (리스트 이어붙이기)  
index(x, start, end):리스트 항목 중 가장 왼쪽에 있는 항목 c의 인덱스 반환  
reverse(): 거꾸로 정렬  
sort(): 정렬  
```python
result = sorted(numbers)
```
count(x):리스트에서 항목 x가 몇개 존재하는지 

### 3. 튜플  
여러개의 값을 순서가 있는 구조로 저장하고 싶을 때 사용(불변자료형)  
```python
day_name = ('월', '화', '수', '목', '금')
print(type(day_name)) #tuple
print(day_name[-3]) #수
print(day_name * 2) #('월', '화', '수', '목', '금', '월', '화', '수', '목', '금')
day_name += False, True
print(day_name) # ('월', '화', '수', '목', '금', True, False)
```
멤버십연산자 in:  
특정 요소가 속해있는지 확인
```python
print('apple' in 'a') #False
print('a' in 'apple') #True
print('나' in ['나', '너', '우리']) #True
```
***
## 순서가 없는 데이터 구조
### 셋, 딕셔너리

### 1. 셋
중복되는 요소가 없이, 순서 상관없는 데이터들의 묶음  
중복되는 원소가 있다면 하나만 저장됨  
순서가 없어서 인덱스를 통한 접근 불가능  
집합연산 가능, 가변자료형  

셋.copy(): 셋의 얕은 복사본을 반환  
셋.add(x): 항목 x 가 셋 s에 없다면 추가  
```python
a={'사과','바나나','수박'}
print(type(a))
print(a.add('딸기'))
#딸기는 맨 뒤에 더해지는게 아니라 걍 중간에 들어감
```
.pop(): 셋에서 랜덤하게 항목을 반환하고, 해당 항목을 제거. 셋이 비어있으면 에러  
.remove(x):x를 셋에서 삭제. 해당 항목이 없으면 에러.  
.discard(x): 항목 x가 셋에 있으면 삭제  
.clear(): 모든 항목 제거  
.update(t): 셋t에 있는 모든 항목 중 셋에 없는 항목 추가  
s.isdisjoint(t): s가 t의 서로 같은 항목을 하나라도 갖고있지 않은 경우, True (이 두 셋은 서로소인가?
)  
s.issubset(t): s가 t의 하위셋인경우, True  
s.issuperset(t):s가 t의 상위셋인 경우, True

### 2. 딕셔너리  
.clear(): 모든 항목제거  
.copy(): 얕은 복사본 반환  
.keys(): 딕셔너리의 모든 키를 담은 뷰 반환  
.values(): 딕셔너리의 모든 값을 담은 뷰 반환 
```python
my_dict = {'apple':'사과', 'banana':'바나나'}
for key in my_dict:
    print(key) # apple banana

for values in my_dict.values():
    print(value)  #사과 바나나

for key, value in my_dict.items():
    print(f'key: {key} / value: {value}')
    #key: apple / value: 사과
    #key: banana / value: 바나나

```
.items(): 딕셔너리의 모든 키-값 쌍을 담은 뷰 반환  
.get(k): 키 k 값 반환, 없으면 None (에러가 안남)  
.get(k,v): 키 k값 반환, 없으면 v  
.pop(k): 키 k값 반환, 키 k인 항목을 딕셔너리에서 삭제, k가 딕셔너리에 없으면 에러  
.pop(k,v): 키 k값 반환, 키 k인 항목을 딕셔너리에서 삭제, k가 딕셔너리에 없으면 v  
```python
dicti = {'apple':'사과', 'banana':'바나나'}
data = dicti.pop('pineapple')
print(data, dicti) #KeyError

dicti = {'apple':'사과', 'banana':'바나나'}
data = dicti.pop('pineapple',0)
print(data, dicti)
```
.update(): 딕셔너리의 값을 매핑하여 업데이트

