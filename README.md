# 타입스크립트와 스마트 택배 API를 활용한 배송 조회 서비스


## 구현 배경

데이터의 자료형을 명시하여, 정확한 데이터의 입출력으로 버그 방지하는 것은 타입스크립트의 수많은 장점 중 하나입니다. 이를 적극적으로 활용해 볼 수 있는 서비스를 개발하기 위해, 스마트 택배 API를 활용한 택배 조회 서비스를 구현해보았습니다.


## 사용한 기술들

### map문

배송 정보를 추적하며 분기에 따라 업데이트 되는 json을 가져와, 맵문을 활용하여 출력하였습니다. 사용자가 최신 배송 정보를 최상단에서 볼 수 있도록, slice().reverse()를 활용하여 배열을 뒤집고, 변경된 인덱스 값에 맞춰 CSS 적용 조건 설정을 업데이트 했습니다.

### async와 await
순차적으로 함수를 실행하여, 데이터를 읽고 출력하는 과정에서 생길 수 있는 `undefined(값이 할당되지 않음)` 버그를 미연에 방지했습니다.

### {theme}과 json

사용자가 페이지의 디자인을 자신의 취향대로 커스터마이징 할 수 있도록, 디자인 설정이 들어있는 json을 생성하여 조건부로 출력했습니다.

### type과 interface를 활용한 타입 설정

데이터의 입출력시, 발생할 수 있는 타입 버그를 미연에 방지하기 위해 서비스를 위해 이용되는 모든 프로퍼티에 타입을 설정했습니다.
