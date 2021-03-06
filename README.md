---
description: '" 컴퓨터 과학의 기본적인 정의는 문제해결을 위한 학문이다 " -David J. Malan-'
---

# 컴퓨터 내부의 언어체계



### 기본 배경 <a href="#undefined" id="undefined"></a>

인간은 의사소통하기 위해서 언어를 사용해왔습니다. 전 세계에 많은 언어가 존재하지만 의사소통이 가능한 이유는 지칭하는 어떤 것의 문맥은 동일하기 때문입니다. 문맥이란 ‘TIME’과 ‘시간’이 모습은 다르지만 의미는 같은 것을 의미합니다.

컴퓨터가 사용하는 언어, 즉 기계어 또한 인간이 만들어낸 컴퓨터 언어에 불과합니다. 사람들은 기계와 자연어가 같은 문맥을 사용한다면 충분히 의사소통이 가능할거라 생각했고 오랜시간에 걸쳐 이를 되게끔 만들었습니다. 오랜 시간동안 언어가 진화해왔던 것 처럼 인간은 끝없이 문제를 해결했으 오늘날 컴퓨터 언어를 만들었습니다.

우리가 사용하는 자연어는 기호 혹은 자음과 모음으로 문자를 구성합니다. 한자리의 표현을 상자에 담는다고 표현하겠습니다. 컴퓨터 또한 비트(_binary digit_)라고 부르는 2진 숫자를 사용하여 아주 적은 비용으로 컴퓨터는 상자에 담을 수 있습니다. 10진수를 사용하는 자연어와 달리, 컴퓨터가 이러한 체계를 사용하는 이유는 트랜지스터에 전원을 공급하여 스위치를 켜고 끄는 이 일련에 작업 매우 단순하기 때문입니다. **비트를 통해 우리가 평소 사용하는 텍스트, 이모티콘, 동영상, 소리 그리고 더 복잡한 데이터를 표현할 수 있습니다.**

****

****

### 논리연산 <a href="#undefined" id="undefined"></a>

비트는 1과 0만을 사용할 수 있는 2진법이지만 논리연산과 NOT, AND, OR연산으로 계산할 수 있습니다. 또한 XOR과 드모르간 법칙을 적용할 수 있습니다. XOR은 서로 다른 논리의 계산을 TRUE로 반환, 같은 값은 FALSE로 반환하는 계산식입니다. 드모르간 법칙은 수학자 드모르간이 발견한 법칙으로 a AND b는 NOT(NOT a OR NOT b)와 같다는 것을 증명합니다.

흥미로운 것은 XOR과 드모르간 법칙의 증명으로 연산은 다른 연산으로 치환할 수 있다는 것입니다. AND 는 OR로 변경할 수 있고 XOR도 NOT, AND, OR의 조합으로 바꿀 수 있습니다. 컴퓨터로 작업하다보면 원하는 값을 인풋으로 못받는 경우가 분명 있기 때문에 이러한 성질은 매우 유용합니다.

{% hint style="danger" %}
_"부정논리, NOT연산을 연속으로 쓰는 것은 효율성이 많이 떨어집니다. 연산을 추가적으로 사용하기 때문에 최소한으로 사용하는 것이 좋습니다. 또한 전달력에서도 좋은 방법은 아닙니다. 야식 안먹을려고 했는데 안먹을 수가 없었다는 야식 먹었다는 소리자나요 ㅎㅎ 동등한 연산이면 간단하게 계산하는 것이 여러방면에서 좋습니다."_
{% endhint %}





### 정수를 비트로 표현하는 방법

수는 논리보다 더 복잡하지만 단어보다는 훨씬 단순합니다. 우리는 보통 10진수 체계를 사용하여 10가지 기호를 한자리를 표현합니다. 1000(10\*\*3 + 10\*\*2 + 10\*\*1 + 10\*\*0)처럼 표현하는 것을 base10 시스템이라 말합니다. 비트를 사용해 값을 만들 때도 이와 비슷하게 접근할 수 있습니다. 2진수에서는 기호가 2개이기 때문에 각 상자의 자릿수는 2의 거듭제곱이며, 따라서 2진수 체계는 10을 밑으로 하지않고 2를 밑으로 하는 시스템입니다.

$$
1001110100100 =1*2**12 + 0*2**11 + ... + 0*10**0 =5,028
$$

5028을 2진체계로 표현했을 때 13개의 비트가 사용되었습니다. 하지만 실제 컴퓨터에서는 0001001110100100의 모습으로 보여지는데 그 이유는 **컴퓨터가 미리 정해진 수의 비트를 한 덩어리로 사용하도록 만들어 졌기 때문**입니다. 그래서 항상 일정한 개수의 비트를 사용해 값을 표현하는 경우가 있습니다. 이때 유효하지않은 비트에 0을 리딩제로라하고 가장 오른쪽의 비트를 LSB, 왼쪽 비트를 MSB라 축약하여 부르기도 합니다.

{% hint style="info" %}
" 10진수를 2진수로 표현하는 또다른 방법은 2진 코드화한 10진수(BCD)로 변환하는 것입니다. 예를들어, 12를 2진수로 표현하면 1100이지만 BCD를 이용하면 0001 0010로 나타낼 수 있습니다. 하지만 이 방법은 4비트로도 충분히 나타낼 수 있는 수를 8비트로 표현하기에 배우 비효율적이라 이런 시스템은 잘 사용하지 않습니다.
{% endhint %}





### **덧셈과 음수표현**

비트도 정수처럼 덧셈, 음수표현, 실수표현이 가능합니다. 비트 덧셈에서 기억해야할 것은 비트를 서로 더한 결과는 XOR한 값과 같습니다. 또 덧셈 결과가 우리가 사용할 비트의 개수로 표현할 수 있는 범위를 벗어나면 **오버플로**가 발생합니다.

{% hint style="info" %}
_"오버플로란 MSB에서 올림이 발생했다는 의미이기도 합니다. 이 결과는 조건 코드 레지스터에 오버플로 비트에서 확인할 수 있습니다."_
{% endhint %}

지금까지 4비트로 0부터 15까지 16가지 수를 표현했지만 4비트로 수를 16가지만 표현할 수 있다는 말이 꼭 0에서 15까지만 표현할 수 있다는 뜻은 아닙니. 조금 새로운 방법으로 표현한다면 비트의 한자리를 부호의 상태를 표현하는 것에 쓰고 나머지를 숫자로 여기는 방법입니다. 이로인해 15가지 음수와 양수를 표현할 수 있습니다. 하지만 이것이 16가지의 숫자가 아니라는 점에 유의해야 합니다. <mark style="color:yellow;">**이런 방법을 부호와 크기 표현법이라고 합니다. 이 표현법이 사용되지 않는 2가지 이유는 첫 째, 0을 표현하는 방법이 두가지라서 비용이 낭비됩니다. 둘째, XOR과 AND를 통한 계산을 했을 때 +1 AND -1은 0이 아니라 -2가 됩니다.**</mark>

$$
+7,+6,+5,+4,+3,+2,+1,+0,-0,-1,-2,-3,-4
$$

음수를 표현하는 또 다른 방법은 양수의 모든 비트를 반대로 뒤집는 방법입니다. 이런 방법은 **1의 보수 표현법**이라고 입니다. 0000(+1)을 뒤집 1111(-1)로 얻을 수 있음을 알 수 있습니다. 이 방법 또한 부호와 크기표현법 처럼 부호를 표현하는 비트와 값을 표현하는 비트가 나눠져 있으며 +7\~-7까지의 수를 표현합니다. 마찬가지로 0을 표현하는 방법이 2가지로 나타내는 문제가 여전히 존재합니다. 하지만 덧셈연산을 가능한데 이는 조금 복잡한 방식입니다. 0010(+2)와 1110(-1)을 더했을 때 발생하는 오버플로값을 추가적으로 더하면 정상적인 덧셈의 결과를 반환합니다. 추가적인 연산을 수행해야하므로 현대의 컴퓨터에서는 사용하지 않는 방식입니다.

하드웨어의 추가가 없고 하나의 0의 표현만 가능한 방법을 **2의 보수 표현법**이라고 합니다. 원리는 연산할 두 값의 결과가 0이 나오는 비트를 찾는 것입니다. 0001(+1)이 0000이 될 수 있는 방법은 간단합니다. 값을 뒤집어 1을 더하면 1111(-1)의 값을 얻을 수 있습니다. 이렇게 계산할 때 발생하는 올림은 무시합니다.

{% hint style="warning" %}
_"이처럼 각각의 방법을 사용했을 때, 2진수 1111은 2의 보수에서는 -1이지만 부호와 크기 표기로는 -7이고 1의 보수에서는 -0인 것을 알 수 있습니다. 사용하는 표현법에 따라 달라짐을 꼭 인지하고 있어야합니다."_
{% endhint %}

__

__

### 실수 표현

밑이 10인 실수에는 10진 소수점이 포함됩니다. 밑이 2인 경우에도 2진 소수점을 표현할 방법이 필요합니다. 이전에 여러가지 방법으로 음수를 표현했던 것처럼 문맥에 따라 실수를 표현하는 방법이 달라질 수 있습니다.

첫 번째 실수 표현 방법 4비트 중에서 2비트는 정수를 나타낼 때 사용하고 나머지 2비트는 실수를 표현하는데 사용합니다. 이 경우, 소수점의 위치가 항상 일정하기 때문에 이 방식을 **고정 소수점 표현법**이라합니다.

{% hint style="info" %}
_" 10진 체계에서는 1/10, (1/10)\*\*2, ... , (1/10)\*\*n 사용하지만 2진 체계에서는 2의 거듭제곱을 분모로 사용합니다. 1/2, (1/2)\*\*2, ... , (1/2)\*\*n "_
{% endhint %}

4비트를 실수를 표현하는데 사용한다면 분수 부분을 표현하는 방법은 4가지가 될 수 있습니다. 이런 접근 방법이 잘 작동하긴 하지만 00(0) ,01(1/4), 10(1/2), 11(3/4)의 구성으로 쓸모있는 실수를 표현하기는 제한적일 수 밖에 없습니다.&#x20;

일반적인 문제를 해결하기하려면 넓은 범위의 수를 다룰 수 있어야합니다. 예를 들어, 물리학에서 사용하는 범위인 플랑크 상수에서부터 아보가르드로 수까지의 실수표현을 위해서는 대략 191비트가 필요합니다. 모든 수를 몇백 비트로 표현하면 메모리 비용이 너무 많이들기때문에 고정소수점은 적절한 표현방법이 아닙니다.

다른 방법은 **실수에 과학적 표기법을 적용하는 것입니다. 이 방법은 0.0012처럼 모든 자리의 0의 자리를 표현하는 것이 아니 1.2\*10^3처럼 사용하는 것입니다. 지수를 바꾸어 소수점을 이동시키는 이 방법을 부동소수점 표현법이라고 합니다.** 4비트를 사용할 때, 2자리는 소수점 한자리를 표현하는 가수를 위해 사용하고 나머지 2자리는 지수(2^n)로 사용합니다.&#x20;

$$
0110 = 1/2*2^2 = 2.0 , 1001 = 1*2^1 = 2.0,   1110 = 1/2 * 2^2 = 6.0
$$

​부동 소수점으 0000\~1111값을 표현했을 때 아주 비효율적인 것을 확인할 수 있습니다. 예를 들어 0을 표현하는 방법은 4가지나 되고 1.0, 2.0, 4.0을 표현하는 방법도 두가지씩있습니다. 또한 지수가 커질 수록 가수의 한 패턴과 다른 패턴 사이의 값의 차이가 커집니다.

사실 부동소수점 수 시스템은 컴퓨터에서 계산을 수행할 때 실수를 표현하는 표준방법입니다. 예시보다 훨씬 더 많은 비트를 사용하며 가수와 지수에 대해 각각 부호 비트를 사용합니다. IEEE 754라는 표준은 앞에 다뤘던 비효율적인 부분을 최소화하기 위한 다양한 기능을 정의합니다. 대표적으로 정밀도를 높이는 정규화가 있습니다.

더욱 넓은 범위를 표현하기 위해서 2가지 방법이 사용되는데 하나는 32비트를 사용하는 기본정밀도, 62비트를 사용하는 더블 정밀도 부동소수점 수입니다. 몇가지 특징에 대해서 살펴보면, 두배 정밀도는 기본 정밀도에 비해서 지수는 3비트가 더 크며 가수는 무려 29비트 더 큽니다. 지수의 부호를 표현하는 값은 따로 없지만 편향된 지숫값을 사용하여 이를 표현합니다. 또한 0으로 나눴을 때 양의 무한대 또는 음의 무한대를 나타내는 여러가지 특별한 비트패턴을 제공합니다.

{% hint style="info" %}
_" NaN(not a number) 또한 IEEE754에서 제공하는 특별한 값입니다. 부동소수점 수로 계산하던 도중에 NaN이 생기면 잘못된 산술연산을 수행했다는 뜻입니다. 이러한 특별한 비트 패턴들은 특별한 지숫값을 사용합니다. 지수의 비트가 모두 0또는 1일때 특별한 의미를 갖게 하고 편향된 지수값을 사용하였습니다. 이 의미는 지수값의 범위 0\~254의 표현을 -126 \~ +127범위 표현하게 함으로서 지수의 부호가 필요없게 되었습니다._
{% endhint %}





### 문자를 표현하는 방법

예전에는 문자를 코드로 표현할 때 한 바이트안에 들어가도록 표현했습니다. 수와 마찬가지로 문자를 표현하는 방법의 경우에도 몇 가지 방법이 있습니다. 가장 초기에는 미국 표준 코드(ASCII)가 모든 기호에 대해 7비트 수 값을 할당했습니다. 65(A)\~90(Z), 97(a)\~122(z)을 보면 알파벳을 표현하기에는 충분했습니다. 상당 기간 표준 역할을 했지만 컴퓨터가 널기 쓰이게 됨에 따라 그 밖의 언어를 지원해야 할 필요성이 점차 늘어나게 되었습니다.

국제 표준화 기구(ISO)는 아스키를 확장하여 다른 나라의 문자를 표현하기위해 다양한 표준을 도입했습니다. 이렇게 각기다른 표준이 존재하는 이유는 비트가 지금보다 더 비싼 시절에 표준이 만들어 졌었고 모두 7,8비트에 욱여넣을 수 밖에 없었기 때문입니다.&#x20;

비트 가격이 떨어짐에 따라 유니코드라는 새로운 표준이 만들어졌고, 문자에 16비트 코드를 부여했습니다. 하지만 현재에는 그것마저 부족하여 앞으로 모든 문자를 표현하기위해 21비트로 확장되었습니다.

{% hint style="info" %}
" 가장 많이 쓰는 아스키코드의 경우 8비트면 충분한데 굳이 16비트를 사용해야하는 걸까? UTF-8 인코딩은 데이터의 아스키 문자를 8비트로 변환하고 아스키를 받아서 처리하는 프로그램이 깨지지 않는 방법으로 문자를 인코딩합니다. 아스키 데이터를 인코딩할 때 추가적인 공간을 사용하지 않는 방법입니다.
{% endhint %}

지금까지는 숫자체계를 사용하여 문자를 표현하였습니다. 반대로 문자를 사용하여 수를 표현할 수 있습니다. 베이스64인코딩은 3바이트 데이터를 4문자로 표현합니다. 이렇게 표현하였을 때 특정 문자들의 기능덕분에 다양한 표현이 가능하게 되었습니다. 만일 기능적으로 사용하지않고 문자의 의미 그대로 나타내려면 어떻게 해야할까요? URL인코딩은 %뒤에 어떤 문자의 16진 표현을 덧붙이는 방식으로 기능을 제거한 문자를 인코딩합니다. 예를 들어, 문자 ' / ' 는 %2F로 대신하고 '%' 는 %25로 나타냅니다.

