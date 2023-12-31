### 3장 : 다른 개발자와 코드 계약
자신이 작성한 코드로 작업할 다른 개발자에 대해 생각하는 것이 중요하다는 점을 강조한다.
<br/>
또한, **코드 계약**(code contract)과 이러한 계약에 대해 신중하게 생각하는 것이 어떻게 버그를 예방할 수 있는지 논의한다.
- 다른 개발자들이 코드와 어떻게 상호작용하는지
- 코드 계약과 코드 계약의 세부 조항
- 세부 조항을 최소화하는 것이 어떻게 오용과 예측을 벗어나는 코드를 예방하는 데 도움이 되는지
- 세부 조항을 피할 수 없다면 체크와 어서션을 어떻게 사용할 수 있는가?

소프트웨어를 작성하고 유지보수하는 일은 대개 팀 단위에서 수행하는 작업이다. 소프트웨어를 만드는 회사는 일반적으로 개발자를 여러 명 고용한다.
두세 명으로 이루어진 팀이 하나의 소프트웨어에 대해 작업하는 경우도 있고, 수백 가지 다른 제품에 대해 수천 명의 개발자가 작업할 수도 있다. 정확한 숫자는 중요하지 않다.
요점은 자신이 작성한 코드를 다른 개발자가 작업해야 하고, 반대로 다른 개발자가 작업한 코드를 자신이 작업해야 할 때도 있다.

1장에서 소개한 코드 품질의 핵심 요소 가운데 '예측 가능한 코드를 작성하라'와 '코드를 오용하기 어렵게 만들라'라는 두 가지 원칙이 있었다.
이 원칙은 개발자들이 다른 사람이 작성한 코드와 상호작용할 때 일어날 수 있는 일(그리고 잘못될 수 있는 일)과 관련이 있다.
이 장에서는 코드의 중요한 세부 사항을 다른 개발자에게 전달하기 위한 여러 가지 기법에 대해 논의하는데, 어떤 기법은 다른 기법보다 더 신뢰할 수 있다.
그다음 코드 계약 및 숨겨진 세부 조항(small print)의 개념을 사용해서 이 내용을 형식화한다.
이 장의 마지막 두 절에서는 오용과 오해를 쉽게 유발하는 코드의 실제 사례를 살펴보고 코드를 개선하는 방법을 논의한다.
(6장/7장: 이 장의 내용을 바탕으로 더 구체적인 사례 제시)
<br/>

### [요약]
- 코드베이스는 계속 변하고 일반적으로 여러 개발자에 의해 변경된다.
- 다른 개발자가 어떻게 코드를 해석하고 오용할 수 있을지 생각해보고, 이러한 가능성을 최소화하거나 오용이 불가능하게 만드는 방식으로 코드를 작성하는 것이 유용하다.
- 코드를 작성할 때 일종의 코드 계약이 항상 만들어진다. 여기에는 명핵한 항목이나 세부 조항과 같은 내용이 포함될 수 있다.
- 코드 계약의 세부 조항은 다른 개발자가 계약을 준수하도록 하기 위한 방법이지만 신뢰할만한 방법은 아니다.
  보통 더 나은 접근법은 명백한 항목으로 계약의 내용을 전달하는 것이다.
- 일반적으로 컴파일러를 사용하여 계약을 확인하는 것이 가장 신뢰할 수 있는 방법이다. 이것이 가능하지 않을 때, 체크나 어서션을 사용하여 실행 시간에 계약을 확인할 수 있다.
