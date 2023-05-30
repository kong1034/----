# 번들러가 뭘까?
코딩을 하면서 생긴 수많은 파일들을 하나의 파일로 압축시켜주는 도구이다.

## 번들러의 종류?
번들링을 도와주는 프론트엔드 프레임워크중 대표적으로 웹팩이 있다.

## 웹팩의 장점과 단점
- 웹팩의 장점 - 메모리 손실을 막아주고 성능을 높여준다.
- 웹팩의 단점 - 비교적 러닝커브가 높다. 프로젝트가 크다면 속도가 느려진다.

## 웹팩 설정 파일
프로젝트의 최상위 루트폴더에 webpack.config.js or ts 를 이용하여 생성해준다. 웹팩의 문법을 이용하여 설정파일안을 채워주면 설정한 대로 번들링이 실행된다.

## 웹팩의 기본적인 문법
entry - entry에 적은 파일을 중심으로 아래의 파일들이 압축된다.

output - output에 적은 파일경로를 토대로 entry에서 적은 파일들이 뭉쳐서 새로 생긴다.

mode - production(배포), development(개발), none 3가지가 존재하고 상황에 맞게 적절히 사용한다.

loader - js 파일이 아닌 css나 image 같은 경우 번들링을 도와주는 도구이다. (사용한다면 설치 필요)
(ex) css-loader, style-loader, file-loader 등등

plugin - output으로 나온 파일들에 다양한 기능들을 줄수 있는 도구이다. (사용한다면 설치 필요)

## 명령어
웹팩 설치 - npm i webpack webpack-cli
설정웹팩실행 - npm webpack --config webpack.config.js or ts
로더 설치 - npm i css-loader style-loader 등등
