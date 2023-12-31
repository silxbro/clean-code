## 7장 : 코드를 오용하기 어렵게 만들라
코드 오용을 어렵게 하여 다른 개발자가 실수로 잘못된 코드나 가정에 위배되는 코드를 작성하기 힘들게 하여 버그 발생 가능성을 최소화하는 방법을 논의한다.
- 코드 오남용으로 인해 버그가 발생하는 방식
- 코드를 오용하기 쉬운 흔항 방식
- 코드를 오용하기 어렵게 만드는 기술

우리가 작성하는 코드는 훨씬 더 큰 소프트웨어 일부분에 불과한다는 점에 대해 3장에서 논의했다. 소프트웨어가 올바르게 작동하려면 서로 다른 코드들이 잘 맞물려 작동해야 한다.
코드가 오용하기 쉽게 작성된다면, 조만간 오용될 가능성이 있고 소프트웨어가 올바르게 작동하지 않을 것이다.

비합리적이거나 애매한 가정에 기반해서 코드가 작성되거나 다른 개발자가 잘못된 일을 하는 것을 막지 못할 때 코드는 오용되기 쉽다.
코드를 잘못 사용할 수 있는 몇 가지 일반적인 경우는 다음과 같다.
- 호출하는 쪽에서 잘못된 입력을 제공
- 다른 코드의 부수 효과 (입력 매개변수 수정 등)
- 정확한 시간이나 순서에 따라 함수를 호출하지 않음 (3장 참조)
- 관련 코드에서 가정과 맞지 않게 수정이 이루어짐

설명서를 작성하고 코드에 대한 사용 지침을 제공하면 이러한 문제를 완화하는 데 도움이 될 수 있다.
그러나 3장에서 살펴봤듯이, 이것들은 코드 계약의 세부 조항이기 때문에 간과되거나 최신 정보가 아닐 수도 있다. 그러므로 코드를 오용하기 어렵게 설계하고 작성하는 것이 중요하다.
이번 장에서는 코드를 쉽게 오용할 수 있는 경우를 살펴보고, 코드를 오용하기 어렵게 만드는 기법을 제시한다.

#### [오용하기 어려움]
오용하기 어렵게(또는 불가능하게) 함으로써 문제를 피하려는 생각은 설계와 제조 분야에서 잘 확립된 원칙이다.
이것의 한 예는 자동자 제조 중 결함을 줄이기 위해 시게오 신고(Shigeo Shongo)가 1960년대에 만든 포카 요케(poka yoke)의 린(lean) 제조 개념이다.
이것은 보다 일반적인 **방어적 디자인**(defensive design) 원칙의 공통적인 특징이다. 오용을 어렵게 만드는 몇 가지 실제적인 예는 다음과 같다.
- 식품 가공기의 많은 디자인은 뚜껑을 제대로 부착해야만 작동한다. 이것은 손가락이 날 근처에 있을 때 실수로 날이 회전하는 것을 방지하기 위한 것이다.
- 소켓과 플러그는 모양이 다르다. 예를 들어 전원 플러그를 HDMI 소켓에 꽂을 수 없다.
- 전투기의 탈출 좌석을 작동시키기 위해 당김 핸들은 다른 항공기 제어장치로부터 멀리 떨어져 있어 우발적으로 작동될 가능성을 최소화한다.
  (오버헤드 당김 손잡이가 있는) 이전 설계에서 손잡이의 위치는 또한 탑승자가 등받이를 곧게 펴도록 하는 행위(탈출 중 부상 위험을 감소시킴)를 의미하므로
  손잡이 위치는 오용을 어렵게 하는 측면에서 두 가지 기능을 동시에 가지고 있었다.

소프트웨어 엔지니어링 분야에서 이 원칙은 API와 인터페이스가 '사용하기는 쉽고 오용하기는 어려워야 한다'는 문장으로 이해되기도 하는데,
EUHM(easy to use and hard to misuse)이라고도 한다.

### [요약]
- 코드가 오용되기 쉽게 작성되고 나면 어느 시점에선가는 오용될 가능성이 크고 이것은 버그로 이어질 수 있다.
- 코드가 오용되는 몇 가지 일반적인 사례는 다음과 같다.
  - 호출하는 쪽에서 잘못된 입력을 제공
  - 다른 코드에서 일어나는 부수 효과
  - 함수 호출 시점이 잘못되거나 올바른 순서로 호출되지 않은 경우
  - 원래의 코드에 연관된 코드를 수정할 때 원래의 코드가 내포한 가정과 어긋나게 수정하는 경우
- 오용이 어렵거나 불가능하도록 코드를 설계하고 구조화하는 것이 종종 가능하다. 이를 통해 버그 발생 가능성이 크게 줄어들고 중장기적으로 개발자의 시간을 많이 절약할 수 있다.
