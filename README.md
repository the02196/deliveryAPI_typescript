# 타입스크립트와 스마트 택배 API를 활용한 배송 조회 서비스

<img style="width: 100%;" src="./parcel.png" alt="photo" />

## 배포 링크

(현재 배포 이후 데이터 출력이 제대로 되지 않는 버그를 수정 중입니다.)
https://delivery-api-typescript.vercel.app

## 구현 배경

데이터의 자료형을 명시하여, 정확한 데이터의 입출력으로 버그 방지하는 것은 타입스크립트의 수많은 장점 중 하나입니다. 이를 적극적으로 활용해 볼 수 있는 서비스를 개발하기 위해, 스마트 택배 API를 활용한 택배 조회 서비스를 구현해보았습니다.

# 기술 스택

- React
- Typescript
- TailwindCSS
- 스마트택배 API (Sweet-Tracker)
- Postman

## 개발 내용

디자인은 최대한 배제하고 기능만 테스트 하는 식으로 만들어보려고 했으나, 기왕이면 다홍치마라고, 사용자가 페이지 디자인(theme)을 커스터마이징 할 수 있도록 개발해보았습니다. theme은 CSS 설정이 저장된 객체를 직접 생성하여 활용했습니다.</br></br> 
배송 정보를 추적하며 분기에 따라 업데이트 되는 json을 가져와, 맵문을 활용하여 출력해보았는데, 최신 정보가 최하단에 표시되는 문제가 있었습니다. 이를 slice().reverse()를 활용하여 원본을 데이터는 유지한 채, 복사된 배열만 뒤집는 식으로 해결했습니다.</br></br> 
프론트에서 데이터를 읽어오는(get)데 있어, 순차적으로 함수를 실행할 수 있는 것, 즉 콜백의 활용이 아주 필수적인데, async와 await, optional changing 등을 사용해보면서, 이것에 대해 다시 한 번 복습할 수 있어 좋았습니다. </br></br>
또한 서비스에 위해 이용되는 모든 프로퍼티에 데이터 타입을 설정한 뒤, 이런저런 데이터 값을 일부러 잘못 입력하고 타입 에러가 발생하는 것을 보면서, 타입 스크립트의 버그 미연 방지 기능을 한껏 느껴볼 수 있었던 시간이었습니다.

## 개선할 부분

사용자가 택배회사를 고를 때, section과 option 태그로 이루어진 목록에서 일일히 뒤져 찾아야 하는데, 검색 기능을 넣으면 훨씬 편할 것 같습니다. 커스터마이징 된 theme의 상태가 새로고침 했을 때, 유지되어도 좋을 것 같은데, 로컬 스토리지를 활용하면 될 것 같습니다. 추후 리팩토링 해볼 예정입니다.
