기숙사에서 UQ 센터로 가는 도중 길을 잃은 당신은 우연히 대학 지하의 비밀 동굴 입구를 찾게 되었다. 입구는 `N` 개의 연속된 문으로 이루어진 경비 시스템으로 막혀 있는데, 각 문은 차례대로 놓여 있고, 총 `N` 개의 스위치 중 하나와 연결되어 있다. 각 스위치는 정확히 하나의 문에만 연결되어 있다.

<center>

![동굴의 모습](https://s3.ap-northeast-2.amazonaws.com/oj.uz/old/IOI13_cave/pic1.png?dl=1)

</center>

문은 차례대로 `0`, `1`, ..., `(N - 1)` 로 번호가 매겨져 있고, 0번 문이 가장 앞에 있다. 스위치도 `0`, `1`, ..., `(N - 1)` 로 번호가 매겨져 있지만, 어느 스위치가 어느 문에 연결되어 있는지는 주어지지 않는다.

모든 스위치는 동굴 입구에 있다. 각각의 스위치는 위나 아래로 설정될 수 있다. 각 스위치마다 이 둘 중 하나만 정답이며, 스위치를 정답 위치에 놓으면 이 스위치와 연결된 문이 열린다. 만약 스위치를 오답 위치에 놓으면 이 스위치와 연결된 문은 닫힌다. 스위치마다 정답은 다를 수 있으며, 어느 위치가 정답인지는 주어지지 않는다.

당신은 이 경비 시스템을 이해하고 싶다. 이를 위해서, 스위치를 임의의 조합으로 설정한 후 동굴 안으로 걸어가서 처음으로 닫혀 있는 문이 무엇인지를 알 수 있다. 문은 투명하지 않기 때문에, 첫 번째 닫혀 있는 문 이후의 상태는 알 수 없다.

스위치 조합은 최대 `70,000` 번 시도해볼 수 있다. 당신의 임무는 각 스위치의 정답 위치를 찾고, 또 어느 스위치가 어느 문에 연결되어 있는지를 알아내는 것이다.

### 구현

다음 조건을 만족하는 함수 `exploreCave()`를 구현한 파일을 제출해야 한다. 이 함수는 그레이더 함수 `tryCombination()`을 최대 70,000번 호출할 수 있고, 그레이더 함수 `answer()`를 호출하는 것을 마지막으로 종료해야 한다. 이 함수들은 다음과 같이 정의된다.

#### 그레이더 함수 : `tryCombination()`

```
int tryCombination (int S[]);
```

##### 설명

이 함수는 그레이더에 포함되어 있다. 이 함수는 스위치 조합을 테스트해보고, 그리고 동굴에 들어가서 처음으로 닫혀 있는 문의 번호를 알려준다. 만약 모든 문이 열려 있다면 `-1`을 리턴한다. 이 함수는 `O(N)` 시간에 동작한다. 즉, 실행 시간은 최악의 경우에도 `N`에 비례한다.
이 함수는 최대 `70,000` 번 호출될 수 있다.

##### 파라미터

* `S` : 각 스위치의 상태를 나타내는 길이 `N` 인 배열. `S[i]` 는 `i` 번 스위치에 해당한다. 이 값이 `0`이면 이 스위치가 위로 되어 있음을, `1`이면 이 스위치가 아래로 되어 있음을 나타낸다.
* 반환값 : 첫 번째 닫힌 문의 번호이며, 모든 문이 열려 있으면 `-1`를 리턴한다.

#### 그레이더 함수 : `answer()`

```
void answer (int S[], int D[]);
```

##### 설명

모든 문을 열 수 있는 스위치의 조합과, 각 스위치가 어느 문에 연결되어 있는지를 알아내면 이 함수를 호출하시오.

##### 파라미터

* `S` : 길이 `N` 의 배열로, 각 스위치의 정답 위치를 나타낸다. 포맷은 위에서 설명한 `tryCombination()` 함수와 같다.
* `D` : 길이 `N` 의 배열로, 각 스위치가 어느 문에 연결되어 있는지를 나타낸다. 보다 자세하게, `D[i]` 는 스위치 `i` 가 연결된 문의 번호를 저장한다.
* 반환값 : 이 함수는 반환값이 없지만, 호출되면 프로그램이 종료하게 된다.

#### 구현해야 하는 함수 : `exploreCave()`

```
void exploreCave (int N);
```

##### 설명

이 함수를 구현하여 제출해야 한다.

이 함수는 각 스위치의 정답 위치와 각 스위치가 연결된 문을 알아내기 위해서 그레이더 함수 `tryCombination()`를 이용해야 하며, 이 정보를 알아내면 `answer()` 함수를 호출해야 한다.

##### 파라미터

* `N` : 동굴에 있는 스위치와 문의 수

### 예제 세션

문과 스위치가 위 그림처럼 주어졌다고 하자.

<table class="table table-bordered">
 <tr>
  <th style="width: 35%;">Function Call</th>
  <th style="width: 15%;">Returns</th>
  <th>Explanation</th>
 </tr>
 <tr>
  <td><code>tryCombination([1, 0, 1, 1])</code></td>
  <td><code>1</code></td>
  <td>앞의 그림에 해당한다. 스위치 0, 2, 3은 아래로 되어 있고 1은 위로 되어 있다. 이 함수의 리턴값은 1인데, 이는 왼쪽부터 봤을 때 1번 문이 닫혀 있는 첫 번째 문이라는 뜻이다.</td>
 </tr>
 <tr>
  <td><code>tryCombination([0, 1, 1, 0])</code></td>
  <td><code>3</code></td>
  <td>문 0, 1, 2가 모두 열려있고, 3이 닫혀 있다.</td>
 </tr>
 <tr>
  <td><code>tryCombination([1, 1, 1, 0])</code></td>
  <td><code>-1</code></td>
  <td>스위치 0을 아래로 내리면 모든 문이 열리게 되어 리턴값이 `-1`이 된다.</td>
 </tr>
 <tr>
  <td><code>answer([1, 1, 1, 0], [3, 1, 0, 2])</code></td>
  <td>(프로그램 종료)</td>
  <td>우리가 알아낸 스위치의 정확한 조합은 <code>[1, 1, 1, 0]</code>이고, 스위치 0, 1, 2, 3은 각각 문 3, 1, 0, 2와 연결되어 있다.</td>
 </tr>
</table>

### 제약 조건

* 시간 제한 : 2초
* 메모리 제한 : 32MB
* `1 ≤ N ≤ 5,000`

### 서브태스크

<table class='table table-condensed table-bordered'>
 <tr>
  <th style="width: 10%;">서브태스크</th>
  <th style="width: 10%;">배점</th>
  <th>추가적인 입력 제한 사항</th>
 </tr>
 <tr>
  <td>1</td>
  <td>12</td>
  <td>각 스위치 <code>i</code>는 문 <code>i</code>와 연결되어 있다. 당신은 올바른 스위치 조합을 찾기만 하면 된다.</td>
 </tr>

 <tr>
  <td>2</td>
  <td>13</td>
  <td>올바른 스위치 조합은 항상 <code>[0, 0, 0, ..., 0]</code>이다. 당신은 어느 스위치가 어느 문에 연결되어 있는지만 알아내면 된다.</td>
 </tr>
 <tr>
  <td>3</td>
  <td>21</td>
  <td><code>N ≤ 100</code></td>
 </tr>
 <tr>
  <td>4</td>
  <td>30</td>
  <td><code>N ≤ 2,000</code></td>
 </tr>
 <tr>
  <td>5</td>
  <td>24</td>
  <td>(없음)</td>
 </tr>
</table>

### 테스트용 입력 형식

[여기](https://s3.ap-northeast-2.amazonaws.com/oj.uz/old/IOI13_cave/cave.zip?dl=1)에 주어지는 샘플 그레이더는 입력을 파일 cave.in에서 읽어들이는데,
포맷은 다음과 같아야 한다.

* line 1: `N`
* line 2: `S[0] S[1] ` ... `S[N - 1]`
* line 3: `D[0] D[1] ` ... `D[N - 1]`

여기서 `N`은 문과 스위치의 수이다. `S[i]`는 스위치 `i`의 정답 위치이며, `D[i]`는 스위치 `i`가 연결된 문이다.

예를 들어, 위의 예시는 다음와 같은 형식을 따라야 한다.

<pre>
4
1 1 1 0
3 1 0 2
</pre>

### 프로그래밍 언어 유의사항

<table class="table table-condensed table-bordered">
 <tr>
  <th style="width: 15%;">C/C++</th>
  <td><code>#include "cave.h"</code>를 해야 한다.</td>
 </tr>
 <tr>
</table>

예시를 위해서 솔루션 템플릿을 참조하시오.