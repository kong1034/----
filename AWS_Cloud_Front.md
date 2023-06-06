# AWS CloudFront 란?<br/>
AWS의 CDN(Content Delivery Network) 서비스이다.<br/>
<br/>
<br/>


# AWS 동작 간단 설명<br/>
client의 요청으로 서버에서 받아온 콘텐츠를 캐싱하고 이후 같은 요청이 왔을때, 캐싱 해두었던 콘텐츠를 다시 제공하는 순서로 동작한다.<br/>
<br/>
<br/>


# AWS 장점<br/>
1. 물리적으로 거리가 먼곳에도 빠르게 요청이 가능하다.<br/>
2. 서버의 부하를 낮춰준다.<br/>
<br/>
<br/>


# 어떻게 물리적으로 거리가 먼곳에도 빠르게 요청이 가능할까?<br/>
AWS CloudFront에는 Edge Location 이라는 개념이 있다.<br/>
클라이언트가 요청한 콘텐츠를 캐싱하고 client에게 캐싱된 데이터를 제공해주는 서버들이 여러나라에 퍼저있다.<br/>
클라이언트와 가장 가까운 캐싱서버에 연결되어 빠르게 얻을수있는것이다.<br/>
<br/>
<br/>


# AWS 동작 순서<br/>
1. 클라이언트가 콘텐츠 요청을한다.<br/>
2. CloudFront는 해당 클라이언트에게 적합한 Edge Location으로 라우팅 한다.<br/>
3. Edge Location에서 캐시를 확인하고 사용자에게 반환한다.<br/>
<br/>
<br/>

#### <Regional edge caches에 캐시가 없다면><br/>
1. 캐시가 없다면 가까운 Regional edge caches로 캐시가 있는지 요청한다.<br/>
2. Regional edge caches에도 없으면 CloudFront는 오리진으로 요청한다.<br/>
3. 그리고 오리진에서부터 보낸 순서의 역방향으로 요청한 콘텐츠를 캐시와 함께 전달한다.<br/>

#### <Regional edge caches에 캐시가 있다면><br/>
1. 콘텐츠를 요청한 Edge Location으로 반환한다.<br/>
2. 콘텐츠의 첫번째 바이트가 도착하는 즉시 Edge Location은 사용자에게 반환한다.<br/>
3. Edge Location은 해당 콘텐츠의 캐시를 저장해둔다.<br/>
<br/>
<br/>


# CloudFront의 정적/동적 콘텐츠 처리<br/>

CloudFront는 정적/동적 컨텐츠 모두를 처리한다.<br/>
<br/>

- 정적 콘텐츠<br/>
이미지처럼 굳이 서버가 필요하지 않은 콘텐츠가 정적 콘텐츠에 해당된다.<br/>
<br/>

- 동적 콘텐츠<br/>
서버가 필요한 콘텐츠를 말한다. 가장 대표적인 예로 데이터베이스에서 가져오는 콘텐츠가 동적 콘텐츠라고 생각하면 된다.<br/>
이런 자료를 정적으로 캐싱하게된다면 하나의 콘텐츠를 받는 동안 새롭게 변경되거나 추가되거나 삭제되는 콘텐츠들을 신경쓸수없게된다.<br/>
<br/>

![img](https://github.com/kong1034/Frontend-Theory/assets/19910034/3f0c7260-0c8d-455d-b0c8-a8c80d09f7c1)

콘텐츠의 종류에 따라 분기처리 하여 나눠주면 해결된다.<br/>
<br/>
<br/>


# CloudFront 몇가지 기능<br/>
1. HTTPS 지원<br/>
![img](https://github.com/kong1034/Frontend-Theory/assets/19910034/8a913d6d-ed82-4c72-b169-702a396cfba3)

HTTPS를 위해 웹서버에서 이것저것 할 필요가 없어졌다.<br/>
<br/>


2. 특정 지역 콘텐츠 접근 제한<br/>
![img](https://github.com/kong1034/Frontend-Theory/assets/19910034/ddd03a42-5f6d-4eb5-ad50-5c23037d49ca)

예를 들어 중국쪽에서 해킹공격이 들어왔다. 차단할수있다.<br/>
<br/>

3. Signed URL<br/>
인증된 URL을 받은 특정 사람들에게만 하나의 콘텐츠를 제공해준다.<br/>
<br/>


4. Signed cookie<br/>
인증된 쿠키를 이용하여 특정 사람들에게만 다수의 콘텐츠를 제공해줄수있다.<br/>
