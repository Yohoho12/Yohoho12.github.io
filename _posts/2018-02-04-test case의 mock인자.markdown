---
layout: post
title:  "test case의 mock인자"
date:   2018-02-04 17:50:13 +0530
categories: jekyll update
---
## TEST CASE
이번에 새로운 과제로 junit을 이용한 test case를 만들어 line coverage를 70% 이상으로 만들라는 과제를 받았다.
unit 테스트를 해야하기 때문에 mock을 쓰는것이 필요했다.
 when함수를 이용해서 mock 객체가 반응 할수 있도록 설정해주는 부분이 있었는데 anyInt anyString anyObject 같은 함수들을 인자에 넣어 주면 값이 특정 값일 필요가 없는 인자에 대해서 매핑이 되도록 할 수 있다.
```
when(letterMapper.selectReceivedLetters(eq(id), anyInt(), anyInt())).thenReturn(letterList);
```
위와 같은 코드를 선언하면 첫번째 인자가 id이며 두번째, 세번째 인자는 임의의 int 값이기만 하면 정해준 letterList를 반환하게 된다.
주의해야 할 부분은 `eq(id)` 이 부분인데 만약 인자 중 하나라도 any 관련 인자를 넣었다면, 특정 인자를 넣는 부분을`eq()`로 감싸지 않으면 컴파일 에러가 나게되니 주의해야한다.

끝
