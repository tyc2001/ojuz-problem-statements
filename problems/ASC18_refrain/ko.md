승현이는 *Windump* media player에 들어갈 새로운 플러그인을 작성하고 있습니다. 이 플러그인의 목적은 각양각색의 노래들에서 후렴구를 발견하는 것입니다.

후렴구가 정확히 어느 부분이라고 말하는 것은 굉장히 어렵기 때문에, 똑똑한 승현이는 이를 찾아내는 수학적인 모델을 만들어냈습니다. 모든 노래는 음(音, note)들이 나열된 것으로 생각할 수 있습니다. 1개 이상의 연속적인 음들을 *연속하는 음*이라고 정의합시다. 연속하는 음의 *반복 값*은 이 배열의 길이에다 노래 전체에서 이 음들이 등장하는 횟수를 곱한 것입니다. 예로 들어, 노래가 "1, 2, 1, 2, 1, 3, 1, 2, 1"일 때 "1, 2, 1"의 반복 값은 9입니다. "1, 2, 1"의 길이가 3이고, 노래 전체에서 "1, 2, 1"이 3번 등장하기 때문입니다.

노래의 *후렴구*는 모든 연속하는 음들 중에서 반복 값이 가장 큰 것입니다.

승현이가 플러그인을 작성하는 것을 도와줍시다. 노래가 주어질 때, 후렴구를 찾는 프로그램을 작성하세요.

### 입력 형식

첫 번째 줄에는 노래에 나오는 음의 수 $n$과 쓰인 음계의 수 $m$ ($1 \le n \le 150,000, 1 \le m \le 10$)이 공백을 사이로 두고 주어집니다. 두 번째 줄에는 노래에 나오는 음들을 나타내는 1 이상 $m$ 이하의 정수 $n$개가 공백을 사이로 두고 주어집니다.

### 출력 형식

첫 번째 줄에 후렴구의 반복 값을 출력합니다. 두 번째 줄에는 후렴구의 길이를 출력합니다. 세 번째 줄에는 후렴구를 출력합니다. 여러 개의 후렴구가 존재한다면, 아무 거나 출력해도 좋습니다.

### 예제

<table class='table table-bordered table-condensed'>
 <thead>
  <tr>
   <th style="width: 50%;">입력</th>
   <th style="width: 50%;">출력</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td class="code-font">9 3<br/>
1 2 1 2 1 3 1 2 1</td>
   <td class="code-font">9<br/>
3<br/>1 2 1</td>
  </tr>
 </tbody>
</table>