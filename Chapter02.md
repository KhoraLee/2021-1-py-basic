# Chapter02
[파이썬의 기본 문법](#파이썬의-기본-문법)<br>
[사칙연산](#사칙-연산)<br>
[변수와 자료형](#변수와-자료형)<br>
[좀더 알아보기](#좀-더-알아보기)

## 파이썬의 기본 문법
지난시간에는 파이썬 프로그래밍을 위한 개발환경을 만들고, 간단한 문자열을 출력해보았습니다.<br>
이번에는 파이썬을 프로그래밍할 때 알아야 하는 기본적인 문법을 알아보겠습니다.

### 주석
주석은 소스코드를 읽는 **사람**에게 주는 설명입니다.<br>
당연히 번역기는 주석을 읽지 않습니다.<br>
다음은 파이썬의 주석 예시입니다.
```python
# objects를 sep로 나누고 end를 붙여서 file로 출력합니다.
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False):
  # flush는 3.3 버전부터 추가되었습니다.
```
파이썬에서 주석은 해쉬태그(`#`)를 이용해서 작성합니다.

### 들여쓰기와 세미콜론
잠시 다른 언어로 가보겠습니다.
```c
int main(void) {
  printf("Hello, World!\n");
}
```
#### 들여쓰기
C언어에서 `{ }`로 둘러싸인 부분을 **코드 블럭**이라고 합니다.<br>
코드 블럭은 한 문단처럼 보이는, 코드의 한 부분입니다.<br>
그러면 `int main(void) {printf("Hello, World!\n");}`처럼 한줄로 써도 되는거 아닌가요?<br>
맞습니다. 하지만 그렇게 쓰지 않는 이유는 **가독성** 때문입니다.<br>
코드를 작성하는 사람이나 나중에 코드를 읽어보는 사람을 위해 **들여쓰기**<sup>indentation</sup> 매우 중요합니다.

파이썬에서 **들여쓰기**는 문법으로 정해져 있습니다.<br>
왜냐하면, 파이썬에서 **코드 블럭**을 구분할 때 C언어와는 다르게 `{ }`를 쓰지 않기 때문입니다.<br>
파이썬은 들여쓰기를 통해 코드 블럭을 구분합니다.

같은 블럭이면, 들여쓰기 정도가 같아야 하죠.<br>
예를들면 다음과 같습니다.
```python
if __name__ == '__main__':
  print('Hello, World')
  for i in range(10):
    print(i)
```
horizon tab `\t`이나 space ` `를 이용해 들여쓰기를 합니다.

#### 세미콜론
C언어에서는 문장의 끝을 `;`(semicolon) 으로 구분합니다.<br>
어떤 문장이 끝날 때에는 반드시 이 기호를 붙여야 합니다.<br>
하지만 파이썬에서는 반드시 붙일 필요는 없습니다.<br>
만약 한 줄에 여러 문장을 넣고 싶을 때는 사용해도 됩니다.
```python
print('hello'); print('world')
```
세미콜론을 통해 문장을 구분해 주면 됩니다. 

## 사칙 연산
지난시간에 우리는 파이썬 인터렉티브 셸을 통해 입력한 문장의 결과를 대화하듯이 바로 바로 알 수 있었습니다.<br>
이번에는 파이썬을 계산기로 이용해 봅시다.

각자의 IDE, 또는 CLI 콘솔에서 파이썬을 실행해 봅시다.
```cmd
C:\Users\1982kca> python
Python 3.9.2 (tags/v3.9.2:1a79785, Feb 19 2021, 13:44:55) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
파이선 프롬프트<sup>Python prompt</sup> `>>>`에 `1 + 2`를 입력해 봅시다.<br>
그러면 `3`이라는 값이 출력될 것입니다.
```cmd
>>> 1 + 2
3
```
덧샘 뿐만 아니라 다른 연산도 해봅시다.

```cmd
>>> 2 - 5
-3
>>> 7 * 2
14
>>> 7 / 2
3.5
```
파이썬에서 나누기는 &#247;대신에 `/`를 사용합니다.<br>
아마도 파이썬 뿐만 아니라 다른 언어도 마찬가지 입니다.
> 여러분이 파이썬 3이 아니라 파이썬 2를 사용하고 있다면 `7 / 2` 의 결과가 `3.5`가 아니라 `3`일 것입니다.<br>
> 왜냐하면 파이썬 2에서는 정수 끼리의 나눗셈은 항상 정수가 나오도록 정했기 때문입니다.<br>
> 만약 파이썬 3에서 정수 몫을 구하고 싶다면 `//`를 사용하면 됩니다.

정수 몫을 구해봤으니 나머지도 구해봅시다.
```cmd
>>> 7 % 2
1
```
`7`을 `2`로 나누면 3번 나누고 1이 남습니다.<br>
`%`는 나머지를 구하는 `modulo`연산자 입니다.

파이썬에서는 거듭제곱도 계산할 수 있습니다. 
```cmd
>>> 7 ** 7
823543
```
`7 ** 7`은 7<sup>7</sup>를 의미합니다.

어 ... 혹시 정수만 다루나요? <br>
아니요, 이번엔 실수도 연산해 봅시다. 

```cmd
>>> 4.2 + 1.3
5.5
>>> 4.2 - 1.3
2.9000000000000004
>>> 4.2 / 1.3
3.230769230769231
```
음... 왜 `4.2 - 1.3`이 `2.9`가 아니라 `2.9000000000000004`죠?<br>
컴퓨터가 실수를 표현할때 발생하는 오차 때문입니다.<br>
이번에는 "그냥 오차가 발생하는 구나"정도만 알고 넘어가면 됩니다.<br>
왜 오차가 발생하는지 알고 싶다면 [부동소수점](https://ko.wikipedia.org/wiki/부동소수점)을 검색해 보세요.

저기... 혹시 출력한 값의 형식을 변경할 수는 없나요? 정수를 실수로 또는 실수를 정수로 말이에요.<br>
좋은 질문입니다. 자료형을 변경하는 것을 **형변환**이라고 합니다.<br>
파이썬에서는 `int()`, `float()`같은 함수를 사용해서 형식을 변경할 수 있습니다.<br>
아! 만약 어떤 자료형인지 알고 싶다면 `type()`함수를 이용하면 됩니다.

```cmd
>>> int(3.5)
3
>>> type(3.5)
<class 'float'>
>>> float(3)
3.0
>>> type(3)
<class 'int'>
```

`2 + 3 * 4`의 연산 결과는 어떤가요?<br>
당연히 곱하기와 나누기를 먼저 하니까 `2 + 12`, `14`죠?<br>
그럼 더하기를 먼저 계산하고 싶다면 어떻게 해야하죠?<br>
`( )`괄호를 이용하면 됩니다.<br>
괄호 안의 수식은 어떠한 경우에서든지 우선순위가 가장 높기 때문입니다.
```cmd
>>> 2 + 3 * 4
14
>>> (2 + 3) * 4
20
```

## 변수와 자료형
아니요... 근데 오늘 자료형 배우는 날 아닌가요??<br>
여러분은 이미 알고 있습니다. 자료형이 뭔지 말이죠 다만, 단어가 생소해서 모르고 있을 뿐입니다.<br>
그럼 이렇게 말해봅시다. 정수, 실수, 복소수, 문자열, ...

방금 까지 숫자를 이용한 연산을 공부해온 여러분이라면 숫자형이 무엇을 의미하는지 알 것입니다.<br>
**integer! float-pinting Number! comflex!
```cmd
>>> type(2)
<class 'int'>
>>> type(1.2)
<class 'float'>
>>> type(3 + 2j)
<class 'complex'>
>>>
```

### 변수
대부분의 프로그래밍 언어 수업에서는 변수와 자료형을 함께 공부합니다<br>
왜냐하면 변수를 선언할 때 어떤 자료형을 쓸 것인지 정해 주어야 했습니다.<br>
하지만 파이썬은 그럴 필요가 없습니다. 단순히 이름만 붙여주면 되기 때문입니다.

**변수의 선언**<sup>define variables</sup>은 이름 붙여주기 입니다.<br>
다음과 같이 작성해 봅시다.
```cmd
>>> spam = 2
>>> bacon = 3.5
```
결과 값이 없어도 당황하지 말아요! 그게 정상입니다.<br>
방금 우리는 `2`와 `3.5`에 `spam`과 `bacon`이라는 이름을 붙여주었습니다.<br>
그럼 잘 선언되었는지 확인해 보겠습니다.

```cmd
>>> globals()
{'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <class '_frozen_importlib.BuiltinImporter'>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, 'spa
m': 2, 'bacon': 3.5}
```

### 자료형과 객체
파이썬은 모든 자료형을 객체로 정의합니다.<br>
`type()`함수를 이용해서 방금 선언한 변수의 형<sup>type</sup>을 알아봅시다.
```cmd
>>> type(spam)
<class 'int'>
>>> type(bacon)
<class 'float'>
```

`spam`은 `int`라는 `class`라고 합니다.

자료형이 객체라고 했습니다. 객체나 클레스가 지금은 어떤 의미가 있는지는 자세하게는 몰라도 됩니다.<br>
단순하게 어떤형인지 알려주는게 아니라는 것만 알면 됩니다.

`dir(spam)`을 입력해 보겠습니다.
```cmd
>>> dir(spam)
['__abs__', '__add__', '__and__', '__bool__', '__ce ...중략... or', 'real', 'to_bytes']
```
파이썬의 `int`가 할 수 있는 많은 것을 알 수 있습니다. 

### 자료형( )
위에서 `int()`나 `float()`을 이용했습니다. 해당 자료형으로 변환 해주는 기능도 있는데, 그 자료형을 생성할 수도 있습니다.

```cmd
>>> int()
0
>>> float()
0.0
>>> complex()
0j
```

### More Types
앞에서 설명한 숫자 자료형 외에도 여려가지 자료형이 있습니다.<br>
`str`, `list`, `tuple`, `bool`, `dict`, `set`<br>
간단하게 어떤 자료형인지만 알고 넘어가도록 하죠. 왜냐하면 이 자료형마다 하나의 강의가 필요합니다.
뭐,, 정확히 따지자면 자료형이 아니라 자료 구조라고 해야 맞습니다.<br>
`bool`을 제외하면 각각의 자료에 특별한 기능이 추가되어 있기 떄문이죠<br>
어... 파이썬은 모든 자료형이 객체라서, 여기선 자료 구조라고 해야 할 까요 ㅎㅎ

#### str
문자열<sup>String</sup> 자료형 입니다. 단어 그대로 문자들의 연결이죠.<br>
파이썬에서는 다음과 같이 작성합니다.

```cmd
>>> 'Hello, Python`
'Hello, Python'
```
하나의 문자도 문자열입니다.
```cmd
>>> type('A')
<class 'str'>
```
C언어는 ASCII Code를 통해 문자를 정수로 표현했습니다.<br>
그래서 'A' + 3 이라는 재미난 일도 할 수 있죠.<br>
하지만 파이썬에서는 안됩니다. 문자가 아니라 문자열 이기 때문이죠<br>
```cmd
>>> 'A' + 3
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
```
문자열 끼리도 더할 수 있나요?<br>
네 물론 곱하기도 됩니다!!
```cmd
>>> 'Hello' + 'World'
'HelloWorld'
>>> '=' * 30
'=============================='
```
프로그램을 실행할 때마다 다른 문자열을 출력하고 싶어요!<br>
오,, 문자열 포멧팅을 사용하면됩니다.

다음은 문자열 포맷팅의 3가지 방법입니다.
1. 포멧코드 이용하기<br>
  `%`기호를 사용해서 만드는 포멧 코드는 C언어의 `printf()`, Java언어의 `System.out.printf()`에서 사용해 봤을지도 모릅니다.<br>
  다음은 문자열 포멧 코드입니다.
  - `%s`	문자열(String), object -> `%s`에 들어오는 모든 object를 문자열로 만들어줍니다.
  - `%c`	문자 1개(character)
  - `%d`	10진수(decimal)
  - `%f`	부동소수점수(floating-point number)
  - `%o`	8진수(octal)
  - `%x`	16진수(hexadecimal)
  - `%%`	character %
  이 문자열 포멧 코드를 이용해 우리는 다음과 같이 쓸 수 있습니다.<br>
  `'%d, %f' % (decimal, n_float)`이 문장은 10진수와 부동소수점수를 문자열로 만들어줍니다.
2. format 함수사용하기
  `str.format(*args, **kwargs)`함수를 사용하면 됩니다.
  ```cmd
  >>> 'bp is {systolic} and {diastolic}'.format(systolic=120, diastolic=80)
  'bp is 120 and 80'
  >>> '{} {} {}'.format('apple', 'pie', 3)
  'apple pie 3' 
  ```
3. f 문자열
  3.6버전 이상부터는 f'str'을 사용할 수 있습니다.<br>
  f-string은 표현식을 지원하기 때문에 계산식도 넣을 수 있습니다.<br>
  `f'3 + 5 = {3 + 5}'`같이 `{ }`안에 표현식이나 변수를 넣으면 문자열로 변환 해 줍니다.<br>
모두 종합해서 한번에 써보겠습니다.
```python
if __name__ == '__main__':

    integer = 10
    floating-point = 3.5
    comflex = (3 + 2j)
    
    print("%d", % integer)
    print(f'{floating-point}')
    print('{}'.format(comflex))
```
#### list
리스트는 모음입니다. 숫자의 모음이 될 수도 있고, 객체의 모음이 될 수도 있죠.<br>
심지어는 리스트의 모음이 될 수도 있습니다. ~~음, 그럼 모음의 모음인가요~~

리스트의 선언은 다음과 같이 합니다.
```cmd
LIST_NAME = [OBJECT1, OBJECT2, OBJECT3, ...]
```

그러면 모음을 생성해 보곘습니다.
```cmd
>>> list1 = []
>>> list2 = [2, 4, 6, 8, 10]
>>> list1 = ['KonKuk', 'Computer', 'Associate']
>>> list1 = [1, 3, [5, 7, 9], 10]
```

리스트의 각 요소를 불러올 때는 Index를 사용합니다. 문자열이나 튜플도 다음과 같이 불러올 수 있습니다.<br>
리스트와 문자열, 튜플은 모두 순서가 있는 자료이기 떄문입니다.<br>
다음의 방법을 통해 요소를 불러와 봅시다.

```cmd
>>> string = ['H', 'e', 'l', 'l', 'o', ',', ' ', 'K', 'C', 'A']
>>> string[3]
'l'
>>> string[-2]
'C'
>>> string[2:5]
['l', 'l', 'o']
```
`[ ]`기호를 통해 요소를 불러 올 수 있습니다.<br>
하나를 불러올 수도 있고, 여러개를 한번에 불러올 수도 있습니다.<br>
요소 하나를 불러오면 타입은 요소의 타입이 되고, 여러개를 불러오면 리스트 타입이 됩니다.

인텍스는 처음부터 `0`으로 시작하고 마지막부터 `-1`로 시작합니다.

|'H'|'e'|'l'|'l'|'o'|','|' '|'K'|'C'|'A'|
|--|--|--|--|--|--|--|--|--|--|
|0|1|2|3|4|5|6|7|8|9|
|-10|-9|-8|-7|-6|-5|-4|-3|-2|-1|

길이를 구하고 싶다면 다음과 같이 하면 됩니다.
```cmd
>>> len(string)
10
```
#### tuple
튜플은 리스트와 굉장히 유사합니다.
요소를 수정할 수 없다만 빼고 말이죠.
```cmd
>>> t1 = (1, 2, 'a', 'b')
>>> del t1[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object doesn't support item deletion
>>> t1[0] = 3
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
문자열이나 리스트처럼, 요소를 추출할 수도 있고.<br>
더하거나 곱할수도 있습니다. 길이를 구하는 것도 같습니다.<br>
단지 요소를 수정할 수만 없을 뿐이죠.

#### bool
`bool`은 `True`나 `False`를 나타내는 자료형입니다. 참 혹은 거짓 둘 중 한 가지만 가질 수 있죠<br>
```cmd
>>> t = True
>>> f = False
```
`bool`은 조건 연산의 결과 값으로 사용됩니다. 조건연산은 다음과 같이 합니다.

- `==`: equals
- `!=`: not equals to
- `<`: less than
- `>`: greater than
- `<=`: less than or equal to
- `>=`: greater than or equal to

직접 해보겠습니다.

```cmd
>>> 3 == 2
False
>>> 3 != 2
True
>>> 1 < 3
True
```

참과 거짓을 나타내는 값에 `bool`만 있는 것은 아닙니다.<br>
`0`이 혹은 비어있는 것은 `True`이고 아닌 것은 `False`입니다.

`int()`, `list()`같이 비어있는 혹은 자료형의 기본값은 거짓이고 아닌 것은 참입니다.
```cmd
>>> bool(list())
False
>>> bool(int())
False
>>> bool(1)
True
```
#### dict
단어사전을 생각해봅시다. 각각의 단어에는 각각의 뜻이 있습니다.<br>
`dict`도 마찬가지죠 `key`와 `value`가 쌍을 이루고 있습니다.
```
DICTIONARY = {Key1:Value1, Key2:Value2, Key3:Value3, ...}
```
딕셔너리를 생성하고 사용해 봅시다.
```cmd
>>> dic = {'apple': '사과', 'KCA': 'KonKuk Computer Associate'}
>>> dic['apple']
'사과'
>>> dic.keys()
dict_keys(['apple', 'KCA'])
>>> dic.values()
dict_values(['사과', 'KonKuk Computer Associate'])
>>> dic.items()
dict_items([('apple', '사과'), ('KCA', 'KonKuk Computer Associate')])
```
#### set
우리는 중학교 시절에 집합을 공부했습니다.<br>
집합의 사전적 정의는 다음과 같습니다. **특정한 조건에 맞는 원소들의 모임**이다.

집합을 이루는 조건에는 다음과 같습니다.
- 중복을 허용하지 않는다.
- 순서가 없다.

리스트나 튜플은 순서가 있지만 집합은 없기 때문에 인덱싱이나 슬라이싱으로 값을 구할 수는 없습니다.<br>
하지만 집합연산은 할 수 있죠. **교집합, 합집합, 차집합** 같은거 말입니다.

- `&`: intersection 
- `|`: union
- `-`: difference
다음과 같이 선언된 집합이 있다고 생각해 봅시다.
```cmd
>>> s1
{1, 2, 3, 4, 5, 6}
>>> s2
{4, 5, 6, 7, 8, 9}
```
이 집합에 각각의 연산을 해봅시다.
```cmd
>>> s1 & s2
{4, 5, 6}
>>> s1 | s2
{1, 2, 3, 4, 5, 6, 7, 8, 9}
>>> s1 - s2
{1, 2, 3}
```
연산자가 아니라 집합이 가지고 있는 함수를 사용해도 됩니다.
```cmd
>>> s1.intersection(s2)
{4, 5, 6}
>>> s1.union(s2)
{1, 2, 3, 4, 5, 6, 7, 8, 9}
>>> s1.difference(s2)
{1, 2, 3}
```

## 좀 더 알아보기
파이썬이 기본으로 제공하는 여러 함수가 있습니다. 당장 `print()`를 알고 있을 것입니다.<br>
만약 모르는 것이 나타나면 그때 그때 찾아봐야 할 것입니다.<br>
파이썬에게 물어보는 방법도 있죠.

`help([object])`를 사용해서 물어보면 됩니다.<br>
여러분이 `help`를 호출하면 파이썬에 있는 도움말 시스템을 불러옵니다.<br>
`object`가 `str`이면 문자열은 모듈, 함수, 클래스, 메서드, 키워드 또는 설명서 주제의 이름으로 검색합니다.<br>
다른 종류의 객체라면, 그 객체에 대한 도움말 페이지가 만들어집니다.
```cmd
>>> help(int)
Help on class int in module builtins:

class int(object)
 |  int([x]) -> integer
 |  int(x, base=10) -> integer
 |
 |  Convert a number or string to an integer, or return 0 if no arguments
 |  are given.  If x is a number, return x.__int__().  For floating point
 |  numbers, this truncates towards zero.
:
```

아니면 [파이썬 공식 Reference 문서](https://docs.python.org/3/reference/index.html)를 읽어도 됩니다.

## 과제
태양계에서 행성이 가지는 특성을 자료형을 이용하여 저장했다가 출력하는 프로그램을 만들어 보아요.<br>
태양과의 거리, 태양계의 행성들, 자전이나 공전주기, 중력가속도 등 원하는 것을 한가지 골라 프로그램을 만들어 보세요.

`input(prompt)` 는 prompt를 먼저 출력하고 사용자의 입력을 받습니다.<br>
사용자가 작성한 값은 문자열로 입력되기 때문에 적절히 형변환하여 사용할 수 있습니다.

다음은 예시 입니다.
```python
def show_menu():
  print('+==================================================+')
  print('+1. Distance to the sun  2. Planets of Solar-sytem +')
  print('+3. Rotation_period      4. Revolution_period      +')
  print('+5. Gravitational_acceleration                     +')
  print('+0. Quit Programm                                  +')
  print('+==================================================+')


if __name__ == '__main__':
  print('-------------- the Solar System INFOMATION --------------')
  show_menu()
  selected = input('select menu: ')
  print(f'slected menu is {menu}')

```
program을 완성해서 PR 보내주시면 코드 리뷰 하겠습니다.
